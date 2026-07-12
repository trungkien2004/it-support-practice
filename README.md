# IT Support - Windows VM Practice

Dự án thực hành thiết lập, cấu hình và quản trị máy ảo Windows 10 nhằm mô phỏng quy trình bàn giao máy tính cho nhân viên trong môi trường doanh nghiệp.

## Công cụ sử dụng
- VMware Workstation Pro 15.5
- Windows 10 x64 (Education/Professional)
- Microsoft Office 365

# IT Support - Windows VM Practice

Dự án thực hành thiết lập, cấu hình và quản trị máy ảo Windows 10 nhằm mô phỏng quy trình bàn giao máy tính cho nhân viên trong môi trường doanh nghiệp.

## Công cụ sử dụng
- VMware Workstation Pro 15.5
- Windows 10 x64 (Education/Professional)
- Microsoft Office 365

## Nội dung thực hành


### 1. Thiết lập máy ảo
- Triển khai một máy tính hoàn chỉnh từ đầu — mô phỏng đúng quy trình chuẩn bị máy mới cho nhân viên trong doanh nghiệp, từ khâu khởi tạo phần cứng ảo đến cài đặt hệ điều hành:
- Khởi tạo máy ảo trên VMware Workstation, lựa chọn cấu hình phù hợp với nhu cầu sử dụng thực tế
- Tính toán và phân bổ tài nguyên hợp lý: RAM 8GB, CPU 4 processor x 2 core, ổ cứng 256GB — đảm bảo máy vận hành ổn định, không lãng phí tài nguyên
- Cài đặt hệ điều hành Windows 10 x64 từ file ISO, theo dõi và xử lý toàn bộ quá trình cho tới khi máy sẵn sàng sử dụng

  ![Bước 1](./01-thiet-lap-may-ao/setup1.png)
*Khởi tạo máy ảo mới, chọn cấu hình Typical*

![Bước 2](./01-thiet-lap-may-ao/setup2.png)
*Gắn file ISO Windows 10 x64 để cài đặt hệ điều hành*

![Bước 3](./01-thiet-lap-may-ao/setup3.png)
*Thiết lập dung lượng ổ đĩa 256GB*

![Bước 4](./01-thiet-lap-may-ao/setup4.png)
*Cấu hình RAM 8GB*

![Bước 5](./01-thiet-lap-may-ao/setup5.png)
*Cấu hình CPU 4 processor x 2 core*

Sau khi hoàn tất cấu hình phần cứng, tiến hành cài đặt và theo dõi toàn bộ quá trình thiết lập hệ điều hành:

![Bước 6](./01-thiet-lap-may-ao/setup6.png)
*Windows đang được cài đặt*

![Bước 7](./01-thiet-lap-may-ao/setup7.png)
*Hệ thống chuẩn bị khởi động lần đầu*

![Bước 8](./01-thiet-lap-may-ao/setup8.png)
*Setup Windows đang khởi tạo*

![Bước 9](./01-thiet-lap-may-ao/setup9.png)
*Hoàn tất — máy ảo sẵn sàng bàn giao và sử dụng*


### 2. Chia phân vùng ổ cứng
Ngay sau khi cài đặt xong Windows, tiến hành chia ổ đĩa để tách ổ hệ thống (C) và ổ lưu trữ dữ liệu (E),tránh mất dữ liệu khi cần cài lại hệ điều hành sau này.
Dùng Disk Management để thu nhỏ (Shrink) một phần dung lượng ổ C.
Tạo vùng trống, sau đó tạo phân vùng mới, format NTFS và gán ký tự ổ đĩa.


![Bước 1](./02-chia-phan-vung-o-dia/Partition1.png)
*Mở công cụ Disk Management*

![Bước 2](./02-chia-phan-vung-o-dia/Partition2.png)
*Shrink Volume để tạo vùng trống từ ổ C*

![Bước 3](./02-chia-phan-vung-o-dia/Partition3.png)
*Tạo phân vùng mới (New Simple Volume)*

![Bước 4](./02-chia-phan-vung-o-dia/Partition4.png)
*Thiết lập dung lượng phân vùng mới*

![Bước 5](./02-chia-phan-vung-o-dia/Partition5.png)
*Gán ký tự ổ đĩa (E)*

![Bước 6](./02-chia-phan-vung-o-dia/Partition6.png)
*Format phân vùng theo chuẩn NTFS*

![Bước 7](./02-chia-phan-vung-o-dia/Partition7.png)
*Kết quả: ổ C (hệ thống) và ổ E (dữ liệu) đã tách biệt hoàn chỉnh*


### 3. Kiểm tra hệ thống và giám sát hiệu năng
- Kiểm tra thông tin phần cứng và hệ điều hành bằng công cụ DXDiag
- Xác minh cấu hình mạng (địa chỉ IP, gateway) bằng lệnh `ipconfig` trong Command Prompt
- Giám sát hiệu năng ổ đĩa (Disk) và bộ nhớ (Memory) bằng Resource Monitor, giúp phát hiện sớm nếu có tiến trình chiếm dụng tài nguyên bất thường

![Kiểm tra thông tin hệ thống](./03-kiem-tra-ht-mang/dxdiag01.png)
*Kiểm tra thông tin phần cứng và hệ điều hành bằng DXDiag*

![Kiểm tra cấu hình mạng](./03-kiem-tra-ht-mang/ipconfig2.png)
*Xác minh địa chỉ IP, gateway bằng lệnh ipconfig*

![Giám sát bộ nhớ RAM](./03-kiem-tra-ht-mang/RAM3.png)
*Giám sát hiệu năng bộ nhớ (Memory) qua Resource Monitor*

![Giám sát ổ đĩa](./03-kiem-tra-ht-mang/SSD4.png)
*Giám sát hiệu năng ổ đĩa (Disk) qua Resource Monitor*
Bạn dán đè đúng 3 mục này vào README (giữ nguyên mục 4, 5 đã có), rồi Commit changes là hoàn tất toàn bộ.Cette conversation contient 88 images sur 100 (pages PDF incluses). Envisagez de démarrer une nouvelle conversa


### 4. Cài đặt Microsoft Office
Thực hiện quy trình chuẩn bị phần mềm văn phòng cho máy tính trước khi bàn giao — một trong những tác vụ phổ biến nhất của IT Support khi setup máy mới cho nhân viên:
- Gắn file ISO Office vào ổ đĩa ảo (CD/DVD) của máy tính
- Kiểm tra và xác nhận ổ đĩa đã nhận diện đúng file cài đặt
- Chạy file Setup, giám sát quá trình tải và cài đặt bộ ứng dụng Word, Excel, PowerPoint, Outlook, Teams...
- Đảm bảo Office được cài đặt hoàn chỉnh, sẵn sàng sử dụng ngay khi bàn giao cho người dùng

![Gắn ISO Office vào máy ảo](./04-cai-dat-office/office1.png)
 *Cấu hình VM Settings, gắn file ISO Office vào ổ đĩa ảo*

![Xác nhận ổ đĩa nhận file](./04-cai-dat-office/office2.png)
 *Ổ đĩa DVD đã nhận diện file cài đặt*

![Kiểm tra file cài đặt](./04-cai-dat-office/office3.png)
 *Danh sách file cài đặt trên ổ đĩa (Setup, Office)*

![Office đang cài đặt](./04-cai-dat-office/office4.png)
 *Bộ ứng dụng Word, Excel, PowerPoint... đang được tải và cài đặt*


## Kỹ năng đạt được
- Triển khai và cấu hình máy ảo Windows
- Cài đặt hệ điều hành, phần mềm văn phòng
- Cấu hình và chẩn đoán mạng cơ bản
- Quản trị tài khoản người dùng và phân quyền NTFS
- Quản lý phân vùng ổ đĩa
- Giám sát hiệu năng hệ thống

---
*Tác giả: Phạm Trung Kiên — [github.com/trungkien2004](https://github.com/trungkien2004)*


