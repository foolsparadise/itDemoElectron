## ElectronDemo  
此Demo是如何创造一个，自写的Demo举例，工程源码已附有   
.icns图片来自于https://www.easyicon.net/iconsearch/%E7%86%8A%E7%8C%AB/ 如果侵权即删    
以下为完成工程源码的步骤：  
## Howto  
do:  
```  
（创建一个目录，在此目录下）npm init  
(会有一些提示，do sth)  
```  
then modify package.json file as like this:  
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
npm install --save-dev electron (我不知道npm install electron是不是和这条命令同样功能，另，执行可能会自动生成package-lock.json文件和node_modules目录？)  
npm install -g electron-packager (安装打包的，package.json文件会添加一项devDependencies)  
```  
## add electron-packager scripts in package.json file like this  
```  
{  
  "name": "electrondemo",  
  "version": "1.0.0",  
  "description": "",  
  "main": "main.js",  
  "scripts": {  
    "test": "echo \"Error: no test specified\" && exit 1",  
    "start": "electron .",  
    "packager": "electron-packager . electrondemo --arm64 --out ./Release --arch=x64 ---app-version=1.0.0 --electron-version=2.0.2",  
    "packageDarwin": "electron-packager . 'electrondemo' --platform=darwin --arch=x64 --icon=electrondemo.icns --out=./Release --asar --app-version=1.0.0 --ignore=\"(dist|Release|src|docs|.gitignore|LICENSE|README.md|webpack.config*|node_modules)\"",  
    "packageDarwin": "electron-packager . 'electrondemo' --platform=darwin --arch=x64 --icon=electrondemo.icns --out=./Release --asar --app-version=1.0.0",  
    "packageWin": "electron-packager . 'electrondemo' --platform=win32 --arch=x64 --icon=electrondemo.ico --out=./Release --asar --app-version=1.0.0 --ignore=\"(dist|Release|src|docs|.gitignore|LICENSE|README.md|webpack.config.js|node_modules)\"",  
    "packageWin": "electron-packager . 'electrondemo' --platform=win32 --arch=x64 --icon=electrondemo.ico --out=./Release --asar --app-version=1.0.0",  
    "packageLinux": "electron-packager . 'electrondemo' --platform=linux --arch=x64 --out=./Release --asar --app-version=1.0.0 --ignore=\"(dist|Release|src|docs|.gitignore|LICENSE|README.md|webpack.config.js|node_modules)\"",  
    "packageLinux": "electron-packager . 'electrondemo' --platform=linux --arch=x64 --out=./Release --asar --app-version=1.0.0"  
  },  
  "author": "",  
  "license": "MIT",  
  "devDependencies": {  
    "electron": "^2.0.2"  
  }  
}  

```  
## Run  
```  
npm start  
```  
## Release  
```  
(Mac system)npm run-script packager  
(Mac system)npm run-script packageDarwin  
(Windows system，如果是Mac系统编译则需要先安装wine)npm run-script packageWin  
(Linux system)npm run-script packageLinux  
```  
