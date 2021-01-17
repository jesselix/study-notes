-> 安装
apt update -y
apt install -y nodejs npm
npm config set registry https://registry.npm.taobao.org
npm install n -g
n stable

相关命令
n是一个Node工具包，它提供了几个升级命令参数：
n                              显示已安装的Node版本
n latest                    安装最新版本Node
n stable                   安装最新稳定版Node
n lts                         安装最新长期维护版(lts)Node
n <version>            根据提供的版本号安装Node

镜像
得到原本的镜像地址
npm get registry

设成淘宝的
npm config set registry http://registry.npm.taobao.org/

换成原来的
npm config set registry https://registry.npmjs.org/

-> 检查版本，如果看到的仍是旧版本，重启一下系统
node -v
npm -v