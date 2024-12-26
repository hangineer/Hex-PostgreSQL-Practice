# Hex-PostgreSQL-Practice
本專案為「六角學院 - 後端資料庫體驗營」的作業，練習如何使用 Docker 來開啟 postgresSQL 容器，並透過 DBever 去連接本地端的 postgresSQL 資料庫，並依照題目練習寫 postgreSQL 語法
## 快速連結
* [練習 postgreSQL 的連結](https://github.com/hangineer/Hex-PostgreSQL-Practice/blob/main/migrations/task/sqls/20241021064214-task-up.sql)
* [題目和資料表 的連結](https://luminous-mule-717.notion.site/1688722405bf80cfba8dc27b9f585bbb?pvs=4)
* [個人筆記分享 的連結](https://luminous-mule-717.notion.site/2024-12a8722405bf80d3bfaaeae56887d85a)

## 事前準備

下載安裝Docker Desktop
* [Windows版](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*1x0tato*_gcl_au*NDk4NzQwNjM1LjE3MjczMzQ0NDY.*_ga*MTkxMzI2NzM5NC4xNjU5OTM4NTcy*_ga_XJWPQMJYHQ*MTcyNzMzMzcxNy4xNTYuMS4xNzI3MzM0NDY4LjM3LjAuMA..)
* Mac版
  * [Intel處理器](https://desktop.docker.com/mac/main/amd64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*sjadaf*_gcl_au*NDk4NzQwNjM1LjE3MjczMzQ0NDY.*_ga*MTkxMzI2NzM5NC4xNjU5OTM4NTcy*_ga_XJWPQMJYHQ*MTcyNzMzMzcxNy4xNTYuMS4xNzI3MzM0NDY4LjM3LjAuMA..)
  * [M系列處理器](https://desktop.docker.com/mac/main/arm64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*sjadaf*_gcl_au*NDk4NzQwNjM1LjE3MjczMzQ0NDY.*_ga*MTkxMzI2NzM5NC4xNjU5OTM4NTcy*_ga_XJWPQMJYHQ*MTcyNzMzMzcxNy4xNTYuMS4xNzI3MzM0NDY4LjM3LjAuMA..)

下載並安裝Node.js
* [下載連結](https://nodejs.org/zh-tw)

下載並安裝Dbeaver Community
* [Windows版](https://dbeaver.io/files/dbeaver-ce-latest-x86_64-setup.exe)
* Mac版
  * [Intel處理器](https://dbeaver.io/files/dbeaver-ce-latest-macos-x86_64.dmg)
  * [M系列處理器](https://dbeaver.io/files/dbeaver-ce-latest-macos-aarch64.dmg)

## 開始使用

### 安裝套件

>執行前請確保已經安裝了Node.js

打開終端機並輸入以下指令
```
$ npm i
```

### 首次在本機開啟資料庫並執行遷移

> 請確保Docker Desktop已經正常啟動，並能夠看到容器頁面(Containers)

打開終端機並輸入以下指令，程式將自動啟動資料庫，並運行遷移
```
$ npm run start
```

啟動後，請檢查Docker Desktop程式界面中裡是否新增db-migrate-startkit的容器堆疊，該堆疊裡了有兩個容器：
* db_migrate-1：執行遷移檔案的容器，執行後會自動關閉（狀態（STATUS）為Exited）。請務必進入檢查查看遷移的執行結果，確保遷移執行成功。
* postgres-1：資料庫容器，狀態應為Running

### 重新啟動資料庫
```
$ npm run restart
```
### 關閉資料庫
```
$ npm run stop
```

### 關閉資料庫並清除資料
```
$ npm run clean
```
