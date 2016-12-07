**Base package (require)**

```
sudo apt-get install nginx - y
sudo apt-get install git - y
```

----------

**install java (7):**
```
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt-get update
sudo apt-get install openjdk-7-jdk
sudo update-alternatives --config java
sudo update-alternatives --config javac
java -version
```

----------

**install jenkins:**
https://wiki.jenkins-ci.org/display/JENKINS/Installing+Jenkins+on+Ubuntu

*Cài đặt thành công phải mở cổng 8080 trên server mới vào được
sau khi vào http://localhost:8080
mở file /var/lib/jenkins/secrets/initialAdminPassword để lấy mã xác thực cài đặt
tiếp theo làm theo hướng dẫn của jenkins để hoàn tất quá trình cài đặt*

----------

**php5.6 & phpunit** 
để chạy test code trước khi deploy bản chính thức
```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt-get -y install php5.6 php5.6-fpm php5.6-mysql php5.6-cli php5.6-mbstring php5.6-mcrypt php5.6-mysql php5.6-xml php5.6-zip
sudo apt-get install phpunit -y
```

----------

Cài capistrano: để deploy tự động

vui lòng xem hướng dẫn tại đây: https://github.com/mannv/capistrano-guide

----------

---------------- Cấu hình jenkins projects ------------------

Vào tất cả project trên github
https://github.com/mannv/phpunit_production/settings/installations
cài đặt Servers Jenkins (GitHub plugin) để có thay đổi gì từ github nó sẽ bắn 1 event tới jenkin và thực hiện quá trình deploy tự động

Cấu hình 2 project, vui lòng xem thư mục đi kèm
https://github.com/mannv/jenkins/tree/master/capistrano
https://github.com/mannv/jenkins/tree/master/phpunit

để push notification đến slack
Jenkins: cần phải cài plugin
Slack Notification Plugin (chọn phiên bản 1.8.1 - setup đỡ lằng ngoằng)
https://github.com/mannv/jenkins/tree/master/plugin

Slack
vào:  https://my.slack.com/services/new/jenkins-ci
cài đặt để lấy Token


