(Inspired by Bruno Simon's 3JS template)

At its most basic, we have:
- Scene
- Objects
- Camera
- Renderer
---

```javascript
import * as THREE from 'three'
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'
```

**Scene**:
```javascript
const scene = new THREE.Scene();
const canvas = document.querySelector('canvas.webgl');
```
(Selecting canvas element with class="webgl")

For our object, we'll need a mesh consisting of a *geometry* and a *material*. e.g. red default cube:
```javascript
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0xff0000 });
const mesh = new THREE.Mesh(geometry, material);
scene.add(mesh);
```
(In this case, the argument passed to the basic material constructor is itself an object {} containing all our options. See 3JS docs for details)

**Aspect Ratio** and **Camera**:
```javascript
const sizes = {
	width: window.innerWidth,
	height: window.innerHeight
};

// FOV, aspect, (clipping): near, far:
const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height, 0.1, 100);
camera.position.set(0, 0, 1);
scene.add(camera);
```

**Orbit Controls:**
```javascript
const controls = new OrbitControls(camera, canvas);
controls.enableDamping = true;
```
(Orbit controls are optional, but pretty standard for most 3JS demos.)

**Renderer**:
```javascript
const renderer = new THREE.WebGLRenderer({canvas: canvas});
renderer.setSize(sizes.width, sizes.height);
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
```
If the pixel ratio of our device is 1, we set it at 1. Otherwise, capped at 2. Some high-DPI retina-displays might go as high as 3 or 4, but that will hinder performance.
The canvas for our WebGLRenderer is the reference we created above.

**Resize Event Listener:**
```javascript
window.addEventListener('resize', () => {

// Update sizes
sizes.width = window.innerWidth;
sizes.height = window.innerHeight;

// Update camera
camera.aspect = sizes.width / sizes.height;
camera.updateProjectionMatrix();

// Update renderer
renderer.setSize(sizes.width, sizes.height);
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
});
```
Important to update camera projection matrix when properties of camera that affect projection (i.e. aspect ratio) change.

**Animation**:
```javascript
const clock = new THREE.Clock();
const tick = () => {

// For animation (e.g. position.x * elapsedTime):
const elapsedTime = clock.getElapsedTime();

// Update controls
controls.update();

// Render frame
renderer.render(scene, camera);

// Call tick on next frame
window.requestAnimationFrame(tick);
}

// Start
tick();
```

