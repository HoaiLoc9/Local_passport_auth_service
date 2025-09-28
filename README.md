# 🔐 Local Passport Auth Service

## 📌 Giới thiệu
Dự án này minh họa cách sử dụng **Passport.js (LocalStrategy)** để thực hiện cơ chế đăng ký (Register) và đăng nhập (Login) với **Express.js + MongoDB**.  

Khác với cookie/session auth, Passport cung cấp middleware tiện lợi để xác thực user bằng `username/password`.

---

## ⚙️ Cài đặt & Chạy thử

### 1️⃣ Clone repo

git clone https://github.com/HoaiLoc9/local_passport_auth_service.git
cd local_passport_auth_service

## 2️⃣ Cài đặt dependencies
npm install

## 3️⃣ Chạy server
node app.js

### 🔑 Chức năng & Cách test với Postman
## 1. Register

Endpoint: POST http://localhost:3000/register
```bash
Body (JSON):
{
  "username": "admin",
  "password": "12345"
}
```
Kết quả: User mới được lưu trong MongoDB với password đã được hash.
![register](https://github.com/HoaiLoc9/Local_passport_auth_service/blob/main/public/results/register3.png?raw=true)

CheckMongo:
![register](https://github.com/HoaiLoc9/Local_passport_auth_service/blob/main/public/results/register3_checkdb.png?raw=true)


## 2. Login

Endpoint: POST http://localhost:3000/login
```bash
Body (JSON):

{
  "username": "admin",
  "password": "12345"
}
```

Kết quả: Passport kiểm tra thông tin user:

Nếu đúng → trả về "✅ Login successful".

Nếu sai → trả về "❌ Invalid username or password".
![register](https://github.com/HoaiLoc9/Local_passport_auth_service/blob/main/public/results/login3.png?raw=true)

CheckMongo
![register](https://github.com/HoaiLoc9/Local_passport_auth_service/blob/main/public/results/login3_checkdb.png?raw=true)

```bash
local_passport_auth_service/
│── app.js
│── config/passport.js
│── models/User.js      
│── routes/auth.js     
│── package.json
│── README.md
```
