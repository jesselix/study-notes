# Electron Installation

## Install
- Install Node.js  
go to: <u>Node.js Installation</u>

- Install Electron
``` shell
cnpm install -g electron
```

## Validation
- Check the Electron Version
``` shell
electron -v
```

## Install
- Install electron-packager
``` shell
cnpm install electron-packager -g
```

## Run
npm install
npm start

## Package
Windows
``` shell
electron-packager . filebox --platform=win32 --arch=x64 --icon=./assets/images/icon.ico --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

macOS
``` shell
electron-packager . filebox --platform=darwin --arch=x64 --icon=./assets/images/icon.icns --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

Linux
``` shell
electron-packager . filebox --platform=linux --arch=x64 --icon=./assets/images/icon.png --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

以上命令也可以在package.json里配置。如果在package.json里配置了，则：
``` shell
npm run package-win
npm run package-mac
npm run package-linux
```

## VS Code Settings
- add launch.json in debug


## References
> Electron Documentation  
http://www.electronjs.org/docs/tutorial

> Electron安装及打包exe  
https://blog.csdn.net/fukaiit/article/details/90964319

> 快速了解Electron：新一代基于Web的跨平台桌面技术  
https://www.cnblogs.com/imstudy/p/11022315.html

> 60分钟内创建一个Electron小程序  
https://www.bilibili.com/video/av50541022?from=search&seid=9559229007381130577
