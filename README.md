
#  🌟 星星窯業購物網 - Java Swing 桌面應用程式

這是一個以 Java Swing 製作的桌面 GUI 購物管理系統，支援會員登入註冊、商品 CRUD、訂單管理，並依據身分切換後台與前台畫面，適合中小型零售商管理進銷存。

## 🧩 功能介紹

### 🔐 登入系統（Login.java）
- 使用者輸入帳號、密碼及圖形驗證碼（CAPTCHA）
- 驗證後自動依角色導向不同主畫面
  - 管理者 → BossMain
  - 一般會員 → SaleMain
- 登入成功將資訊儲存至 `member.txt`

### 👤 會員模組
- 註冊會員：透過 `MemberAdd.java` 新增會員資料（姓名、帳號、密碼、電話等）
- 登入驗證：透過 `MemberServiceImpl` 連接 DAO 查詢帳密
- 身分分流：登入後依角色切換功能畫面

### 📦 商品模組（限管理者）
- 使用 `ProductList.java` 可執行以下操作：
  - 新增商品
  - 修改商品
  - 刪除商品
  - 顯示商品清單（表格）
- 所有商品資料由 `ProductServiceImpl` 及 `ProductDaoImpl` 實作操作資料庫

### 🧾 訂單模組（一般會員）
- 使用者可透過下列介面完成購物流程：
  - `SaleMain.java`：前台主畫面
  - `SaleAdd.java`：建立新訂單
  - `SaleCheck.java`：查詢訂單
  - `SaleUpdate.java`：更新訂單資訊（如退貨）
```markdown
```
## 🗂️ 專案目錄結構

```
src/
├── controller/
│   ├── Login.java                     ← 登入主畫面（驗證碼 / 登入分流）
│   ├── boss/
│   │   ├── BossMain.java              ← 管理主頁
│   │   └── ProductList.java           ← 商品管理（CRUD）
│   ├── member/
│   │   └── MemberAdd.java             ← 註冊畫面
│   └── sale/
│       ├── SaleMain.java              ← 使用者主頁
│       ├── SaleAdd.java               ← 新增訂單
│       ├── SaleCheck.java             ← 查詢訂單
│       └── SaleUpdate.java            ← 更新訂單
│
├── dao/
│   ├── Productdao.java
│   ├── Memberdao.java
│   └── Saledao.java
│
├── dao/impl/
│   ├── ProductDaoImpl.java
│   ├── MemberDaoImpl.java
│   └── SaleDaoImpl.java              ← JDBC 資料操作實作
│
├── model/
│   ├── Member.java
│   ├── Product.java
│   └── Sale.java
│
├── service/
│   ├── ProductService.java
│   ├── MemberService.java
│   └── SaleService.java
│
├── service/impl/
│   ├── ProductServiceImpl.java
│   ├── MemberServiceImpl.java
│   └── SaleServiceImpl.java
│
├── util/
│   ├── Tool.java                     ← 工具類：驗證碼、序列化等
│   ├── ImagePanel.java               ← 背景圖片處理
│   └── Dbconnection.java             ← JDBC 連線管理
│
├── member.txt                        ← 已登入者暫存資料（序列化）
└── sale.txt                          ← 暫存訂單資料
```


## 🚀 執行方式
1. 開啟 IDE（如 IntelliJ / Eclipse）
2. 設定好資料庫連線（`Dbconnection.java`）
3. 執行 `Login.java` 即可啟動系統

## 👨‍💻 作者
- 開發者：ruby
- 版本：1.0
- 聯絡方式：請透過 GitHub 聯絡我
```
