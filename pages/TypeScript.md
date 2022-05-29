- JavaScript 沒有空值（ [[Void]] ）的概念，在 [[TypeScript ]] 中，可以用 [[void ]] 表示沒有任何返回值的函式：
- ```
  function alertName(): void {
      alert('My name is Tom');
  }
  // 陣列
  let arr : string[] = ['1']
  let arr : string[[]] = [[],[]]  //裡面一樣不能放數字
  
  //元祖
  let tuple: [number, string boolean] = [1, 'a', true] //只能照順序
  let tuple2: [string, string][] = [['a', 'b']] //只能照順序
  ```
- 宣告一個 [[void ]] 型別的變數沒有什麼用，因為你只能將它賦值為 undefined 和 null
- undefined 和 null 是所有型別的子型別，可以賦值給所有型別
- [[任意值型別]] :any允許被賦值為任意型別。
- 變數如果在宣告的時候，未指定其型別，那麼它會被識別為 [[任意值型別]]
- [[型別推論]]: [[TypeScript ]] 會在沒有明確的指定型別的時候推測出一個型別
- [[聯合型別]]:（Union Types）表示取值可以為多種型別中的一種。
- ---
- [[介面]]:（Interfaces）在物件導向程式語言中，是一個很重要的概念，它是對行為的一種抽象，而具體如何行動則需要由類別（classes）去實現（implement）。可用於對類別的一部分行為進行抽象以外，也常用於對「物件的形狀（Shape）」進行描述。
- background-color:: #978626
  heading:: true
  ```
  interface Person {
      readonly id: number; //唯獨屬性:唯讀的約束存在於第一次給「物件」賦值的時候，而不是第一次給「唯讀屬性」賦值的時候
      name: string;
      age?: number; // 可選屬性 可有可無
      [propName: string]: any; //任意屬性:一旦定義了任意屬性，那麼確定屬性和可選屬性的型別都必須是它的型別的子集：
  }
  
  let tom: Person = {
  	id: 89757,
      name: 'Tom',
      gender: 'male'
  };
  
  tom.id = 89757; // 報錯:不能再給ID賦值了
  ```
- ---
- object
- ```
  // 跟interface很像但是TYPE不可擴充
  type card = {
    name: string,
    desc: string
  }
  const obf: card {
    name: '1',
    desc: '2'
  }
  ```
- 編譯成JS檔案，終端機輸入TSC + 檔名。
- config檔 tsc --init
	- 編譯的路徑入口，先創建一個src的資料夾 rootDir: './src'
	- 編譯的路徑出口，創建一個dist資料夾 outDir:'./dist'
	- inlineSourceMpt : true 打開 這樣console可以直接看到TS檔的內容
- ---
- [[Enum]]:枚舉，列舉 : 用於取值被限定在一定範圍內的場景
- ```
  enum Days {Sun, Mon, Tue, Wed, Thu, Fri, Sat};
  // 手動賦值
  enum Days {
  Sun = 7, 
  Mon = 1, 
  Tue = 2, 
  Wed = 3, 
  Thu = 4, 
  Fri = 5, 
  Sat = 6
  };
  ```
- ---
- [[Union]]:聯合型別
- ```
  let myFavoriteNumber: string | number;
  ```
- ---
- [[type]]
- ```
  type A = number || string
  let a1: A
  a1 = 999 // 不能放不是的類型
  ```
- ---
- function
- ```
  function hello (a: string, b: string) {
  	return a + b
  }
  function hello2 (a, b): number {
  	return 999
  }
  // undefined
  function hello3 (a: string, b?:number): number {
  	// 沒有的話B是undefined
      if (B === undefined) return
      return 999
  }
  ```
- ---
- 斷言、unknown
- ```
  // 假設連接API收到的參數無法得知型別 ts推導不出來
  type Data {
  	userId: number,
      id: number,
      title: string,
      completed: Boolean
  }
  
  async function getData () {
  	const res = await fetch('api')
      const data = await res.json() as Data
  }
  ```
-