- ```
  data-* dataset
  在HTML標籤新增 data -* 屬性可使用dataset.* 來找尋值
  
  AJAX
  
  var xhr = new XMLHttpRequest();
  //('格式','要讀取的網址',同步與非同步)
  xhr.open('get', '網址', true)
  //true 非同步，不會傳資料回來就讓程式繼續往下跑，等到回傳才會自動回傳
  //false 會等資料回傳回來才讓程式繼續往下跑
  
  xhr.send(null); //沒有要傳資料放一個空值NULL
  
  readtState //撈的資料的狀態 
  0 - 已經產生一個XMLHttpRequest，但是還沒有連接你要撈的資料
  1 - 已用了open()但還沒有把資料傳送過去
  2 - 偵測到有用send
  3 - loading
  4 - 撈到資料了
  
  readtState 變成4  (資料確定回傳之後)會觸發 true時使用
  xhr.onload = function () {
  
  }
  
  CORS 是否提供跨網域抓取資料
  
  將資料傳送到後端驗證
  
  var xhr = new XMLHttpRequest();
  xhr.open('post', '網址', true);
  xhr.setRequestHeader('content-type', 'application/x-www-form-urlencoded'); //('content-type', 'application/json') json格式 //傳送資料的內容與格式
  xhr.send('email=12345@gmail.com&password=12345');//如果是傳json格式需要將他轉變為字串 JSON.stringify();
  
  ES6語法
  let const 避免汙染全域變數 沒有向上提升特性/同個區塊不能重複命名
  用來宣告區塊裡的變數 區塊= { }
  const 是唯獨變數 - 不能去做修改 /通常設置不能被變更的變數 如果變數是 {} 與 () 需要增加 Object.freeze(變數);
  
  //javascript核心篇
  javascript屬於靜態作用域: 變數的作用域在語法解析時，就已經確定作用域，不會再改變。
  動態作用域: 變數的作用域在函式調用時才決定。
  單執行緒的語言，一次只能執行一個程式碼，執行完後才會去執行下一個程式，如果程式內有非同步事件，非同步事件會先被放在事件佇列(Event queue)中，等到所有的程式堆疊都依序執行完後，才會去執行 事件序列內的程式，事件序列的程式在執行完後，會再不斷的查看事件佇列是否有新的事件，有的話便執行，這稱為「持續檢查（continuous check）」。
  //嚴格相等
  NaN === NaN -> false;
  +0 === -0 -> true;
  //寬鬆相等
  寬鬆相等做比較時 布林與字串會轉為數值
  true == 1; !0 = 1  Number(!0) == 1
  false == 0;
  'true' == NaN;
  // Null、Undefined 不會被轉為數字型別來做比對
  Number(Null) = 0;
  Number(undefined) = NaN;
  null == undefined -> true;
  null === undefined -> false;
  
  //資料型別
  string: 文字
  number / NaN: 數值
  Boolean: 布林
  null: 空白值
  undefuned: 已宣告變數，但尚未指定值。
  
  //物件與非物件、使用包裹物件轉換
  10 == [10] -> true;
  String({ A: 'A' }) = [object Object];
  
  //運算子
  console.log(a && b); 如果A是false會直接回傳A如果是真值會無條件回傳第2個
  console.log(a || b); 如果A是false會直接回傳後面的值，如果A為真值則直接回傳A
  
  //物件與物件比的是參考位置 不是裡面的值
  { } == {} -> false;
  [] == [] -> false;
  
  var a = [];
  var b = a;
  a === b -> true; 參考位置相同;
  
  //物件實字 
  var object = {
      1: 1
  }
  物件裡面屬性一律式字串如果要取值不能用.要用中括號
  ex.object[1];
  新增
  object.cat = '饅頭'
  刪除
  delete object.cat;
  ** 變數無法被刪除，屬性可以
  var a = 1;
  window.b = 2
  delete a; // false
  delete b; // true
  
  //this call apply bind
  函式名稱.call(this的物件, 參數);
  函式名稱.apply(this的物件, [參, 數]);
  var 函式名稱2 = 函式名稱.bind(this的物件, 參數);
  函式名稱2(); 參數不用另外帶入
  
  //繼承與原型練
  
  在原型上新增屬性
  __proto__ //原型上 通常不建議使用應直接修改原本的建構函式
  prototype //函式上
  
  //「如果原型與物件內的屬性同名」那麼會以物件內的屬性優先，原型的屬性權重則較低
  
  //屬性特徵
  Object.defineProperty(物件, 屬性, (參數){
      value:
      Writable: true / false
      configurable: true / false ** 改為false後就不能變回true了
      enumerable: true / false
  })
  1.值
  2.可否寫入
  3.可否被刪除
  4.可否被列舉
  //延伸的物件方法
  Object.方法.(物件名稱)
  preventExtensions、seal、Freeze
  preventExtensions(防止擴充): 物件本身無法新增屬性，但是巢狀屬性可以擴充其他照舊
  seal(封裝): 無法新增或刪除物件屬性但是巢狀屬性可以擴充，也無法重新配置特徵，但是可以調整目前屬性值(包含preventExtensions的功能)
  Freeze(凍結): (包含preventExtensions與Seal的功能)無法調整屬性與屬性特徵。
  
  //let
  let
  1.一樣會有創造階段
  2.但從創造到實際宣告的階段會出現TDZ(暫時性死區) ，這個區域無法呼叫變數
  3.有創造到執行的概念，但不會預先出現undefined 而是出現錯誤提示
  (文件不會表明這與var的Hoisting相同)
  
  // 定錨滑動效果JS
  test(e) {
    if (window.scrollTo) {
      const target = document.getElementById(e.target.hash.replace('#', ''))
      e.preventDefault()
      window.scrollTo({ 'behavior': 'smooth', 'top': target.getBoundingClientRect().top + window.scrollY })
    }
  }
  
  // input輸入到一定的數字後自動focus下一個input  vue的作法
  
  .nextSibling:在相同的層級中返回下一個節點如果沒有下一個節點返回null
  input的name設定為index並且+上maxlength屬性限制字數(要讀取時要改成maxLength)
  接著寫函式帶入的參數為當下的input本身與總共的長度
  判斷條件為當input.value的長度等於限制的最大長度且input.name不等於總共的長度-1
  
  範例:
  <input
    v-for="(item,index) in cardNo"
    v-model="cardNo[index]"
    @keyup="changeInput($event.target, cardNo)"
    :name="index"
    maxlength="4"
    inputmode="numeric"
    pattern="[0-9]*"
    placeholder="4位數字"
  />
  
  changeInput(input, cardNo) {
    if (input.value.length === parseInt(input.maxLength) && parseInt(input.name) !== cardNo.length - 1) {
      input = input.nextSibling
    }
    input.focus()
  }
  ```