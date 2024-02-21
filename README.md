# Next.js 環境變數設置

## .env 檔案

可以分成 .env.local、.env.dev、.env.uat、.env.production 等等的檔案
變數命名規則：沒有特別的前墜，例如：

```
DB_HOST=dev
```

## 如何使用環境變數

```
process.env.DB_HOST
```

## 在 package.json 設定不同的環境

需先執行 npm install env-cmd，一個用來管理環境變數的工具

```bash
"dev": "next dev",
"uat": "env-cmd -f .env.uat next dev",
"prod": "env-cmd -f .env.production next dev",
"build": "next build",
"build:dev": "env-cmd -f .env.dev next build",
"build:uat": "env-cmd -f .env.uat next build",
"build:prod": "env-cmd -f .env.production next build",
"start": "next start",
```
