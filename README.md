# PHẦN MỀM TÍNH THUẾ THU NHẬP CÁ NHÂN

## 1. Giới thiệu dự án

Phần mềm **Tính Thuế Thu Nhập Cá Nhân** được xây dựng nhằm hỗ trợ doanh nghiệp quản lý thông tin nhân viên và tính toán thuế thu nhập cá nhân một cách nhanh chóng, chính xác. Hệ thống cung cấp các chức năng dành cho nhiều vai trò người dùng khác nhau như Nhân viên, Trưởng phòng và Kế toán.

Phần mềm cho phép:

* Đăng nhập theo từng vai trò.
* Xem thông tin nhân viên.
* Tính thuế thu nhập cá nhân theo quy định.
* Tính thử thuế dựa trên dữ liệu nhập vào.
* Xem thông tin thuế của nhân viên.
* Quản lý dữ liệu nhân viên và phòng ban.
* Thiết lập các mức giảm trừ gia cảnh.
* Kiểm thử tự động bằng Selenium và Mocha.

---

# 2. Công nghệ sử dụng

## Frontend

* HTML5
* CSS3
* JavaScript

## Thư viện và công cụ

* XLSX.js
* Selenium WebDriver
* Mocha
* Assert
* Node.js
* ChromeDriver

## Dữ liệu

* Excel (.xlsx)
* CSV (.csv)

---

# 3. Cấu trúc dự án

```text
KiemThu-main-main
│
├── css/
│   ├── style.css
│   └── styles.css
│
├── excel_data/
│   ├── data_tt.xlsx
│   ├── id.csv
│   └── id (Copy).csv
│
├── html/
│   ├── nhanvien.html
│   ├── truongphong.html
│   └── ketoan.html
│
├── js/
│   ├── nhanvien.js
│   ├── truongphong.js
│   ├── ketoan.js
│   ├── dangNhap.spec.js
│   └── giamTru.spec.js
│
└── index.html
```

---

# 4. Chức năng của hệ thống

## 4.1 Đăng nhập

Người dùng đăng nhập bằng:

* Tên đăng nhập
* Mật khẩu

Sau khi đăng nhập thành công:

* Nhân viên → Trang nhân viên.
* Trưởng phòng → Trang trưởng phòng.
* Kế toán → Trang kế toán.

---

## 4.2 Quản lý thông tin cá nhân

Hiển thị:

* Mã nhân viên
* Họ và tên
* Chức vụ
* Phòng ban
* Email
* Số điện thoại
* Lương
* Số người phụ thuộc

---

## 4.3 Tính thử thuế

Người dùng nhập:

* Thu nhập hàng tháng.
* Số người phụ thuộc.

Hệ thống tính:

```text
Thu nhập chịu thuế
= Lương - Giảm trừ bản thân - Giảm trừ người phụ thuộc
```

Sau đó áp dụng biểu thuế lũy tiến để tính số thuế phải nộp.

---

## 4.4 Tính thuế theo tháng

Chức năng:

* Tính thuế tháng hiện tại.
* Hiển thị kết quả thuế.
* Hiển thị số tiền phải nộp.

---

## 4.5 Quyết toán thuế năm

Hiển thị:

* Tổng thu nhập năm.
* Tổng số thuế phải nộp.
* Tổng số người phụ thuộc.

---

## 4.6 Xem thuế nhân viên

Kế toán có thể:

* Tìm kiếm nhân viên.
* Xem thông tin thuế.
* Xem thu nhập và số thuế phải nộp.

---

## 4.7 Thiết lập giảm trừ

Cho phép:

* Cập nhật số người phụ thuộc.
* Cập nhật thông tin giảm trừ gia cảnh.

---

## 4.8 Quản lý nhân viên

* Xem danh sách nhân viên.
* Quản lý dữ liệu nhân viên.

---

## 4.9 Quản lý phòng ban

* Xem danh sách phòng ban.
* Quản lý thông tin phòng ban.

---

## 4.10 Đăng xuất

* Xóa phiên làm việc.
* Quay lại trang đăng nhập.

---

# 5. Hướng dẫn cài đặt

## Bước 1: Cài đặt Node.js

Tải Node.js tại:

https://nodejs.org

Kiểm tra cài đặt:

```bash
node -v
npm -v
```

---

## Bước 2: Giải nén dự án

Giải nén file:

```text
KiemThu-main-main.zip
```

Mở thư mục dự án bằng Visual Studio Code.

---

## Bước 3: Cài đặt các thư viện

Mở Terminal và chạy:

```bash
npm install
```

Hoặc:

```bash
npm install selenium-webdriver
npm install mocha
npm install chromedriver
npm install geckodriver
npm install xlsx
npm install assert
```

Kiểm tra:

```bash
npm list
```

---

# 6. Hướng dẫn chạy chương trình

## Cách 1: Chạy bằng Live Server

Bước 1:

Mở thư mục dự án bằng Visual Studio Code.

Bước 2:

Cài Extension:

```text
Live Server
```

Bước 3:

Mở file:

```text
index.html
```

Bước 4:

Nhấn chuột phải:

```text
Open with Live Server
```

Trình duyệt sẽ mở:

```text
http://127.0.0.1:5500/index.html
```

---

## Cách 2: Mở trực tiếp

Nhấp đúp:

```text
index.html
```

hoặc:

```text
file:///.../index.html
```

Khuyến nghị sử dụng **Live Server** để tránh lỗi đọc file Excel và CSV.

---

# 7. Hướng dẫn sử dụng

## Bước 1

Khởi động chương trình.

## Bước 2

Đăng nhập bằng tài khoản.

Ví dụ:

| Vai trò      | Tài khoản | Mật khẩu |
| ------------ | --------- | -------- |
| Nhân viên    | 20212001  | 1234     |
| Trưởng phòng | 20212002  | 1234     |
| Kế toán      | 20212003  | 1234     |

(Có thể thay đổi theo dữ liệu trong file CSV.)

## Bước 3

Chọn chức năng:

* Xem thông tin.
* Tính thử thuế.
* Tính thuế tháng.
* Quyết toán năm.
* Quản lý nhân viên.
* Quản lý phòng ban.

---

# 8. Quy trình kiểm thử

## 8.1 Mục tiêu

* Kiểm tra tính đúng đắn của chức năng.
* Phát hiện lỗi.
* Đảm bảo hệ thống hoạt động ổn định.

---

## 8.2 Phương pháp kiểm thử

### Kiểm thử hộp đen

Kiểm tra:

* Dữ liệu đầu vào.
* Kết quả đầu ra.

### Kiểm thử chức năng

Kiểm tra:

* Đăng nhập.
* Tính thuế.
* Giảm trừ.
* Quản lý nhân viên.

### Kiểm thử tự động

Sử dụng:

* Selenium WebDriver
* Mocha

---

## 8.3 Test Case

### TC01 – Đăng nhập thành công

Input:

```text
Username: 20212001
Password: 1234
```

Expected:

```text
Đăng nhập thành công.
```

---

### TC02 – Sai mật khẩu

Expected:

```text
Thông báo đăng nhập thất bại.
```

---

### TC03 – Bỏ trống dữ liệu

Expected:

```text
Thông báo yêu cầu nhập dữ liệu.
```

---

### TC04 – Tính thử thuế

Input:

```text
Lương: 20.000.000
Người phụ thuộc: 2
```

Expected:

```text
Hiển thị số thuế chính xác.
```

---

# 9. Chạy kiểm thử tự động

## Chạy test đăng nhập

```bash
npx mocha js/dangNhap.spec.js
```

## Chạy test giảm trừ

```bash
npx mocha js/giamTru.spec.js
```

## Chạy tất cả các bài test

```bash
npx mocha js/*.spec.js
```

hoặc:

```bash
npm test
```

---

# 10. Kết quả mong đợi

Khi chạy thành công:

```text
✔ Đăng nhập thành công
✔ Kiểm tra giảm trừ thành công

2 passing (5s)
```

Nếu xuất hiện:

```text
1 failing
```

Cần kiểm tra:

* Đường dẫn file.
* ChromeDriver.
* Phiên bản Node.js.
* Các thư viện npm.

---

# 11. Dữ liệu kiểm thử

Nguồn dữ liệu:

```text
excel_data/data_tt.xlsx
excel_data/id.csv
```

Dữ liệu gồm:

* Mã nhân viên.
* Họ tên.
* Chức vụ.
* Phòng ban.
* Lương.
* Người phụ thuộc.

---

# 12. Hướng phát triển

* Kết nối cơ sở dữ liệu MySQL.
* Mã hóa mật khẩu.
* Xây dựng API.
* Phân quyền nâng cao.
* Xuất báo cáo PDF.
* Gửi email thông báo thuế.
* Phát triển phiên bản Web hoàn chỉnh.
