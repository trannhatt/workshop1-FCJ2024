---
title: "Giới thiệu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Tổng quan kiến trúc

![Architecture Workshop 1](workshop1-FCJ2024/images/1-Introduce/fcj2024-ws1-architechture.png?featherlight=false&width=40pc)

#### Mô tả

1. Trong **VPC** sẽ có các public và private subnets subnet nằm trong 2 availability zones.
2. 1**Internet Gateway** được sử dụng để cho phép giao tiếp giữa các instances trong VPC và Internet.
3. Chúng ta sẽ sử dụng 2 **Availability Zones** để đảm bảo tính sẵn có cao và có khả năng chịu lỗi.
4. Các tài nguyên khác như Nat Gateway, Bastion Host và Application Load Balancer sẽ nằm trong **Public Subnets**.
5. Chúng ta sẽ đặt các máy chủ web và máy chủ cơ sở dữ liệu trong các **Private Subnets** để bảo vệ chúng.
6. **Nat Gateway** cho phép các instances trong private app subnets và private data subnets truy cập ra ngoài internet.
7. Chúng ta sẽ sử dụng cơ sở dữ liệu **MYSQL** và các **EC2 Instances** để host trang web.
8. **Application Load Balancer** được sử dụng để phân phối lưu lượng web qua **Auto Scaling Group** của các EC2 instances trong multiple AZs.
9. Chúng ta sẽ sử dụng **Auto Scaling Group** để làm cho trang web có tính sẵn sằn cao, có khả năng mở rộng, có thể chịu lỗi và có tính linh hoạt.
10. Chúng ta sẽ sử dụng **AWS S3** để lưu trữ mã nguồn ứng dụng web và tạo **IAM Role** để cấp quyền cho EC2 tải xuống mã nguồn từ AWS S3.
11. Chúng tôi sẽ cài đặt trang web của mình trên 1 **EC2 instance** trước, sau đó sử dụng instance này để tạo 1 **AMI**.
12. Dùng **AWS WAF (Web application firewall)** để bảo vệ ứng dụng, và sử dụng dịch vụ **Cloudfront** để tăng hiệu suất và giảm độ trể khi người dùng truy cập trang web.
13. Chúng ta có thể dùng **Route 53** để đăng ký tên miền của và tạo một bộ bản ghi.

#### Availability Zone

**Availability Zone** hay được viết tắt thành AZ là **một trung tâm dữ liệu con**, nằm bên trong Region và được xác định dựa treo vị trí địa lý. Bên trong AZ có thể có một hoặc nhiều subnet, nhưng một subnet chỉ có thể nằm trong duy nhất một AZ mà không thể mở rộng sang AZ khác.

#### Subnet

**Subnet** là một phân đoạn của **dải địa chỉ IP** mà bạn sử dụng khi **khởi tạo Amazon VPC**, cung cấp trực tiếp dải mạng hoạt động cho các tài nguyên AWS có thể chạy bên trong nó như **Amazon EC2, Amazon RDS (CSDL Quan hệ Amazon),...** Các subnet cũng được xác định thông qua **CIDR block** và bắt buộc các **CIDR của subnet** phải nằm trong **CIDR của VPC**.

Các subnet được chia thành các loại như **Public**, **Private**, hoặc **VPN-only**.

- **Public subnet** là subnet có route table (sẽ thảo luận sau) điều hướng lưu lượng truy cập bên trong subnet đi tới VPC IGW (cũng sẽ thảo luận sau)
- **Private subnet** thì ngược lại với Public subnet, nó không có route table điều hướng lưu lượng truy cập tới VPC IGW.
- **VPN-only subnet** là subnet mà có route table điều hướng lưu lượng truy cập tới VPG của Amazon VPC (sẽ thảo luận sau).

Bất kể loại mạng con nào, dải địa chỉ IP nội bộ của subnet luôn là private (nghĩa là từ bên ngoài Internet không thể kết nối trực tiếp tới các địa chỉ thuộc dải này).

#### Route Table

**Route Table** hay còn gọi là bảng định tuyến, cung cấp hướng dẫn định tuyến và được gán vào các Subnets.
Ví dụ khi bạn tạo VPC với lớp mạng 10.10.0.0/16, cùng 2 subnet 10.10.1.0/24,10.10.2.0/24 thì mỗi subnets mặc định sẽ được gán 1 default route table.\
Bên trong route table sẽ có route entry **destination**:10.10.0.0/16 **target**:local. Route entry này thể hiện các tài nguyên tạo ra trong cùng 1 VPC có thể kết nối với nhau.

#### Internet Gateway

**Internet Gateway (IGW)** là một thành phần Amazon VPC giúp các tài nguyên bên trong VPC, cụ thể là EC2, có khả năng giao tiếp với Internet. IGW có khả năng co giãn mạnh theo chiều ngang, đồng thời tính dự phòng và sẵn sàng cao. Nó hoạt động như một target trong bảng định tuyến của Amazon VPC, giúp lưu lượng truy cập được định tuyến ra ngoài Internet bằng cách biên dịch địa chỉ mạng của EC2 thành địa chỉ Public IP đã được gán cho nó.

#### NAT Gateway

Mặc định, mọi EC2 chạy bên trong Private subnet thì sẽ không có khả năng giao tiếp với Internet thông qua **IGW**. Từ đó vấn đề phát sinh khi EC2 đó cần truy cập ra ngoài Internet để áp dụng các bản cập nhật bảo mật, tải xuống các bản vá hoặc cập nhật phần mềm ứng dụng.
Nắm bắt được nhu cầu đó, AWS cung cấp 2 phương thức cho phép các EC2 bên trong Private subnet có quyền được truy cập Internet, đó là **NAT Instance** và **NAT Gateway**. Với các trường hợp thông thường, thì ta nên sử dụng **NAT Gateway** thay cho **NAT Instance**. **NAT Gateway** đảm bảo tính sẵn sàng và băng thông cao hơn, đồng thời đòi hỏi ít nỗ lực quản trị hơn so với **NAT Instance**.

#### Load Balancer

**Load Balance** (máy cân bằng tải) là một công cụ có thể phân phối lưu lượng dữ liệu được trao đổi tới các tài nguyên AWS (cụ thể trong bài lab này là các **EC2 Instances**) trong **Target Group**.

#### Target Group

**Target Group** (nhóm mục tiêu) là một nhóm những thành phần tài nguyên AWS sẽ nhận lưu lượng dữ liệu được phân phối và truyền tải bởi **Load Balancer**.

#### Amazon CloudFront

**Amazon CloudFront** là một dịch vụ **content delivery network (CDN)** được xây dựng cho việc đảm bảo hiệu năng cao, an toàn cho người sử dụng.

#### Amazon RDS

**Amazon RDS** là một dịch vụ vận hành cơ sở dự liệu tự động (Database-as-a-service) cho phép bạn có thể tự động hóa quy trình tạo lập, vận hành, và mở rộng quy mô của một cơ sở dữ liệu quan hệ (relational database) trên nền tảng điện toán đám mây của AWS.

#### AWS WAF (Web Application Firewall)

**AWS WAF (Web Application Firewall)** là một dịch vụ bảo mật mạng giúp bảo vệ ứng dụng web của bạn khỏi các cuộc tấn công, bảo vệ dữ liệu quan trọng và đảm bảo tính khả dụng của ứng dụng
