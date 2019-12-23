# Mở và khóa đăng nhập mật khẩu của tài khoản user trên Linux #
- Option 1: Sử dụng lệnh "passwd -l username"  
```
[root@localhost ~]# passwd -l username

Locking password for user username.

passwd: Success
```
- Option 2: Sử dụng lệnh "usermod -l username".
```
[root@localhost ~]# usermod -l username
```
# kiểm tra trạng thái của người dùng bị khóa hay không? #
- Tìm người dùng trong tệp / etc / shadow và dấu chấm than (!) sau tên người dùng. Nếu người dùng bị khóa bằng lệnh "passwd -l username", ta có thể thấy dòng như sau.
```
[root@localhost ~]# grep username /etc/shadow

username:!$6$pmQO0ZPH$CodOZ5xfPHmgdR8czIFFL07wPipBpczjeXz5wapGUNj1NLsnrlCEzxOyk6/oL.WIFSoCCppwbCi7bQ//HJAn8.:16052:0:99999:7:::
```
- Nếu người dùng bị khóa bằng việc sử dụng "usermod -l", ta có thể thấy thông báo như dưới đây.
```
root@localhost ~]# grep username /etc/shadow

username:!$6$pmQO0ZPH$CodOZ5xfPHmgdR8czIFFL07wPipBpczjeXz5wapGUNj1NLsnrlCEzxOyk6/oL.WIFSoCCppwbCi7bQ//HJAn8.:16052:0:99999:7:::
```

