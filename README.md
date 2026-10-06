# Session 06 - Exercise 2

## 1. Cấu hình sudoers đã thêm vào hệ thống

Sử dụng `visudo` để chỉnh sửa file cấu hình sudoers:

```bash
sudo visudo
```

Thêm dòng cấu hình sau vào cuối file:

```text
%devops-admin ALL=(ALL) NOPASSWD: /usr/bin/systemctl start *, /usr/bin/systemctl stop *, /usr/bin/systemctl restart *, /usr/bin/systemctl status *
```

Cấu hình trên cho phép các user thuộc nhóm `devops-admin` thực hiện các lệnh `systemctl start`, `stop`, `restart`, `status` mà không cần nhập mật khẩu.

### Hình ảnh cấu hình sudoers

(./images/cau-hinh.png)
## 2. Kết quả chạy `sudo -l`

Đăng nhập bằng tài khoản `deployer`:

```bash
su - deployer
```

Kiểm tra các quyền sudo được cấp:

```bash
sudo -l
```

Kết quả cho thấy tài khoản `deployer` được phép thực hiện các lệnh `systemctl` đã cấu hình với tùy chọn `NOPASSWD`.

### Hình ảnh kết quả `sudo -l`

(./images/ket-qua.png)
