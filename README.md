一个已root的安卓手机
# Ubuntu
```sh
sudo apt install qemu-user-static debootstrap
sudo qemu-debootstrap --arch=arm64 --include=locales,sudo,python3,openjdk-17-jre-headless bookworm rootfs http://mirrors.tuna.tsinghua.edu.cn/debian/
```
修改_apt的用户组
```sh
cd rootfs
sudo vim etc/passwd
```
找到_apt那行，把65534改为3003

`sudo tar -czf ../bookworm.tgz *`

# Termux
1. 换源

`termux-change-repo`

2. 升级系统

`pkg upgrade -y`

3. 安装debootstrap并配置Debian rootfs
```sh
pkg install debootstrap
debootstrap --arch=arm64 --include=locales,sudo,python3,openjdk-17-jre-headless bookworm rootfs http://mirrors.tuna.tsinghua.edu.cn/debian/
cd rootfs
```
4. 修改_apt的用户组

`nano etc/passwd`找到_apt那行，把65534改为3003

5. 打包
```sh
termux-setup-storage
tar -czf /sdcard/bookworm.tgz *
```
