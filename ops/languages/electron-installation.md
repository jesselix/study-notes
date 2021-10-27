# Electron Installation

## Install
- Install Node.js  
go to: <u>Node.js Installation</u>

- Install Electron
``` zsh
cnpm install -g electron
```

## Validation
- Check the Electron Version
``` zsh
electron -v
```

- Output
``` zsh
v15.1.1
```

## Install
- Install electron-packager
``` zsh
cnpm install electron-packager -g
```

## Run
``` zsh
npm install
npm start
```

## Package
- Windows
``` zsh
electron-packager . filebox --platform=win32 --arch=x64 --icon=./assets/images/icon.ico --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

- macOS
``` zsh
electron-packager . filebox --platform=darwin --arch=x64 --icon=./assets/images/icon.icns --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

- Linux
``` zsh
electron-packager . filebox --platform=linux --arch=x64 --icon=./assets/images/icon.png --out=./out --asar --app-version=0.0.1 --overwrite --ignore=node_modules
```

- Commands above can be configed in package.json and then run commands below.
``` zsh
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


