# HƯỚNG DẪN SỬ DỤNG GITHUB

## Trước khi bạn sử dụng Github, bạn cần cài đặt `git-scm`:
Tải xuống tại: https://git-scm.com/download/win

## Hướng dẫn sử dụng Github:

### 1.Đầu tiên cần tạo tài khoản github:

![img](https://i.imgur.com/wvCWP4a.png)

Truy cập vào: https://github.com/join

`Username` là tên tài khoản mình dùng để đăng nhập, sau khi đăng ký xong, địa chỉ github có dạng: github.com/username/

`Email`: nhập email đang sử dụng để kích hoạt tài khoản

`Password`: Nhập mật khẩu, chứa ít nhất 1 ký tự và độ dài trên 8 ký tự.

Điền đầy đủ thông tin rồi bấm `create an account`

### 2.Sau khi tạo tài khoản hoàn tất, chúng ta được đến trang dashboard 
  
![img](https://imgur.com/Uxcxhlh.png)
 
Tại đây chúng ta sẽ tìm hiểu về thuật ngữ `repository`:

`Repository` (kho chứa) nghĩa là nơi mà bạn sẽ lưu trữ mã nguồn và một người khác có thể sao chép (`clone`) lại mã nguồn đó nhằm làm việc.

Repository có hai loại là `Local Repository` (Kho chứa trên máy cá nhân) và `Remote Repository` (Kho chứa trên một máy chủ từ xa).

### 3. Để tạo một dự án mới, trước tiên bạn cần đăng nhập vào Github, sau đó ấn vào dấu + trên menu và chọn `New repository`  hoặc truy cập vào địa chỉ: https://github.com/new
 
![img](https://imgur.com/CejwbfV.png)

Bạn sẽ cần đặt tên cho kho chứa của bạn. Bạn có thể chọn loại kho chứa là `Public` (ai cũng có thể clone) và `Private` (chỉ có những người được cấp quyền mới có thể clone).
 
![img](https://imgur.com/k0Ppa43.png)

Khi tạo xong nó sẽ dẫn bạn tới trang hướng dẫn làm việc với kho chứa vừa tạo. Và kho chứa của bạn bây giờ sẽ có địa chỉ là 
```
https://github.com/username/repository
```
ví dụ 
```
https://github.com/nht1996/blank
```
chẳng hạn.

### B4: Sau khi tạo xong repository, github sẽ gợi ý bạn tạo repository trống hoặc thêm dự án bạn vào repository.

![img](https://imgur.com/5BSq1Ji.png)
 
Tạo repository trắng bạn có thể làm theo hướng dẫn của github, github hướng dẫn rất rõ ràng.

Để thêm dự án của bạn vào repository, bấm `Windows + R` nhập `Powershell.exe`
 
![img](https://imgur.com/Bn0L6kD.png)

Tại giao diện `Powershell`, ta cần trỏ tới thư mục project của bạn: vd dự án của bạn ở 
```
D:\Documents\DeTai_MonHoc\Android\baitap\congtru
```

![img](https://imgur.com/O2acbKC.png)

Tới đây, bạn cần khởi tạo tạo git bằng cách nhập lệnh 
```
git init
 ```
 
![img](https://imgur.com/YEmGr8a.png)

Sau đó bạn nhập lệnh
```
git remote add origin https://github.com/username/repository_name.git
```
để thêm project của mình vào repository, vd 
```
git remote add origin https://github.com/nht1996/blank.git
```

![img](https://imgur.com/nBKexLf.png)

Hiện tại project của bạn đã được thêm vào repository thành công, để mọi người có thể thấy dự án của bạn, bạn cần `commit` lên github, `commit` sẽ quản lý lịch sử upload của bạn: 
```
git add .
git commit –m “upload” 
git push –u origin master
```

![img](https://imgur.com/EiVZd8f.png)

Project của bạn đã được tải lên github thành công:

![img](https://imgur.com/qujLyTP.png)

Để cho phép các thành viên khác tham gia vào project của bạn, ta vào `Setting` > `Collaborators`  > “Nhập tên thành viên cần thêm” > `Add Collaborators` 
   
![img](https://imgur.com/AML4vpU.png)

Hướng dẫn thành viên đóng góp vào dự án:
Để đóng góp vào dự án, bạn cần `clone project` về máy của mình: 
```
git clone repository
```
ví dụ 
```
git clone https://github.com/nht1996/blank.git
```
Sau khi làm việc xong, bạn đưa code lên github theo hướng dẫn ở trên:
```
git add .
git commit –m “upload” 
git push origin master
```
