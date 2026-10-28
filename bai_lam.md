# BÀI LÀM – HACKATHON 01

- **Mã đề:** 20
- **Họ tên:** Phạm Duy Quang
- **Lớp:** CNTT2
- **Link repository:** https://github.com/quangdev05/HN-KS26-CNTT2_Nhap-mon-CNTT_Hackathon01
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
gci -Force
mv "lich_lam_viec.txt" docs
mv "logo_salon_toc.png" media
cp "media/logo_salon_toc.png" backup
rm temp_289.tmp
cd logs
gci
cd ..
gci -R -Force

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiGK1\starter-kit\salon-toc-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026     13:40                backup
d-----        10/28/2026     13:35                data
d-----        10/28/2026     13:39                docs
d-----        10/28/2026     13:35                logs
d-----        10/28/2026     13:39                media
-a----        10/27/2026     01:32             67 .env
-a----        10/28/2026     13:40           2297 bai_lam.md
-a----        10/27/2026     01:32             22 temp_289.tmp


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiGK1\starter-kit\salon-toc-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026     01:32           6113 logo_salon_toc.png


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiGK1\starter-kit\salon-toc-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026     01:32           6103 hoa_don_salon_thang_11.xlsx


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiGK1\starter-kit\salon-toc-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026     01:32             62 lich_lam_viec.txt


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiGK1\starter-kit\salon-toc-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026     01:32           1032 salon.log


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiGK1\starter-kit\salon-toc-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026     01:32           6113 logo_salon_toc.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
gc logs/salon.log | sls "ERROR" > logs/daiy_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-11-28 09:53:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 09:57:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và _in nghiêng_
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
./auto_report.ps1

```

### Kết quả hiển thị

```text
Dang loc log ...
Hoan thanh!

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
gc logs/salon.log | sls "ERROR" | measure

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
Count    : 5

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs/tong_hop.txt
gc logs/salon.log | sls "WARNING" >> logs/tong_hop.txt
gc logs/salon.log | sls "ERROR" | measure | select -exp Count >> logs/tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===

2026-11-28 09:33:35 [WARNING] Anh kieu toc dung luong lon
2026-11-28 09:37:35 [WARNING] Lich toi thu sau sap kin
2026-11-28 10:01:35 [WARNING] Anh kieu toc dung luong lon
2026-11-28 10:09:35 [WARNING] Thoi gian phan hoi cham


5


```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_salon_thang_11.xlsx`, không cần ghi vào đây.
