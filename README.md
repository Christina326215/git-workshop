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

== 而 Git 就是分散式版本控制系統。==

---
### 基本終端機與git指令
```bash=
## 查看所有清單
$ ls --al

## 新增資料夾
$ mkdir {資料夾名稱git-workshop}

## 刪除資料夾
$ rm -r {資料夾名稱git-workshop}

## 新增檔案
$ touch {檔案名稱test.txt}

## 刪除檔案
$ rm {檔案名稱test.txt}

## 轉換資料夾或檔案
$ cd {路徑}

## 表示所在路徑位置
$ pwd

##  回到家目錄
$ cd ~

## 查看git設定清單
$ git config --list
$ cat ~/.gitconfig

## git初始化
$ git init

## git查看狀態
$ git status

### 查看git紀錄
$ git log
$ git log --oneline --graph
$ git log -p {檔案名稱}
$ git log --stat
$ git log --stat {檔案名稱} 
$ git log --grep="想搜尋的字"
$ git blame {檔案名稱}

# 比較檔案的差異，確認後，可以按 q 離開。
$ git diff

## git修改檔案內容
$ nano {檔案名稱}

## git讀取檔案內容
$ cat {檔案名稱}

## 將工作目錄(working directory)中的檔案加入到暫存區域(staging area)
$ git add {檔案名稱}

## 將暫存區域(staging area)中的檔案加入到儲存庫(repository)
$ git commit -m "敘述"

## 同時 add 跟 commit，只有針對已經 tracked 檔案才有效(非新建)
$ git commit -am "敘述"

##  從 git 中移除，且真的移掉檔案 
$ git rm {檔案名稱}
## 仍保留硬碟中的檔案(從 git 中移除，但是檔案還在，只是沒有在git管理之下) 
$ git rm --cached {檔案名稱}

## 從暫存區域回到工作目錄
$ git restore --staged {檔案名稱}
 
## 捨棄在工作目錄的改變(包括修改與刪除)
$ git restore {檔案名稱}

## 創立git分支
$ git branch {分支名稱}

## 查看目前git分支所在位置
$ git branch 

## 轉換git分支
$ git switch {分支名稱}

## 合併git分支
$ git merge {分支名稱}

## 設定遠端repo的連結並且push到遠端  
$ git remote add origin {url}
$ git branch -M main
$ git push -u origin main
$ git push
```
---
## 新增hello.txt
##### 建立檔案使用指令touch hello.txt
```bash=
# 把檔案從 工作目錄 加到 暫存區
$ git add hello.txt

# 提交暫存區的檔案到儲存庫(repo)
$ git commit -m "add hello.txt"

# 查看紀錄
$ git log - -oneline

```
---
## 在新增hello.txt新增內文22222
##### 指令nano hello.txt修改文件
---
## 修改檔案之內文
##### 可使用git log --oneline來查看
```bash=
# 修改檔案

$ git status

# 比較檔案的差異，確認後，可以按q離開。
$ git diff

$ git add hello.txt

$ git commit -m "add 2222"

$ git status

# 同時 add 跟 commit，只有針對已經 tracked 檔案才有效
$ git commit -am "delete 1 and add 3"

$ git log

```
---
## 新增world.txt
##### 建立檔案使用指令touch
---
## 新增meff17.txt
##### 建立檔案使用指令touch
---
### 刪除檔案meff17.txt
##### $ git rm --cached {檔案名稱}
---
## 新增cache.txt
##### 建立檔案使用指令touch
---
### 刪除檔案cache.txt
##### $ git rm --cached {檔案名稱}
---
### 將已刪除的檔案cache.txt救回
$ git restore --staged {cache.txt}
$ git restore {cache.txt}
---

