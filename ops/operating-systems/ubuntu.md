# Ubuntu

更新
-> 检查更新
apt update

-> 更新
apt upgrade

SWAP
-> 检查Swap空间
在设置Swap文件之前，检查一下系统里有没有既存的Swap文件。
swapon -s
如果返回的信息概要是空的，则表示Swap文件不存在。

cd /var

-> 创建一个2048M的文件
dd if=/dev/zero of=swapfile bs=1M count=2048

-> 把它变成swap文件
mkswap swapfile

-> 启动此swap文件
swapon swapfile

-> 修改权限
chmod -R 0600 swapfile

-> 编辑/etc/fstab文件，使得每次开机时自动加载swap文件
echo "/var/swapfile swap swap defaults 0 0" >> /etc/fstab

防火墙
-> 端口设置
永久开放80端口
firewall-cmd --permanent --zone=public --add-port=80/tcp

永久关闭80端口
firewall-cmd --permanent --zone=public --remove-port=80/tcp

--zone #作用域
--add-port=80/tcp  #添加端口，格式为：端口/通讯协议
--permanent   #永久生效，没有此参数重启后失效

查看开放的端口号
firewall-cmd --zone=public --list-ports

查看防火墙状态
systemctl status firewalld.service

查看防火墙命令
firewall-cmd -h



