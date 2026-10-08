# DevOps Hackathon - Đề 006

## 1. Thông tin sinh viên

| Họ và tên | Mã sinh viên | Lớp | Tài khoản Linux | GitHub | Cổng Nginx |
|---|---|---|---|---|---|
| Đặng Khánh An | PTIT-HN-070 | CNTT3 | `khanhan-lab` | [KHANHAN007] | `8091` |

## 2. Môi trường triển khai

- Máy chủ: VPS
- Hệ điều hành: Ubuntu 22.04 LTS
- IP: `160.187.229.99`
- Web server: Nginx
- Công cụ mã nguồn: Git

## 3. Cấu trúc repository

```text
devops-hackathon-de006-khanhan007/
├── src/index.html
├── nginx/khanhan-lab.conf
├── screenshots
├── .gitignore
└── README.md
```

## 4. Cấu hình Nginx

| Tham số | Giá trị | Giải thích |
|---|---|---|
| `listen` | `8091`, `[::]:8091` | Cổng cá nhân IPv4/IPv6 |
| `server_name` | `160.187.229.99` | IP VPS |
| `root` | `/var/www/devops-hackathon-de006-khanhan007/src` | Chỉ phục vụ thư mục `src` |
| `index` | `index.html` | Trang mặc định |
| `allow` | `all` | Cho phép request bên ngoài |
| Access log | `/var/log/nginx/khanhan-lab.access.log` | Log truy cập riêng |
| Error log | `/var/log/nginx/khanhan-lab.error.log` | Log lỗi riêng |

## 5. Tường lửa UFW

```bash
sudo ufw allow 22/tcp
sudo ufw allow 8091/tcp
sudo ufw status verbose
```

## 6. Các bước triển khai

```bash
sudo git clone URL_REPOSITORY /var/www/devops-hackathon-de006-khanhan007
sudo chown -R khanhan-lab:khanhan-lab /var/www/devops-hackathon-de006-khanhan007
sudo find /var/www/devops-hackathon-de006-khanhan007 -type d -exec chmod 755 {} \;
sudo find /var/www/devops-hackathon-de006-khanhan007 -type f -exec chmod 644 {} \;
sudo nginx -t
sudo systemctl reload nginx
```
