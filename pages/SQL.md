- ```
  primary key 唯一值
  foreign key 外鍵 -> 對應另一份表格的primary key 讓表格跟表格之間產生關聯但是也可以對應自己的表格
  
  //創建資料庫
  CREATE DATABASE `資料庫名子`; -> 選取按閃電
  SHOW DATABASES; //列出所有資料庫
  DROP DATABASE `資料庫名子`; //刪除資料庫
  USE `資料庫名子` //使用資料庫
  
  //SQL資料型態
  INT -- 整數
  DECIMAL(m,n) -- 有小數點的數 m:總共有幾位數 n:小數點占了幾位
  VARCHAR(n) -- 字串 n:最多能存放幾個字元
  BLOB -- (Binary Large Object) 圖片 影片 檔案...
  DATE -- 'YYYY-MM-DD' 日期
  TIMESTAMP -- 'YYYY-MM-DD HH:MM:SS' 紀錄時間
  
  //創建表格
  CREATE TABLE `tablename`(
      //設定屬性
      `id` INT PRIMARY KEY,
      `name` VARCHAR(20),
      `major` VARCHAR(20)
  );
  
  //新增屬性
  ALTER TABLE `tablename` ADD attrname DECIMAL(3,2);
  //刪除屬性
  ALTER TABLE `tablename` DROP COLUMN attrname;
  
  //檢查表格
  DESCRIBE `tablename`;
  //刪除表格
  DROP TABLE `tablename`;
  ```