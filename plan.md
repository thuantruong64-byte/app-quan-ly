# 🚀 **TỔNG QUAN LỘ TRÌNH (HỌC + XÂY WEBSITE)**

Bạn sẽ đi qua **8 giai đoạn**, mỗi giai đoạn có:

✔ Mục tiêu
✔ Kiến thức cần học + giải thích
✔ Bài tập thực hành
✔ Kết quả đạt được

---

# 🟦 **GIAI ĐOẠN 1 — NỀN TẢNG WEB CƠ BẢN (1–2 tuần)**

## 🎯 **Mục tiêu**

* Biết cách tạo một trang web đơn giản.
* Hiểu các khái niệm nền tảng mà bất kỳ lập trình viên web nào cũng phải biết.

---

## 📘 **1. HTML – Khung của website**

### ✔ Khái niệm:

HTML là ngôn ngữ để **tạo cấu trúc** cho trang web (giống khung xương ngôi nhà).

### ✔ Cần học:

* Thẻ `<div>`
* Thẻ `<form>`, `<input>`, `<button>`
* Bảng `<table>`
* Thuộc tính id, class

### ✔ Code mẫu:

```html
<form id="accountForm">
  <input type="text" id="platform" placeholder="Nền tảng (Facebook)">
  <input type="text" id="username" placeholder="Tên tài khoản">
  <button type="submit">Lưu</button>
</form>
```

---

## 📘 **2. CSS – Giao diện của website**

### ✔ Khái niệm:

CSS giúp **trang web đẹp**, giống như sơn tường + trang trí nội thất.

### ✔ Cần học:

* Màu sắc
* Flexbox (cách căn chỉnh bố cục)
* Khoảng cách (margin/padding)
* Font chữ

### ✔ Code mẫu:

```css
form {
  display: flex;
  gap: 10px;
}
input {
  padding: 8px;
}
```

---

## 📘 **3. JavaScript cơ bản – điều khiển website**

### ✔ Khái niệm:

JavaScript giúp website **có logic**, có tương tác, lưu dữ liệu.

### ✔ Cần học:

* Biến (let, const)
* Hàm (function)
* Object & Array
* DOM (lấy và hiển thị dữ liệu HTML)
* LocalStorage (lưu tạm)

### ✔ Code mẫu:

```javascript
document.getElementById("accountForm").addEventListener("submit", function(e) {
  e.preventDefault();
  alert("Bạn vừa nhấn nút!");
});
```

---

## 🎯 **Kết quả đạt được sau giai đoạn 1**

✔ Biết tạo trang web cơ bản
✔ Biết thêm CSS làm đẹp
✔ Biết viết JavaScript đơn giản
✔ Biết gắn form input với code

---

# 🟩 **GIAI ĐOẠN 2 — LÀM WEBSITE OFFLINE (1 tuần)**

Mục tiêu: **Tập trung vào frontend – không backend**.

---

## 🎯 **Mục tiêu**

* Tạo phiên bản đầu tiên của website quản lý tài khoản.
* Lưu dữ liệu bằng LocalStorage (trên trình duyệt).

---

## 📘 Nội dung cần làm

### 1. Form thêm tài khoản

### 2. Hiển thị danh sách

### 3. Sửa tài khoản

### 4. Xóa tài khoản

### 5. Lưu vào LocalStorage

---

## 🎉 Code mẫu – lưu dữ liệu địa phương

```javascript
let list = JSON.parse(localStorage.getItem("accounts")) || [];

function addAccount() {
  const acc = {
    platform: platform.value,
    username: username.value,
  };
  list.push(acc);

  localStorage.setItem("accounts", JSON.stringify(list));
}
```

---

## 🎯 Kết quả đạt được

✔ Có thể tự build website offline hoàn chỉnh
✔ Hiểu cách dữ liệu chạy trong frontend
✔ Hiểu cấu trúc dữ liệu (object, array)

---

# 🟥 **GIAI ĐOẠN 3 — HỌC BACKEND (2 tuần)**

Backend là “phần sau” của website, xử lý dữ liệu và API.

---

## 🎯 **Mục tiêu**

* Hiểu backend hoạt động như thế nào
* Tự tạo server
* Tạo API (giao tiếp giữa frontend ↔ backend)

---

## 📘 Công nghệ dùng: NodeJS + Express

### ✔ Khái niệm:

* **NodeJS**: chạy JavaScript phía server
* **ExpressJS**: framework giúp tạo API nhanh hơn

---

## 📘 Kiến thức cần học

* Cách tạo server
* Route (đường dẫn API)
* Request & Response
* Middleware
* JSON

---

## 🎉 Code mẫu – Tạo API đơn giản

```javascript
const express = require("express");
const app = express();

app.use(express.json());

app.get("/", (req, res) => {
  res.send("API OK");
});

app.listen(5000, () => console.log("Server chạy tại 5000"));
```

---

## 🎯 Kết quả đạt được

✔ Biết tạo server
✔ Biết API là gì và hoạt động thế nào
✔ Biết gửi – nhận dữ liệu JSON

---

# 🟧 **GIAI ĐOẠN 4 — DATABASE (1 tuần)**

Bạn sẽ học cách lưu dữ liệu thật.

---

## 🎯 Mục tiêu

* Hiểu database là gì
* Lưu dữ liệu tài khoản thật vào DB

---

## 📘 Chọn: MongoDB (dễ nhất cho người mới)

### ✔ Khái niệm:

* Lưu dạng JSON → cực dễ
* Dùng công cụ **Mongoose** để thao tác

---

## 🎉 Code mẫu — Tạo model

```javascript
const mongoose = require("mongoose");

const AccountSchema = new mongoose.Schema({
  platform: String,
  username: String,
  email: String
});

module.exports = mongoose.model("Account", AccountSchema);
```

---

## 🎯 Kết quả đạt được

✔ Biết thao tác database
✔ Biết tạo bảng (schema)
✔ Biết lưu dữ liệu thực

---

# 🟪 **GIAI ĐOẠN 5 — API FULL CRUD (1 tuần)**

Bạn sẽ tạo đủ tính năng backend:

| Chức năng     | API    |
| ------------- | ------ |
| Xem danh sách | GET    |
| Thêm          | POST   |
| Sửa           | PUT    |
| Xóa           | DELETE |

---

## 🎉 Code mẫu – API thêm tài khoản

```javascript
router.post("/", async (req, res) => {
  const acc = await Account.create(req.body);
  res.json(acc);
});
```

---

## 🎯 Kết quả đạt được

✔ Backend hoàn chỉnh
✔ Dữ liệu lưu vào MongoDB
✔ Hiểu sâu luồng xử lý dữ liệu

---

# 🟫 **GIAI ĐOẠN 6 — KẾT NỐI FRONTEND ↔ BACKEND (1 tuần)**

---

## 🎯 Mục tiêu

* Gọi API từ frontend
* Hiển thị dữ liệu từ server

---

## 🎉 Code mẫu – Lấy danh sách từ server

```javascript
async function load() {
  const res = await fetch("http://localhost:5000/accounts");
  const data = await res.json();
  console.log(data);
}
```

---

## 🎯 Kết quả đạt được

✔ Website bắt đầu chạy thật
✔ Dữ liệu có thể lưu – sửa – xóa trên server
✔ Bạn hiểu cách Frontend ↔ Backend giao tiếp

---

# 🟦 **GIAI ĐOẠN 7 — HOÀN THIỆN WEBSITE (1 tuần)**

---

## 🎯 Mục tiêu

* Hoàn thiện trang đăng nhập
* Hoàn thiện UI
* Validate dữ liệu
* Mã hóa password (nếu có)

---

## 📘 Những thứ cần thêm

* Login
* Mã hóa AES (CryptoJS)
* Responsive UI

---

## 🎯 Kết quả đạt được

✔ Website hoàn chỉnh như một sản phẩm thật
✔ Có thể cho người khác dùng

---

# 🟩 **GIAI ĐOẠN 8 — TRIỂN KHAI (1–2 ngày)**

---

## 🎯 Mục tiêu

* Đưa website lên Internet
* Có thể truy cập từ mọi nơi

---

## 📘 Công cụ

* Frontend → Vercel
* Backend → Render
* Database → MongoDB Atlas

---

## 🎯 Kết quả đạt được

✔ Website online
✔ Bạn hoàn thiện 1 dự án fullstack thực tế

---

# 🎉 **BẢNG TỔNG HỢP LỘ TRÌNH (8 tuần)**

| Tuần | Giai đoạn       | Kết quả                      |
| ---- | --------------- | ---------------------------- |
| 1–2  | Nền tảng Web    | Biết HTML – CSS – JS         |
| 3    | Website offline | Quản lý tài khoản chạy local |
| 4–5  | Backend         | Biết API + server            |
| 6    | Database        | Lưu dữ liệu thật             |
| 7    | Fullstack       | Website hoàn chỉnh           |
| 8    | Deploy          | Website online               |

---

# 💬 Bạn muốn bước tiếp theo là gì?

Tôi có thể giúp bạn:

1️⃣ Vẽ sơ đồ kiến trúc hệ thống
2️⃣ Viết **full code website offline**
3️⃣ Viết **full backend NodeJS + MongoDB**
4️⃣ Hướng dẫn bạn học theo ngày (Daily plan)

Bạn muốn chọn mục nào?
