# Electron Installation

## Install
- Install Node.js  
go to: 
[Node.js Installation](/languages/node-js-installation.md)

- If you are in China, modify the electron mirror
``` bash
npm config set ELECTRON_MIRROR https://registry.npmmirror.com/-/binary/electron/

```
- or edit the npm config file
``` bash
npm config edit
```

- Install Electron
``` bash
npm install -g electron
```

``` bash
npm install -g nodemon
```

## Validation
- Check the Electron Version
``` bash
electron -v
```

- Output
``` bash
v25.0.1
```

## Install
- Install electron-packager
``` bash
cnpm install electron-packager -g
```

## Init the package.json
``` bash
npm init
```

## Run
``` bash
npm install
npm start
```

## Package
- Windows
``` bash
electron-packager . project-name --platform=win32 --arch=x64 --icon=./assets/images/icon.ico --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

- macOS
``` bash
electron-packager . project-name --platform=darwin --arch=x64 --icon=./assets/images/icon.icns --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

- Linux
``` bash
electron-packager . project-name --platform=linux --arch=x64 --icon=./assets/images/icon.png --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

- Commands above can be configed in package.json and then run commands below.
``` bash
npm run package-win
npm run package-mac
npm run package-linux
```

## VS Code Settings
- add launch.json in debug


## References
> Electron  
https://www.electronjs.org/

> Electron安装及打包exe  
https://blog.csdn.net/fukaiit/article/details/90964319

> electron 安装步骤
http://www.manongjc.com/detail/29-hxqrypcghyryvzz.html
