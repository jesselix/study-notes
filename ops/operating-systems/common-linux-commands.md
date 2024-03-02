# Common Linux Commands

## User
- useradd testuser  创建用户testuser
- passwd testuser  给已创建的用户testuser设置密码 说明：新创建的用户会在/home下创建一个用户目录testuser
- usermod --help  修改用户这个命令的相关参数
- userdel testuser  删除用户testuser
- rm -rf testuser  删除用户testuser所在目录

# Version
查看内核版本
uname -srm

查看发行版
cat /etc/os-release

## Time zone
- Check time with timezone
``` bash
date -R
```

- Select timezone
``` bash
tzselect
```

- Copy file to /etc
``` bash
cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```

## Command alias
``` bash
vim .bashrc
```