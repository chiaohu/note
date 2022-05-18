- ```
  //執行node.js檔案
  新增資料夾並且新增一個app.js檔案
  在終端機輸入 node app.js
  node 的全域叫global
  在個別的js檔用VAR定義變數不會被GLOBAL所應用
  
  // 有兩個檔案 a.js b.js(都在同一層) a要拿取b.js的資料
  //a.js
  var 變數 = require('b的路徑不用+.js')
  //b.js 第一種寫法
  module.exports = 要給a的資料
  //b.js 第二種寫法
  exports.資料or函式 a啟用 變數.資料or函式
  如果2種寫法都有只會吃到第一種寫法
  
  //建立內建模組http
  var http = require('http')
  http.createServer(function(request, response) {
      response.writeHead(200, {"Content-Type": "text/plain"});
      response.write('helo!!');
      response.end();
  }).listen(8080);
  
  //抓取檔案路徑
  var path = request('path');
  //分析路徑
  console.log(path.parse('路徑'))
  
  //建立package.json
  npm init
  
  //nodemon
  nodemon XX.js 儲存後直接顯示變化
  
  // 網頁錯誤或是程式錯誤的錯誤訊息
  
  app.use(function(req, res, next) {
      res.status(404).send('抱歉,您的頁面找不到')
  })
  
  app.use(function(err, req, res, next) {
      res.status(500).send('程式有些問題，請稍後嘗試')
  })
  
  // express 增加靜態檔案的路徑
  var express = require('express')
  var app = express()
  
  app.use(express.static('資料夾的名稱'))
  
  app.get('網址',functio(req,res){
      // 渲染畫面
      res.render('search')
  })
  
  app.post('網址',functio(req,res){
      // 轉址
      res.redirect('search')
  })
  ```
-