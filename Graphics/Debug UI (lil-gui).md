```js
import GUI from 'lil-gui'; 
const gui = new GUI();
```
# Types of parameters:

**Range (with optional parameters):**
```js
gui.add(mesh.position, 'y').min(-2).max(2).step(0.1).name('elevation');
```
**Can modify custom properties using an object:**
```js
const customObj = {
	someVar: 3
};
gui.add(customObj, 'someVar');
```

**Checkbox (boolean property):**
```js
gui.add(mesh, 'visible');
```
**Color (one approach):**
Use a debug object to store the color value before it's modified by 3JS shader/render code:
```js
const debugObj = {};
debugObj.color = '#ff0000';
const material = new THREE.MeshBasicMaterial({ color: debugObj.color });

gui.addColor(debugObj, 'color').onChange(() =>
{
	material.color.set(debugObj.color);
});
```
**Functions:**
```js
debugObj.someFunction = () =>
{
	console.log('function triggered');
};

gui.add(debugObj, 'someFunction');
```
**Folders:**
```js
const geomTweaks = gui.addFolder('Geometry Tweaks');
// Close by default:
geomTweaks.close();

geomTweaks.add(mesh.position, 'y');
...
```
**GUI Setup:**
```js
const gui = new GUI({
	width: 300,
	title: 'A Debug UI',
	closeFolders: true
})
// If you want to close by default:
gui.close();
```

