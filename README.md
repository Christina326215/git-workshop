---
title: My First Git Workshop Note
tags: git notes
description: My First Git Workshop Note
version: 20210724
---

# My First Git Workshop Note

* 版本控制系統 (Version Control System, VCS) 能記錄任何專案內各個修改過的版本，並讓使用者可以取得特定版本的系統。
且又分為 集中式版本控制系統 (Centralized Version Control System) 與 分散式版本控制系統 (Decentralized Version Control System)。

* 集中式版本控制系統 - 係指版本都儲存在中央的伺服器，且需要有網際網路的情況下才能使用。就是說用自己的電腦時，需要先到中央伺服器取得最新版本，進行新增刪除修改後，再提交回去數據庫。

* 分散式版本控制系統 - 沒有「中央伺服器」，每個人的電腦上都有一個完整的數據庫，這樣工作的時候就不需要網際網路惹，因為自己的電腦上就有數據庫了。

==而 Git 就是分散式版本控制系統。==

---
## 基本終端機與git指令

#### git相關設定
```bash=
$ git --version
$ git config --global user.name "<使用者名字>"
$ git config --global user.email "<電子信箱>"
$ git init
```

#### 查看所有清單
```bash=
$ ls -al
```

#### 新增資料夾
```bash=
$ mkdir {資料夾名稱git-workshop}
```

#### 刪除資料夾
```bash=
$ rm -r {資料夾名稱git-workshop}
```

#### 新增檔案
```bash=
$ touch {檔案名稱test.txt}
```

#### 刪除檔案
```bash=
$ rm {檔案名稱test.txt}
```

#### 轉換資料夾或檔案
```bash=
$ cd {路徑}
```

#### 表示所在路徑位置
```bash=
$ pwd
```

####  回到家目錄
```bash=
$ cd ~
```

#### 查看git設定清單
```bash=
$ git config --list
$ cat ~/.gitconfig
```

#### git初始化
```bash=
$ git init
```

#### git查看狀態
```bash=
$ git status
```

#### 查看git紀錄
```bash=
$ git log
$ git log --oneline --graph
$ git log -p {檔案名稱}
$ git log --stat
$ git log --stat {檔案名稱} 
$ git log --grep="想搜尋的字"
$ git blame {檔案名稱}
```

#### 比較檔案的差異，確認後，可以按 q 離開。
```bash=
$ git diff
```

#### git修改檔案內容
```bash=
$ nano {檔案名稱}
```

#### git讀取檔案內容
```bash=
$ cat {檔案名稱}
```

#### 將工作目錄(working directory)中的檔案加入到暫存區域(staging area)
```bash=
$ git add {檔案名稱}
```

#### 將暫存區域(staging area)中的檔案加入到儲存庫(repository)
```bash=
$ git commit -m "敘述"
```

#### 同時 add 跟 commit，只有針對已經 tracked 檔案才有效(非新建)
```bash=
$ git commit -am "敘述"
```

####  從 git 中移除，且真的移掉檔案 
```bash=
$ git rm {檔案名稱}
```

#### 仍保留硬碟中的檔案(從 git 中移除，但是檔案還在，只是沒有在git管理之下) 
```bash=
$ git rm --cached {檔案名稱}
```

#### 從暫存區域回到工作目錄
```bash=
$ git restore --staged {檔案名稱}
```
 
#### 捨棄在工作目錄的改變(包括修改與刪除)
```bash=
$ git restore {檔案名稱}
```

#### 創立git分支
```bash=
$ git branch {分支名稱}
```

#### 查看目前git分支所在位置
```bash=
$ git branch 
```

#### 轉換git分支
```bash=
$ git switch {分支名稱}
```

#### 合併git分支
```bash=
$ git merge {分支名稱}
```

#### 設定遠端repo的連結並且push到遠端 
```bash= 
$ git remote add origin {url}
$ git branch -M main
$ git push -u origin main
$ git push
```
#### 刪除本地分支
```bash= 
$ git branch -d {branch-name}
```
#### 從github上clone下來
$ git clone {url}

#### 版本控制的狀態分為工作區、暫存區與儲存庫
![](https://i.imgur.com/hGK7bxd.png)
![](https://i.imgur.com/luUKlnD.png)

#### git flow
![](https://i.imgur.com/Kweo8l6.png)

![](https://i.imgur.com/rV7GdFn.png)

參數的意義，不同指令會不一樣，但通常會是這樣

-a ==> all   全部

-f ==> force 強制

| Windows | MacOS/Linux | 說明 |
| -------- | -------- | -------- |
| cd     | cd     | 切換目錄 change directory    |
| cd     | pwd     | 顯示目前所在路徑     |
| dir     | ls     | 列出目前檔案夾的檔案列表  list   |
| mkdir     | mkdir     | 建立新的檔案夾  make dir   |
| copy     | cp     | 複製檔案   copy  |
| move     | mv     | 移動檔案   move  |
| del     | rm     | 刪除檔案    remove |
| cls     | clear     | 清除畫面上的內容     |


#### 套件管理系統
PHP => composer

Unix-like / Linux-like

MacOS => brew

Ubuntu => apt

CentOS => yum

