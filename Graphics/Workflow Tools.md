Need a "build tool" or "bundler" to optimize, cache break, run a local server for testing. (In the past, just opened index.html in browser, but browsers limit functionality of this approach for security.)

Many options: Webpack, Parcel, Vite, etc. I like **Vite**.

Need **Node.js** and **npm** to manage dependencies. Funny tidbit from Wikipedia:
```
Although "npm" is commonly understood to be an abbreviation of "Node Package Manager", it is officially a recursive backronym for "npm is not an acronym".
```
---
```
npm init -y
```
Create a package.json with minimal information to run Node.js project

package.json and package-lock.json enable project sharing. (Don't share or modify 'node-modules', this folder contains dependencies.) To install dependencies according to package.json:
```
npm i
```
package-lock is optional; If present, specifies exact versions of dependencies with no tolerance.

---
```
npm install vite
npm install three
```
In package.json,
```json
  "scripts": {
    "dev": "vite",
    "build": "vite build"
  }
```
Then to run local server we just call
```
npm run dev
```
---
# Vite Config

We'll need to install vite restart plugin:
```
npm install vite-plugin-restart
```
Then, an example vite.config.js moving forward:
```javascript
import restart from 'vite-plugin-restart'  

export default {
	root: 'src/',
	publicDir: '../static/',
	server:
	{
		host: true,	
		open: true
	},
	build:
	{
		outDir: '../dist',	
		emptyOutDir: true,
		sourcemap: true
	
	},
	plugins:
	[
		restart({ restart: [ '../static/**', ] }) 
	],
}
```
Config exported as an object which Vite will use to set up development environment.
- Root defines source file directory (js, css, index.html)
- publicDir specifies static assets folder (textures, models, images); served as if available in root folder
- Server settings:
	- host: true means development server will be accessible to other devices on local network, not just localhost
	- open option controls whether browser should open automatically when server starts
- Build settings:
	- outDir, specifies build directory, one level up from src/ (root)
	- emptyOutDir, will empty old files from dist/ on build
	- Source maps help with debugging by mapping minified code back to source
- Plugins: restart will restart server if any file in static/ is modified