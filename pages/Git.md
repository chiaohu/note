- ```
  // git/bash github
  回上一層: cd..
      展開列表: ls
  新增資料夾 mkdir 資料夾名稱
  新增檔案 touch 檔案名稱
  加入索引 git add.全部加入
  檢查狀態 git status
  提交更新 git commit - m '修改紀錄'
  查詢紀錄 git log
  
  忽略檔案
  新增.ignore
  在.ignore檔案上新增
  1.名稱
  2. *.格式(html)
  3. 資料夾名稱/
  
      HEAD 目前所在位置指標
  git reset HEAD 取消索引
  git reset --hard 還原工作目錄與索引，跟最後一次COMMIT保持一樣
  git branch 瀏覽目前分支
  git checkout 檔案名稱: 回復檔案到最新COMMIT狀態
  git checkout 前4碼: 瀏覽當時的程式碼
  git checkout 分支名稱: 移動到分支
  git checkout master: 回復到當前狀態
  git branch + 名子 : 新增分支
  在主線裡打git merge 分支名稱: 合併成分支的狀態
  當主線與分支同時更新並且合併發生衝突時 將程式碼確認後重新加入索引 git add.git commit - m '版本內容'
  
  標籤（tag）」是一個指向某一個 Commit 的指標。標籤一旦貼上去之後，不管 Commit 怎麼前進，標籤還是留在原來貼的那個位置上。
  git tag + 標籤名稱: 新增標籤
  git tag - d + 標籤名稱: 刪除標籤
  git tag - am "備註內容" + 標籤名稱: 新增標示標籤的備註
  git tag - n: 查詢詳細標籤與備註
  git checkout + 標籤名稱: 切換到標籤的commit  git checkout master 回到最新版
  git tag 查詢標籤
  
  暫存檔案
  git stash: 暫時儲存目前狀態
  git stash list: 瀏覽暫存列表
  git stash pop: 還原暫存狀態
  git stash drop: 清除最新暫存
  git stash clear: 清除全部暫存
  
  推送分支到遠端資料庫
  git clone(Url): 第一次下載專案使用
  git remote: 查詢遠端數據庫
  git remote rename + 原名稱 + 修改名稱
  git push + 遠端主機名稱 + 分支名稱
  
  git pull: 已經有專案只是要更新最新版本
  pull 這個指令是包含 merge 的
  如果要避免直接 merge 可使用 git fetch
  拉下來後可在自行切換分支及 merge
  ```