# Karma
> JavaScript的測試執行器

## Installation
Install Karma Command Line Interface(CLI)
```
sudo npm install -g karma-cli
```
Install Karma
```
sudo npm install karma
```
由於Karma只是一個測試執行器(test runner),並不是測試框架(test framwork),因此需要安裝karma的外掛程式來選擇我們要使用的框架
```
sudo npm install karma-mocha mocha
```
Karma再做測試的時候會開啟遊覽器來執行測試, 因此需要再安裝啟動器(launcher)外掛
```
sudo npm install karma-firefox-launcher
```

## config
> karma測試流程組態設定

karma執行時會依照設定的組態做測試

有兩種方式可以建立組態檔

* 自己新增karma.config.js做設定
* 終端鍵入`karma init`使用shell進行設置

### 屬性說明
* **frameworks**: 需要的框架, 這裡需要mocha跟chai
* **files**: 要載入的檔案, 包括要測試的程式及測試程式
* **browsers**: 測試使用的瀏覽器, 這裡使用firefox
* **autoWatch**: 使否監聽變更, 如果為`true`則files上的檔案有變更的話會重新執行karma
## Hello Karma
> 執行Karma

將`Mocha/test`複製到karma下, 執行下列指令
```
karma start
```
會看到下面的錯誤
```
Firefox 55.0.0 (Ubuntu 0.0.0) ERROR
  ReferenceError: require is not defined
  at http://localhost:9881test/HelloMocha.js:1
```
原因是Karma是一個client端的測試執行器, `require`是nodejs的語法, Karma並不支持, 需要利用chai替換assert

使用npm安裝chai
```
npm install chai karma-chai
```
karma.config.js裡的frameworks加上chai
```javascript
frameworks: ['mocha', 'chai'],
```
修改`HelloMocha.js`
```javascript
//var assert = require('assert');
var assert = chai.assert;
```