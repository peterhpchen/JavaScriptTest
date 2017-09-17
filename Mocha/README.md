# Mocha
> JavaScript的測試框架

## Installation
安裝nodejs
> https://nodejs.org/

使用npm安裝Mocha
```
sudo npm insatll mocha
```
## Hello Mocha
> 建立第一支Mocha測試程式

建立測試資料夾, 並新增HelloMocha.js
```
mkdir test
cd test
code HelloMocha.js
```
本文使用visual studio code進行, 可以選擇自己喜好的Editor

貼上以下的程式碼
```javascript
var assert = require('assert');
describe('Array', function() {
  describe('#indexOf()', function() {
    it('should return -1 when the value is not present', function() {
      assert.equal(-1, [1,2,3].indexOf(4));
    });
  });
});
```
開啟終端機, Run Mocha
```
$ mocha


  Array
    #indexOf()
      ✓ should return -1 when the value is not present


  1 passing (10ms)
```
mocha預設是抓名為test的資料夾啟動測試,如果測試資料夾名稱不是test, 請在指定後面加上`folder name`
```
mocha [folder name]
```

在package.json裡設置測試時使用mocha
```
"scripts": {
    "test": "mocha"
  }
```
使用npm跑測試案例
```
npm test
```