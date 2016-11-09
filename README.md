# cordova-icon-gm

Automatic icon resizing for Cordova. Add `icon.png` to the root folder of your Cordova project and use cordova-icon-gm to automatically resize, copy and configure the icon for all current Android and iOS devices.

### Manual usage
1. `npm install -g cordova-icon-gm`
2. Place `icon.png` to the root folder of your Cordova project
3. Run `cordova-icon`.

### Automated usage
1. `npm install cordova-icon-gm --save-dev`

2. Create `my-icon-hook.js`
    ```javascript
    var icon = require('cordova-icon-gm');
    
    module.exports = function() {
      return icon.generate();
    };
    ```

3. Add hook to `config.xml`
    ```xml
    <hook src="my-icon-hook.js" type="after_platform_add" />
    ```

That's it. Now every time you `cordova add platform`, the icons will be auto generated.

### Requirements
- GraphicsMagick
- At least one platform was added to your project
- Cordova's config.xml file must exist in the root folder

### Credits
All credit goes to [Alex Disler](https://github.com/AlexDisler) for his [cordova-icon](https://github.com/AlexDisler/cordova-icon) module, from which this project is forked from. The node [imagemagick](https://www.npmjs.org/package/imagemagick) module is deprecated in favor of [gm](https://www.npmjs.org/package/gm).

### License

MIT
