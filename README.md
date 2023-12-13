# stats.js

### Code Fork Changes

This fork was created primarily to address: https://github.com/mrdoob/stats.js/pull/33. Above and beyond minor code formatting changes, I have added the aforementioned ability to retrieve the current `fps rate` via `[instance].fps`, which can be helpful for activities such as updating shader uniforms.

```js
const stats = new Stats();
...
uniforms.iFrameRate = stats.fps;
...
stats.update();
```

### Installation

Since these changes aren't unfortunately part of the main line, the typical npm install instructions don't apply. With that being said, you can simply copy-paste the Stats.js file and include a typical html file reference, or use a module reference as follows:

```js
import Stats from "./your/path/stats.js";
```

#### JavaScript Performance Monitor

This class provides a simple info box that will help you monitor your code performance.

- **FPS** Frames rendered in the last second. The higher the number the better.
- **MS** Milliseconds needed to render a frame. The lower the number the better.
- **MB** MBytes of allocated memory. (Run Chrome with `--enable-precise-memory-info`)
- **CUSTOM** User-defined panel support.

### Screenshots

![fps.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/fps.png)
![ms.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/ms.png)
![mb.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/mb.png)
![custom.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/custom.png)

### Usage

```javascript
var stats = new Stats();
stats.showPanel(1); // 0: fps, 1: ms, 2: mb, 3+: custom
document.body.appendChild(stats.dom);

function animate() {
  stats.begin();

  // monitored code goes here

  stats.end();

  requestAnimationFrame(animate);
}

requestAnimationFrame(animate);
```
