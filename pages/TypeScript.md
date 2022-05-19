- JavaScript 沒有空值（ [[Void]] ）的概念，在 [[TypeScript ]] 中，可以用 [[void ]] 表示沒有任何返回值的函式：
- ```
  function alertName(): void {
      alert('My name is Tom');
  }
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
-