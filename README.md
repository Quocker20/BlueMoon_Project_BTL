# (BTL) Phần mềm Quản lý Chung cư BlueMoon (v1.0)

> **Tác giả:** Vũ Quốc Anh
> **MSSV:** [MSSV CỦA BẠN]
> **Lớp:** [LỚP CỦA BẠN]
> **Môn học:** Nhập môn Công nghệ phần mềm (Mã môn: [MÃ MÔN HỌC CỦA BẠN])

---

> **LƯU Ý QUAN TRỌNG: TÀI LIỆU DỰ ÁN**
> 
> Kho lưu trữ (Repository) này **chỉ chứa Mã nguồn (Source Code)** của ứng dụng.
> 
> Toàn bộ Tài liệu Dự án (bao gồm `Thư mục 01` đến `Thư mục 06`: Tuyên ngôn Dự án, WBS, SRS, Đặc tả Use Case, Thiết kế, Báo cáo...) được lưu trữ và quản lý tập trung tại đây:
> 
> ### ➡️ **[Toàn bộ Tài liệu Dự án BlueMoon (Google Drive)](https://drive.google.com/drive/folders/1XDtw1UxgtzvF0eWAdbl8XzQ4arjFJObt)**

---

## 1. 📝 Mô tả Dự án

Dự án này xây dựng một **ứng dụng Desktop (Java/MySQL)** nhằm tin học hóa quy trình nghiệp vụ tại Chung cư BlueMoon.

**Vấn đề (Problem):** Ban quản trị (BQT) hiện đang quản lý thu phí và thông tin dân cư bằng phương thức thủ công (sổ sách, Excel), dẫn đến tốn thời gian, rủi ro sai sót cao và khó khăn trong việc tra cứu, thống kê (As-Is Scenario).

**Giải pháp (Solution):** Phần mềm cung cấp một công cụ tập trung, an toàn và hiệu quả cho BQT để quản lý các nghiệp vụ cốt lõi, thay thế hoàn toàn quy trình thủ công.

## 2. 🛠️ Công nghệ Sử dụng (Tech Stack)

* **Ngôn ngữ:** Java (JDK 11+)
* **Nền tảng:** Desktop (Java Swing)
* **Cơ sở dữ liệu:** MySQL 8.0
* **Quản lý Dự án & Thư viện:** Apache Maven

## 3. 🎯 Tính năng Cốt lõi (Phạm vi v1.0)

Hệ thống được thiết kế cho người dùng là **Ban quản trị**. Các chức năng chính bao gồm:

* **E-01: Quản lý Thu phí & Tài chính**
    * (F-1.1) Cấu hình đơn giá (phí dịch vụ, phí quản lý).
    * (F-1.2) Tự động tính phí bắt buộc hàng tháng theo diện tích.
    * (F-1.3) Quản lý các đợt thu đóng góp tự nguyện (quỹ từ thiện).
    * (F-1.5) Ghi nhận thanh toán và theo dõi công nợ chi tiết.
* **E-02: Quản lý Cư dân**
    * (F-2.1) Quản lý thông tin Hộ khẩu (Thêm/Sửa/Xóa).
    * (F-2.2) Quản lý thông tin Nhân khẩu (thành viên trong hộ).
    * (F-2.3) Ghi nhận biến động (tạm trú, tạm vắng).
* **E-03: Báo cáo & Tra cứu**
    * (F-3.2) Thống kê nhanh công nợ, tổng thu.
    * (F-3.3) Tra cứu, trích xuất thông tin dân cư để báo cáo chính quyền.
* **E-04: Hệ thống**
    * (F-4.1) Đăng nhập bảo mật cho thành viên BQT.

## 4. 🚀 Hướng dẫn Cài đặt và Chạy (Demo)

Để chạy dự án này trên máy của bạn, vui lòng làm theo các bước sau:

### 4.1. Yêu cầu Môi trường

* **Java JDK:** Phiên bản 11 trở lên.
* **MySQL Server:** Phiên bản 8.0 trở lên (ví dụ: cài qua XAMPP hoặc MySQL Workbench).
* **Maven:** (Thường đã tích hợp sẵn trong VS Code hoặc IntelliJ).

### 4.2. Cài đặt Cơ sở dữ liệu

1.  Mở MySQL Workbench (hoặc phpMyAdmin).
2.  Tạo một cơ sở dữ liệu (schema) mới với tên: `bluemoon_db`
3.  Import file script SQL `database_script.sql` (bạn có thể tải file này từ link Google Drive ở đầu trang) để tạo các bảng và dữ liệu mẫu.
4.  **QUAN TRỌNG:** Cấu hình kết nối CSDL:
    * Mở file: `src/main/java/com/bluemoon/app/utils/DatabaseConnector.java`
    * Thay đổi `USERNAME` và `PASSWORD` cho phù hợp với cấu hình MySQL trên máy của bạn.

### 4.3. Chạy Ứng dụng

1.  Clone kho lưu trữ này về máy.
2.  Mở dự án (thư mục `bluemoon-desktop`) bằng VS Code hoặc IntelliJ.
3.  Đợi IDE (thông qua Maven) tự động tải về các thư viện (dependencies) đã khai báo trong `pom.xml` (bao gồm cả thư viện MySQL Connector).
4.  Tìm và chạy file `src/main/java/com/bluemoon/app/App.java` (file chứa hàm `public static void main(String[] args)`).
5.  Sử dụng tài khoản demo (nếu có):
    * **Username:** `admin`
    * **Password:** `123456`

## 5. 🗂️ Cấu trúc Thư mục Mã nguồn (MVC)

Dự án được tổ chức theo mô hình MVC (Model-View-Controller):

* `src/main/java/com/bluemoon/app/`
    * `models/`: Định nghĩa các đối tượng (POJO) như `HoKhau`, `NhanKhau`, `CongNo`.
    * `views/`: Chứa các file giao diện (JFrame, JPanel) như `FormLogin`, `FormMain`.
    * `controllers/`: Chứa logic nghiệp vụ, xử lý sự kiện như `LoginController`, `ThuPhiController`.
    * `utils/`: Chứa các lớp tiện ích, ví dụ `DatabaseConnector.java`.
    * `App.java`: File khởi chạy ứng dụng.
* `src/main/resources/`: Chứa icon, ảnh...
* `pom.xml`: File quản lý thư viện (Maven).