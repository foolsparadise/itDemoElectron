## ElectronDemo  
## Howto  
do:  
```  
npm init  
(do sth)  
```  
modify package.json file as like this:  
```  
{
  "name": "electrondemo",
  "version": "1.0.0",
  "description": "",
  "main": "main.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "electron .",
    "packager": "electron-packager . electrondemo --arm64 --out ./Release --arch=x64 ---app-version=1.0.0 --electron-version=2.0.2"  
  },
  "author": "",
  "license": "MIT"
}
```  
add new file main.js, index.html  
do:  
```  
npm install  
npm install --save-dev electron (可能会自动生成package-lock.json文件和node_modules目录？)  
npm install -g electron-packager  
```  
## Run  
```npm start```  
## Release  
```npm run-script packager```
