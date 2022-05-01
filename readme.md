##課程心得

很喜歡小賴老師的互動式的上課方式！讓我們不是一昧接受資訊，而是利用提出問題使我們可以動腦思考，不只加深印象也更有利於我們內化課程內容。
老師上課講了很多實務會碰到的東西，像是向他人詢問的方式、資料庫設計時需要注意的事項、提交訊息撰寫以及code style等問題，而且對我們提出的問題也都會花時間為我們詳細解釋，課程內容非常充實，如果不小心閃神就會錯過很多經驗分享，超級期待之後的課程！

##課程筆記

####command
|檔案位置||指令參數||
|-------|:------------:|-------|:------------:|
|.|同一層|-a|全部|
|..|上一層|-f|強制|
|~|根目錄|-r|遞迴|

|指令|MacOs / Linux|
|-------|:------------:|
|cd|前往|
|pwd|目前位置|
|ls|顯示資料夾檔案|
|mkdir|開新資料夾|
|touch|開新**檔案**|
|cp|複製|
|mv|移動|
|rm|刪除|
|clear|清除iterm上內容|

###git-分散式版本控制
####結構
1. 本地
    1. 工作區域（add to 暫存）
    1. 暫存區（commit to 儲存庫）
    1. 儲存庫（push to 遠端）
1. 遠端

####使用教學
環境設定
```bash
#建立repo，使git可以監聽該資料夾
git init

#設定環境變數
git config --global user.name = "$username"
git config --global user.email = "$useremail"

#確認設定狀態
cat ~/.gitconfig #這是在全域的，局部檔案也可自行修改
```
####工作區 git 操作
```bash
#把檔案從工作目錄加至暫存區
git add $filename
git commit -m "記錄提交緣由"


#查看 config log
git log #可以看到commit的相關內容、誰提交的
git status #可以看到目前各區域狀況


#從暫存區域回到工作目錄
$ git restore --staged $filename

#捨棄在工作目錄的改變(包括修改與刪除)
$ git restore $filename

#比較檔案的差異   
#確認後，可以按 "q" 離開
$ git diff


#已經加入過的檔案，可以不用 git add 重加
#可以同時加入這次的修改與訊息
$ git commit -am "訊息"
```
####分支
```bash
#檢視分支
$ git branch

#新增分支
$ git branch $branch-name

#切換分支
$ git switch $branch-name

#合併分支 feature-login -> main
#1. 先切換到 main
$ git switch main
#2. 再把 feature-login 合併進來
$ git merge feature-login

# 刪除本地分支
$ git branch -d $branch-name
```

###遠端Remote
```bash
# 建好repo後連動
git remote add origin https://github.com/yvonne0414/git-workshop.git
git branch -M main
git push -u origin main 
# 有推過就只要寫git push就好
# .git 中的 config 會有紀錄
# 但新分支要再重新 -u orgin $branch-name
```


