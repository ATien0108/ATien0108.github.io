---
title: "First Cloud Journey"
date: 2025-07-03
weight: 1
chapter: false
---

# Xây dựng ứng dụng quản lý dự án Nextjs và triển khai trên AWS

## 📝 TỔNG QUAN ĐỀ TÀI

**Tên đề tài**:  
**Xây dựng Ứng dụng Quản lý Dự án (Project Management App) bằng Next.js và triển khai trên nền tảng AWS**

**Mục tiêu đề tài**:  
Phát triển một ứng dụng web hiện đại cho phép quản lý dự án, nhiệm vụ, và thành viên nhóm hiệu quả. Hệ thống hỗ trợ xác thực người dùng, phân quyền truy cập, theo dõi tiến độ theo thời gian thực, và trực quan hóa dữ liệu bằng biểu đồ và bảng dữ liệu.

**Công nghệ sử dụng**:

- **Frontend**: Next.js, Tailwind CSS, Material UI Data Grid, Redux Toolkit, Recharts, React DnD
- **Backend**: Node.js, Express, Prisma ORM, PostgreSQL
- **Dịch vụ AWS**: Cognito, EC2, RDS, S3, Lambda, API Gateway

**Kiến trúc hệ thống**:  
Ứng dụng được triển khai theo mô hình **Client – Server – Cloud**, trong đó:

- Giao diện người dùng xây dựng bằng **Next.js**, giao tiếp với backend qua API RESTful.
- Backend xử lý nghiệp vụ và xác thực thông qua **Node.js + Express**, triển khai trên **Amazon EC2**.
- Dữ liệu được lưu trữ và truy vấn hiệu quả bằng **PostgreSQL trên Amazon RDS**, kết nối qua **Prisma ORM**.
- Các tính năng như xác thực người dùng (Cognito), lưu trữ file (S3), xử lý không máy chủ (Lambda), và quản lý endpoint (API Gateway) giúp hệ thống linh hoạt, bảo mật và dễ mở rộng.

**Kết quả mong đợi**:  
Xây dựng thành công một ứng dụng dashboard quản lý dự án đầy đủ chức năng, có giao diện hiện đại, trải nghiệm người dùng tốt và sẵn sàng triển khai thực tế trên hạ tầng AWS.
