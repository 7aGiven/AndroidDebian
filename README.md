一个已root的安卓手机

# Ubuntu
```sh
sudo apt install qemu-user-static debootstrap
sudo qemu-debootstrap --arch=arm64 --include locales,sudo buster buster http://mirrors.tuna.tsinghua.edu.cn/debian/
```

# Termux
1. 换源

`termux-change-repo`

2. 升级系统

`pkg upgrade -y`

3. 安装debootstrap并配置Debian rootfs

```sh
pkg install debootstrap
debootstrap --arch=arm64 bullseye bullseye_arm64 http://mirrors.tuna.tsinghua.edu.cn/debian/
```
