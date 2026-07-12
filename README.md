# IT Support — Windows VM Practice

Dự án thực hành thiết lập, cấu hình và quản trị máy ảo Windows 10, mô phỏng đầy đủ quy trình bàn giao máy tính cho nhân viên trong môi trường doanh nghiệp thực tế — từ khởi tạo phần cứng ảo, cài đặt hệ điều hành, đến quản trị tài khoản và phân quyền bảo mật.

## Công cụ sử dụng
- VMware Workstation Pro 15.5
- Windows 10 x64 (Education/Professional)
- Microsoft Office 365

## Nội dung thực hành

### 1. Thiết lập máy ảo

Triển khai một máy tính hoàn chỉnh từ đầu, mô phỏng đúng quy trình chuẩn bị máy mới cho nhân viên: khởi tạo phần cứng ảo, tính toán tài nguyên hợp lý và cài đặt hệ điều hành.

- Khởi tạo máy ảo trên VMware Workstation, lựa chọn cấu hình phù hợp với nhu cầu sử dụng thực tế
- Phân bổ tài nguyên: RAM 8GB, CPU 4 processor x 2 core, ổ cứng 256GB — cân đối giữa hiệu năng và tối ưu chi phí tài nguyên
- Cài đặt Windows 10 x64 từ file ISO, theo dõi và xử lý toàn bộ quá trình cho đến khi máy sẵn sàng bàn giao

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

![Bước 6](./01-thiet-lap-may-ao/setup6.png)
*Windows đang được cài đặt*

![Bước 7](./01-thiet-lap-may-ao/setup7.png)
*Hệ thống chuẩn bị khởi động lần đầu*

![Bước 8](./01-thiet-lap-may-ao/setup8.png)
*Setup Windows đang khởi tạo*

![Bước 9](./01-thiet-lap-may-ao/setup9.png)
*Hoàn tất — máy ảo sẵn sàng bàn giao và sử dụng*

### 2. Chia phân vùng ổ cứng

Sau khi cài đặt Windows, tiến hành tách ổ hệ thống (C) và ổ lưu trữ dữ liệu (E) — một thao tác quan trọng giúp bảo toàn dữ liệu người dùng khi cần cài lại hệ điều hành.

- Dùng Disk Management để thu nhỏ (Shrink) một phần dung lượng ổ C
- Tạo phân vùng mới từ vùng trống, format chuẩn NTFS và gán ký tự ổ đĩa

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
- Giám sát hiệu năng ổ đĩa và bộ nhớ bằng Resource Monitor, giúp phát hiện sớm tiến trình chiếm dụng tài nguyên bất thường

![Kiểm tra thông tin hệ thống](./03-kiem-tra-ht-mang/dxdiag01.png)
*Kiểm tra thông tin phần cứng và hệ điều hành bằng DXDiag*

![Kiểm tra cấu hình mạng](./03-kiem-tra-ht-mang/ipconfig2.png)
*Xác minh địa chỉ IP, gateway bằng lệnh ipconfig*

![Giám sát bộ nhớ RAM](./03-kiem-tra-ht-mang/RAM3.png)
*Giám sát hiệu năng bộ nhớ (Memory) qua Resource Monitor*

![Giám sát ổ đĩa](./03-kiem-tra-ht-mang/SSD4.png)
*Giám sát hiệu năng ổ đĩa (Disk) qua Resource Monitor*

### 4. Cài đặt Microsoft Office

Chuẩn bị phần mềm văn phòng cho máy tính trước khi bàn giao — một trong những tác vụ phổ biến nhất của IT Support khi setup máy mới cho nhân viên.

- Gắn file ISO Office vào ổ đĩa ảo, xác nhận hệ thống nhận diện đúng file cài đặt
- Chạy Setup, giám sát quá trình cài đặt bộ ứng dụng Word, Excel, PowerPoint, Outlook, Teams
- Đảm bảo Office được cài đặt hoàn chỉnh, sẵn sàng sử dụng ngay khi bàn giao

![Gắn ISO Office vào máy ảo](./04-cai-dat-office/office1.png)
*Cấu hình VM Settings, gắn file ISO Office vào ổ đĩa ảo*

![Xác nhận ổ đĩa nhận file](./04-cai-dat-office/office2.png)
*Ổ đĩa DVD đã nhận diện file cài đặt*

![Kiểm tra file cài đặt](./04-cai-dat-office/office3.png)
*Danh sách file cài đặt trên ổ đĩa (Setup, Office)*

![Office đang cài đặt](./04-cai-dat-office/office4.png)
*Bộ ứng dụng Word, Excel, PowerPoint... đang được tải và cài đặt*

### 5. Tạo tài khoản và phân quyền người dùng

Kỹ năng cốt lõi mà bất kỳ IT Support nào cũng cần thành thạo: cấp tài khoản đúng chuẩn và kiểm soát chặt chẽ quyền truy cập, hạn chế rủi ro bảo mật khi bàn giao máy cho nhân viên mới.

- Tạo tài khoản người dùng mới trong Computer Management, đặt mật khẩu và yêu cầu đổi mật khẩu ở lần đăng nhập đầu — tuân thủ quy trình bảo mật cơ bản
- Kiểm tra thực tế bằng cách đăng nhập lại với tài khoản vừa tạo, xác nhận hệ thống hoạt động đúng thiết kế
- Thiết lập phân quyền NTFS cho thư mục dùng chung, chỉ cấp quyền Read & Execute — giới hạn đúng mức cần thiết
- Xử lý tình huống nâng cao: ngắt kế thừa quyền (Block Inheritance) cho thư mục có nhiều quyền kế thừa phức tạp, đảm bảo chỉ đúng người được phép mới truy cập được

![Bước 1](./05-tao-tai-khoan-va-phan-quyen/user1.png)
*Mở Computer Management để quản lý tài khoản người dùng*

![Bước 2](./05-tao-tai-khoan-va-phan-quyen/user2.png)
*Khởi tạo hộp thoại New User*

![Bước 3](./05-tao-tai-khoan-va-phan-quyen/user3.png)
*Điền thông tin tài khoản, đặt mật khẩu và yêu cầu đổi mật khẩu lần đầu đăng nhập*

![Bước 4](./05-tao-tai-khoan-va-phan-quyen/user4.png)
*Tài khoản "Nhanvien1" đã được tạo thành công*

![Bước 5](./05-tao-tai-khoan-va-phan-quyen/user5.png)
*Kiểm tra thực tế: đăng nhập lần đầu bằng tài khoản vừa tạo*

![Bước 6](./05-tao-tai-khoan-va-phan-quyen/user6.png)
*Kiểm tra quyền hạn ban đầu của thư mục dùng chung*

![Bước 7](./05-tao-tai-khoan-va-phan-quyen/user7.png)
*Tìm và thêm tài khoản vào danh sách phân quyền*

![Bước 8](./05-tao-tai-khoan-va-phan-quyen/user8.png)
*Cấp quyền Read & Execute — giới hạn đúng mức, không cho phép chỉnh sửa*

![Bước 9](./05-tao-tai-khoan-va-phan-quyen/user9.png)
*Xác minh quyền truy cập bằng tài khoản vừa phân quyền*

![Bước 10](./05-tao-tai-khoan-va-phan-quyen/user10.png)
*Kiểm tra lại màn hình đăng nhập, đảm bảo tài khoản hoạt động ổn định*

![Bước 11](./05-tao-tai-khoan-va-phan-quyen/user11.png)
*Xác nhận toàn bộ quy trình đăng nhập diễn ra chính xác*

![Bước 12](./05-tao-tai-khoan-va-phan-quyen/user12.png)
*Phát hiện thư mục Public Documents có nhiều quyền kế thừa phức tạp cần xử lý*

![Bước 13](./05-tao-tai-khoan-va-phan-quyen/user13.png)
*Ngắt kế thừa quyền (Block Inheritance) để kiểm soát chính xác*

![Bước 14](./05-tao-tai-khoan-va-phan-quyen/user14.png)
*Danh sách quyền sau khi xử lý — chỉ giữ lại đúng những gì cần thiết*

![Bước 15](./05-tao-tai-khoan-va-phan-quyen/user15.png)
*Kiểm tra lại quyền truy cập sau khi cấu hình*

![Bước 16](./05-tao-tai-khoan-va-phan-quyen/user16.png)
*Xác minh kết quả phân quyền qua File Explorer*

![Bước 17](./05-tao-tai-khoan-va-phan-quyen/user17.png)
*Xác nhận quyền quản trị (UAC) khi thực hiện thay đổi hệ thống*

## Kỹ năng đạt được

- **Triển khai và cấu hình máy ảo Windows**: cấu hình tài nguyên (RAM, CPU, ổ cứng) phù hợp nhu cầu sử dụng, đảm bảo hệ thống vận hành ổn định
- **Quản lý phân vùng ổ đĩa**: tách ổ hệ thống và ổ dữ liệu, giảm rủi ro mất dữ liệu khi cần cài lại hệ điều hành
- **Cấu hình và chẩn đoán mạng cơ bản**: xác minh kết nối, địa chỉ IP, gateway bằng CMD, đảm bảo máy sẵn sàng kết nối trước khi bàn giao
- **Cài đặt hệ điều hành và phần mềm văn phòng**: xử lý toàn bộ quy trình chuẩn bị máy từ ISO cho đến khi sẵn sàng bàn giao
- **Quản trị tài khoản người dùng và phân quyền NTFS**: tạo tài khoản, cấu hình phân quyền cơ bản và xử lý tình huống nâng cao (kế thừa quyền, bảo mật thư mục dùng chung)
- **Giám sát hiệu năng hệ thống**: sử dụng Resource Monitor, DXDiag để theo dõi CPU/RAM/Disk, phát hiện sớm sự cố tiềm ẩn

---
*Dự án được thực hiện nhằm mô phỏng sát nhất quy trình công việc thực tế của một IT Support trong doanh nghiệp.*
