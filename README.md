# Đặc trưng
- Nhảy cổng, kiểm soát tốc độ truyền tải
- Hysteria là một giao thức proxy được mã hóa dựa trên UDP để truyền cơ bản. So với các giao thức hiện đang được sử dụng như ss, vmess, vless và trojan, hysteria có thể tăng đáng kể tốc độ Internet trong khi vượt qua kiểm duyệt tường lửa. Điều này là do hysteria đã sửa đổi khả năng kiểm soát tắc nghẽn của quic. thuật toán

  
# Cài đặt Hysteria2 chỉ bằng một cú nhấp chuột
```
bash <(curl -fsSL https://get.hy2.sh/)
```

#Tạo chứng chỉ tự ký
```
openssl req -x509 -nodes -newkey ec:<(openssl ecparam -name prime256v1) -keyout /etc/hysteria/server.key -out /etc/hysteria/server.crt -subj "/VN=dl.kgvn.garenanow.com" -days 36500 && sudo chown hysteria /etc/hysteria/server.key && sudo chown hysteria /etc/hysteria/server.crt
```

# Start Hysteria2
```
systemctl start hysteria-server.service
```
# Khởi động lại Hysteria2
```
systemctl restart hysteria-server.service
```
# Xem trạng thái Hysteria2
```
systemctl status hysteria-server.service
```
# Stop Hysteria2
```
systemctl stop hysteria-server.service
```
# Đặt tự động khởi động khi khởi động
```
systemctl enable hysteria-server.service
```
# Xem nhật kí
```
journalctl -u hysteria-server.service
```
