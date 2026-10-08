# DevOps Hackathon - Đề 006

## 1. Thông tin sinh viên

| Họ và tên | Mã sinh viên | Lớp | Tài khoản Linux | GitHub | Cổng Nginx |
|---|---|---|---|---|---|
| Đặng Khánh An | PTIT-HN-070 | CNTT3 | `khanhan-lab` | [KHANHAN007] | `8091` |

## 2. Triển khai

```bash
sudo git clone devops-hackathon-de006-khanhan007.git /var/www/devops-hackathon-de006-khanhan007

sudo chown -R khanhan-lab:khanhan-lab /var/www/devops-hackathon-de006-khanhan007

sudo find /var/www/devops-hackathon-de006-khanhan007 -type d -exec chmod 755 {} \;

sudo find /var/www/devops-hackathon-de006-khanhan007 -type f -exec chmod 644 {} \;
```
