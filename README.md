# cordova-icon-gm

Automatic icon resizing for Cordova. Add `icon.png` to the root folder of your Cordova project and use cordova-icon-gm to automatically resize, copy and configure the icon for all current Android and iOS devices.

### Installation
`npm install -g cordova-icon-gm`

### Usage
Create a `icon.png` file in the root folder of your cordova project and run:
`cordova-icon-gm`

### Creating a cordova-cli hook
Since the execution of cordova-icon-gm is pretty fast, you can add it as a cordova-cli hook to execute before every build.

To create a new hook, go to your cordova project and run:

    $ mkdir hooks/after_prepare
    $ vi hooks/after_prepare/cordova-icon-gm.sh

Paste the following into the hook script:

    #!/bin/bash
    cordova-icon-gm

Then give the script +x permission:

    $ chmod +x hooks/after_prepare/cordova-icon-gm.sh

That's it. Now every time you `cordova build`, the icons will be auto generated.

### Requirements

- GraphicsMagick

- At least one platform was added to your project ([cordova platforms docs](http://cordova.apache.org/docs/en/3.4.0/guide_platforms_index.md.html#Platform%20Guides))
- Cordova's config.xml file must exist in the root folder ([cordova config.xml docs](http://cordova.apache.org/docs/en/3.4.0/config_ref_index.md.html#The%20config.xml%20File))

### Credits
All credit goes to [Alex Disler](https://github.com/AlexDisler) for his [cordova-icon](https://github.com/AlexDisler/cordova-icon) module, from which this project is forked from. The node [imagemagick](https://www.npmjs.org/package/imagemagick) module is deprecated in favor of [gm](https://www.npmjs.org/package/gm).

### License

MIT
