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


### 5. Tạo tài khoản và phân quyền người dùng
Đây là kỹ năng cốt lõi mà bất kỳ IT Support nào cũng cần thành thạo — cấp tài khoản đúng chuẩn và kiểm soát chặt chẽ quyền truy cập dữ liệu, tránh rủi ro bảo mật khi bàn giao máy cho nhân viên mới:
- Tạo tài khoản người dùng mới trong Computer Management, đặt mật khẩu và cấu hình yêu cầu đổi mật khẩu ở lần đăng nhập đầu tiên — đảm bảo tuân thủ quy trình bảo mật cơ bản
- Kiểm tra thực tế bằng cách đăng nhập lại với tài khoản vừa tạo, xác nhận hệ thống hoạt động đúng như thiết kế
- Thiết lập phân quyền NTFS cho thư mục dùng chung, chỉ cấp quyền Read & Execute — giới hạn đúng mức cần thiết, không cho phép chỉnh sửa/xóa ngoài ý muốn
- Xử lý tình huống thực tế phức tạp hơn: một thư mục có sẵn nhiều quyền kế thừa từ thư mục cha, cần chủ động ngắt kế thừa (Block Inheritance) để chỉ giữ lại đúng những quyền cần thiết, đảm bảo không ai ngoài phạm vi được phép vẫn truy cập được

![Bước 1](./05-tao-tai-khoan-va-phan-quyen/user1.png)
*Mở Computer Management để quản lý tài khoản người dùng*

![Bước 2](./05-tao-tai-khoan-va-phan-quyen/user2.png)
*Khởi tạo hộp thoại New User*

![Bước 3](./05-tao-tai-khoan-va-phan-quyen/user3.png)
*Điền thông tin tài khoản, đặt mật khẩu và yêu cầu đổi mật khẩu lần đầu đăng nhập*

![Bước 4](./05-tao-tai-khoan-va-phan-quyen/user4.png)
*Tài khoản "Nhanvien1" đã được tạo thành công trong hệ thống*

![Bước 5](./05-tao-tai-khoan-va-phan-quyen/user5.png)
*Kiểm tra thực tế: đăng nhập lần đầu bằng tài khoản vừa tạo*

![Bước 6](./05-tao-tai-khoan-va-phan-quyen/user6.png)
*Kiểm tra quyền hạn ban đầu của thư mục dùng chung*

![Bước 7](./05-tao-tai-khoan-va-phan-quyen/user7.png)
*Tìm và thêm chính xác tài khoản vào danh sách phân quyền*

![Bước 8](./05-tao-tai-khoan-va-phan-quyen/user8.png)
*Cấp quyền Read & Execute — giới hạn đúng mức, không cho phép chỉnh sửa*

![Bước 9](./05-tao-tai-khoan-va-phan-quyen/user9.png)
*Xác minh quyền truy cập ứng dụng bằng tài khoản vừa phân quyền*

![Bước 10](./05-tao-tai-khoan-va-phan-quyen/user10.png)
*Kiểm tra lại màn hình đăng nhập, đảm bảo tài khoản hoạt động ổn định*

![Bước 11](./05-tao-tai-khoan-va-phan-quyen/user11.png)
*Xác nhận toàn bộ quy trình đăng nhập diễn ra chính xác*

![Bước 12](./05-tao-tai-khoan-va-phan-quyen/user12.png)
*Phát hiện thư mục Public Documents có nhiều quyền kế thừa phức tạp cần xử lý*

![Bước 13](./05-tao-tai-khoan-va-phan-quyen/user13.png)
*Chủ động ngắt kế thừa quyền (Block Inheritance) để kiểm soát chính xác*

![Bước 14](./05-tao-tai-khoan-va-phan-quyen/user14.png)
*Danh sách quyền sau khi xử lý — chỉ giữ lại đúng những gì cần thiết*

![Bước 15](./05-tao-tai-khoan-va-phan-quyen/user15.png)
*Kiểm tra lại giao diện và quyền truy cập sau khi cấu hình*

![Bước 16](./05-tao-tai-khoan-va-phan-quyen/user16.png)
*Xác minh kết quả phân quyền qua File Explorer*

![Bước 17](./05-tao-tai-khoan-va-phan-quyen/user17.png)
*Xác nhận quyền quản trị (UAC) khi thực hiện thay đổi hệ thống*




## Kỹ năng đạt được
- Triển khai và cấu hình máy ảo Windows**: Cấu hình tài nguyên (RAM, CPU, ổ cứng) phù hợp với nhu cầu sử dụng, đảm bảo hệ thống vận hành ổn định
- Quản lý phân vùng ổ đĩa: Sử dụng Disk Management để tách ổ hệ thống và ổ dữ liệu, giảm rủi ro mất dữ liệu khi cần cài lại hệ điều hành
- Cấu hình và chẩn đoán mạng cơ bản: Xác minh kết nối mạng, địa chỉ IP, gateway bằng CMD (ipconfig), đảm bảo máy sẵn sàng kết nối trước khi bàn giao
- Cài đặt hệ điều hành và phần mềm văn phòng: Cài đặt Windows, Microsoft Office từ ISO, xử lý toàn bộ quy trình chuẩn bị máy cho người dùng
- Quản trị tài khoản người dùng và phân quyền NTFS: Tạo tài khoản, cấu hình phân quyền cơ bản và xử lý các tình huống phân quyền nâng cao (kế thừa quyền, bảo mật thư mục dùng chung)
- Giám sát hiệu năng hệ thống: Sử dụng Resource Monitor, DXDiag để theo dõi và chẩn đoán hiệu năng CPU/RAM/Disk, phát hiện sớm sự cố tiềm ẩn

---



