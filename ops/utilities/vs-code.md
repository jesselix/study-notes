# VS Code

## Remote Development
-> 若通过Windows连接，用PowerShell安装OpenSSH。以管理员身份启动 PowerShell。

Get-WindowsCapability -Online | ? Name -like 'OpenSSH*'
# This should return the following output:
Name  : OpenSSH.Client~~~~0.0.1.0
State : NotPresent
Name  : OpenSSH.Server~~~~0.0.1.0
State : NotPresent

# Install the OpenSSH Client
Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0
# Install the OpenSSH Server
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
# Both of these should return the following output:
Path          :
Online        : True
RestartNeeded : False

-> 检查 C:\Users\jesse\.ssh 是否有id_rsa id_rsa.pub文件，如果没用，使用 PowerShell的ssh-keygen 命令生成密钥文件。将 id_rsa.pub 里的内容复制到远程主机的'~/.ssh/authorized_keys' 文件中。

-> C:\Users\jesse\.ssh目录中创建一个ssh_config文件，里面配置格式参考如下：
Host vm-ubuntu
    HostName 192.168.52.128
    User root

-> VS Code安装Remote Development插件。

-> VS Code的Remote Explorer中通过指定ssh_config文件连接服务器。


## References
VS Code Remote  
https://code.visualstudio.com/docs/remote/remote-overview

https://www.cnblogs.com/xiaoqi/p/vs-code-remote.html

https://segmentfault.com/a/1190000019550872?utm_source=tag-newest

https://www.jianshu.com/p/d7c9cef525bc