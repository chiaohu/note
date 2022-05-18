- [[HTML]]
- ` <!DOCTYPE html> #HTML5格式`
- ```
  <html> #所有網頁內容都要包在裡面
    <head>
       <title>標題</title>
       <meta charset="UTF-8"> # 編碼  
       <link rel="shortcut icon" href="favicon.ico"> #分頁圖片小ICON
       <meta name='description' content='網站描述文字' />
       <meta name-='keyword' content='關鍵字一, 關鍵字二, 關鍵字三' />
      # og:FB的設定
       <meta property="og:title" content="FB的標題"/>
       <meta property="og:description" content="FB的描述">
       <meta property="og:type" content="website"/>
       <meta property="og:url" content="FB上的網址"/>
       <meta property="og:image" content="FB的圖片"/>
       <!--螢幕解析度強制變成載具的寬度 RWD-->
       <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"> #手機板 IPAD 螢幕解析調整
      
       <meta http-equiv="X-UA-Compatible" content="IE=Edge" /> #讓IE最新的版本做渲染
  
       <link rel="stylesheet" href="css/style.css"> #CSS
       <script type="text/javasctipt" src="/js/alljs"></script> #javascript
       
       <link
       rel="stylesheet"
       href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
     />
      <link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css">
      <link href="css/lightbox.css" rel="stylesheet" />
    </head>   
    <body>
      <figure> #包含圖片與圖片說明
      <img src="圖片路徑" alt="文字敘述" title="">   # src="圖片路徑" ALT是給視障人士看的 title游標移到圖片上會顯示內容
      <figcaption>圖片描述 </figcaption>
      </figure>   
      <table class="price"> #表格
          <tr> # 列
            <th></th> # 表格標題 粗體字  空表格也要列出來
            <td colspan="2", rowspan="2" > # 欄  1.數字幾代表佔幾個欄位(橫向) 2.佔幾列(直向)         
            </td>            
          </tr>
      </table> 
  
      # form
      <form action="資料庫連結" method="get or post"> #post使用時機(允許使用者上傳檔案,表單很長,包含敏感資料(密碼)要將資料加到資料庫或刪除)
        <label for="mail">電子郵件</label> #在INPUT表格前，FOR跟ID要依樣出現點到LEBEL時會直接跳到表格裡
        <input id="mail" action="text" placeholder="請輸入電子郵件" name="mail">  #text:文字欄位;讓輸入者輸入 #placeholder 在表格中出現文字 輸入時消失。
        <input action="text" placeholder="請輸入姓名" name="person">
        <input type="submit/password/date/email/url" value="下一步"> #submit:資料送出;password:輸入時會出現*; value:按鈕名子; date: 日期;
      
        #檔案輸入區塊{
        <form action="" method="post">
          <p>上傳檔案</p>
          <input type="file" name="user-song">
          <br>
          <input type="submit" value="upload">
        </form>
      }
       
      #radio 與 checkbox 應用
        <h2>性別</h2>
        <input type="radio" name="sex" value="male"> 男生   #radio是單選題
        <input type="radio" name="sex" value="female"> 女生
        <h2>興趣</h2>
        <input type="checkbox" name="hobby" value="movie"> 看電影  #checkbox是多選題;name跟value要傳送給資料庫
        <input type="checkbox" name="hobby" value="music"> 聽音樂
        <iuput type="checkbox" name="hobby" value="comix"> 看漫畫
        <br> # 換行
        <hr> #水平線
        <input  type="submit" value="送出">
  
        # select textarea 應用
        <select name="birth" id="birth">     #下拉式選單 OPTION是選項
            <option value="1900" disabled (之後不能再選擇)>1900</option>
            <option value="1901">1901</option>
        </select>
        <h2>內容:</h2>
        <textarea name="content"  cols="30" rows="10"></textarea> #表格 cols 填入字元 rows 行數
        <br>
      </form>
  
      # iframe屬性 插入一個HTML網頁
      <iframe  width="450" height="350" src="網址"></iframe>
  
      <audio src"音訊位置" controls autoplay> </audio> #controls:是否顯示控制按鈕 autoplay:是否自動撥放;
  
      <script src="https://unpkg.com/swiper/swiper-bundle.js"></script>
      <script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
      <script src="js/lightbox-plus-jquery.js"></script>
      
    </body>
  </html>
  ```
- ---
- [[CSS]]
- ```
  # 游標碰到會觸發  擬態選擇器
  p:hover{
    transform: scale(1.2); /* 移到目標上會變大 */
  }
  
  # 滑鼠點住的時候觸發
  p:active{
  	transition: all 1s;  /*轉場*/
  }
  
  #*代表所有HTML標籤都可以吃到 before&after是偽元素
  *,*:before,*:after{   
  
  }
  
  #以CSS元素插入圖片，如果長寬跟圖片不一樣會重複出現
  .box{                  
      width: 350px;
      height: 60px;
      background-image: url(路徑);
      background-repeat: no-repeat, repeat-x, repeat-y; # 小張圖片預設值會自動重複填滿,如果切成小張的圖片不想重複,不想重複,X軸重複,Y軸重複
      background-color: blue;
      background-position: top, 30px 50%; # 調整位置
      background: url(路徑) no-repeat blue 50%; # 前面四行的縮寫
  }
  
  # 圖片取代LOGO
  .hearder h1{
      float: left;
  }
  .header h1 a{
      background-image: url(路徑);
      display: block;
      text-indent: 101%;  #這三行以圖片取代文字
      overflow: hidden (scroll); #scroll加入卷軸
      white-space: nowrap;
  }
  
   mixin用法
  
    @mixin hide-text($參數,$參數) {
      text-indent: 101%;
      white-space: nowrap;
      overflow: hidden;
    }
  
    .header {
      @include hide-text($參數,$參數);
    }
  
    @mixin pad {
      @media (max-width: 768px){
        @content
      }
    }
  
    .header{
      @include pad() {
        height: 30px;
      }
    }
    
    視差滾動網頁設計 start
    @mixin overflow {
      overflow: hidden;
      background-image: url();
      background-position: center center;
      background-size: cover;
      background-attachment: fixed;
    }
  ```
-