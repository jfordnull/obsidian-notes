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
