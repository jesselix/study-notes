# Electron

## Configuration


## Process
1. package.json
Define your app's starting point: main.js

2. main.js
Main process: spin up your app and create a renderer process.

3. index.html
Renderer process: layout and style your app's interface.

4. Use IPC to do tasks in and get info from main process.

## Lifecycle
- ready
- dom-ready
- did-finish-load
- window-all-closed
- before-quit
- will-quit
- quit
- closed

MainWindow  
ipcRenderer.send -> ipcMain.on

Electron App  
mainWindow.webContents.send
ipcRenderer.on


## References
