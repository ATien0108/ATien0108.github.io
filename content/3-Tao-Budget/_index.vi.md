---
title: "Tạo Budget"
date: 2025-07-03

weight: 3
chapter: false
pre: " <b> 3. </b> "
---

## Tổng quan

Trong phần này, bạn sẽ học cách tạo AWS Budget sử dụng template có sẵn của AWS. AWS Budget là công cụ quan trọng giúp bạn theo dõi và kiểm soát chi phí AWS một cách hiệu quả.
Tạo Budget theo template

## Tạo Budget theo template

1. Truy cập vào **AWS Management Console**:

   - Mở **AWS Management Console**

   - Tìm và chọn dịch vụ **AWS Billing and Cost Management**

<p align="center">
<img src="/images/3/3.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Trong giao diện **AWS Billing and Cost Management**:

   - Chọn **Budgets** từ menu bên trái

   - Nhấn vào **Create a budget**

<p align="center">
<img src="/images/3/3.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Thiết lập cấu hình Budget:

   - Chọn **Use a template (simplified)** để sử dụng mẫu có sẵn

   - Trong phần **Templates**, chọn **Monthly cost budget**

<p align="center">
<img src="/images/3/3.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Nhập thông tin chi tiết cho Budget:

   - Đặt tên cho **Budget**

   - **Xác định số tiền** ngân sách hàng tháng

   - Thiết lập **ngưỡng cảnh báo**

   - Nhấn **Create budget** để hoàn tất

<p align="center">
<img src="/images/3/3.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. **Xác nhận Budget** đã được tạo thành công:

## Lợi ích của việc sử dụng AWS Budget Templates

**Information**: AWS Budget Templates giúp đơn giản hóa quá trình tạo ngân sách bằng cách cung cấp các cấu hình được định nghĩa trước cho các trường hợp sử dụng phổ biến.

**Pro Tip**: Sử dụng Monthly cost budget là lựa chọn tốt để bắt đầu, nhưng hãy cân nhắc tạo thêm các budget theo dịch vụ cụ thể khi hệ thống của bạn phát triển.

**Security Note**: Đảm bảo thiết lập quyền truy cập phù hợp cho AWS Budget để chỉ những người có thẩm quyền mới có thể chỉnh sửa hoặc xóa các budget đã tạo.

**Warning**: Các cảnh báo budget không tự động dừng tài nguyên hoặc ngăn chặn việc sử dụng dịch vụ khi vượt quá ngân sách. Hãy cân nhắc kết hợp với AWS Service Quotas hoặc IAM policies để kiểm soát việc sử dụng tài nguyên.
