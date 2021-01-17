# Networks

# d


模型
OSI七层网络模型	TCP/IP四层概念模型  	对应网络协议
应用层（Application）	应用层	HTTP、TFTP, FTP, NFS, WAIS、SMTP
表示层（Presentation）		Telnet, Rlogin, SNMP, Gopher
会话层（Session）		SMTP, DNS
传输层（Transport）	传输层	TCP, UDP
网络层（Network）	网络层	IP, ICMP, ARP, RARP, AKP, UUCP
数据链路层（Data Link）	数据链路层	FDDI, Ethernet, Arpanet, PDN, SLIP, PPP
物理层（Physical）		IEEE 802.1A, IEEE 802.2到IEEE 802.11


References
OSI七层协议模型、TCP/IP四层模型学习笔记
https://www.cnblogs.com/Robin-YB/p/6668762.html



TCP和UDP的优缺点及区别 
TCP的优点： 可靠，稳定 TCP的可靠体现在TCP在传递数据之前，会有三次握手来建立连接，而且在数据传递时，有确认、窗口、重传、拥塞控制机制，在数据传完后，还会断开连接用来节约系统资源。 TCP的缺点： 慢，效率低，占用系统资源高，易被攻击 TCP在传递数据之前，要先建连接，这会消耗时间，而且在数据传递时，确认机制、重传机制、拥塞控制机制等都会消耗大量的时间，而且要在每台设备上维护所有的传输连接，事实上，每个连接都会占用系统的CPU、内存等硬件资源。 而且，因为TCP有确认机制、三次握手机制，这些也导致TCP容易被人利用，实现DOS、DDOS、CC等攻击。
UDP的优点： 快，比TCP稍安全 UDP没有TCP的握手、确认、窗口、重传、拥塞控制等机制，UDP是一个无状态的传输协议，所以它在传递数据时非常快。没有TCP的这些机制，UDP较TCP被攻击者利用的漏洞就要少一些。但UDP也是无法避免攻击的，比如：UDP Flood攻击…… UDP的缺点： 不可靠，不稳定 因为UDP没有TCP那些可靠的机制，在数据传递时，如果网络质量不好，就会很容易丢包。 基于上面的优缺点，那么： 什么时候应该使用TCP： 当对网络通讯质量有要求的时候，比如：整个数据要准确无误的传递给对方，这往往用于一些要求可靠的应用，比如HTTP、HTTPS、FTP等传输文件的协议，POP、SMTP等邮件传输的协议。 在日常生活中，常见使用TCP协议的应用如下： 浏览器，用的HTTP FlashFXP，用的FTP Outlook，用的POP、SMTP Putty，用的Telnet、SSH QQ文件传输 ………… 什么时候应该使用UDP： 当对网络通讯质量要求不高的时候，要求网络通讯速度能尽量的快，这时就可以使用UDP。 比如，日常生活中，常见使用UDP协议的应用如下： QQ语音 QQ视频 TFTP ……
有些应用场景对可靠性要求不高会用到UPD，比如长视频，要求速率

小结TCP与UDP的区别：
1.基于连接与无连接；
2.对系统资源的要求（TCP较多，UDP少）；
3.UDP程序结构较简单；
4.流模式与数据报模式 ；
5.TCP保证数据正确性，UDP可能丢包，TCP保证数据顺序，UDP不保证。

https://www.cnblogs.com/thrillerz/p/6464203.html
【问题1】为什么连接的时候是三次握手，关闭的时候却是四次握手？
答：因为当Server端收到Client端的SYN连接请求报文后，可以直接发送SYN+ACK报文。其中ACK报文是用来应答的，SYN报文是用来同步的。但是关闭连接时，当Server端收到FIN报文时，很可能并不会立即关闭SOCKET，所以只能先回复一个ACK报文，告诉Client端，"你发的FIN报文我收到了"。只有等到我Server端所有的报文都发送完了，我才能发送FIN报文，因此不能一起发送。故需要四步握手。





Session与Cookie：Cookie可以让服务端跟踪每个客户端的访问，但是每次客户端的访问都必须传回这些Cookie，如果Cookie很多，则无形的增加了客户端与服务端的数据传输量，
而Session则很好地解决了这个问题，同一个客户端每次和服务端交互时，将数据存储通过Session到服务端，不需要每次都传回所有的Cookie值，而是传回一个ID，每个客户端第一次访问服务器生成的唯一的ID，客户端只要传回这个ID就行了，这个ID通常为NAME为JSESSIONID的一个Cookie。这样服务端就可以通过这个ID，来将存储到服务端的KV值取出了。
Session和Cookie的超时问题，Cookie的安全问题

防止表单重复提交
https://www.cnblogs.com/xdp-gacl/p/3859416.html

针对"在网络延迟的情况下让用户有时间点击多次submit按钮导致表单重复提交"这个应用场景，使用JavaScript是可以解决这个问题的，解决的做法就是"用JavaScript控制Form表单只能提交一次"。

在服务器端生成一个唯一的随机标识号，专业术语称为Token(令牌)，同时在当前用户的Session域中保存这个Token。然后将Token发送到客户端的Form表单中，在Form表单中使用隐藏域来存储这个Token，表单提交的时候连同这个Token一起提交到服务器端，然后在服务器端判断客户端提交上来的Token与服务器端生成的Token是否一致，如果不一致，那就是重复提交了，此时服务器端就可以不处理重复提交的表单。如果相同则处理表单提交，处理完后清除当前用户的Session域中存储的标识号。
　　在下列情况下，服务器程序将拒绝处理用户提交的表单请求：
存储Session域中的Token(令牌)与表单提交的Token(令牌)不同。
当前用户的Session中不存在Token(令牌)。
用户提交的表单数据中没有Token(令牌)。




二者有如下的区别: 
    首先：Post传输数据时，不需要在URL中显示出来，而Get方法要在URL中显示。 
    其次：Post传输的数据量大，可以达到2M，而Get方法由于受到URL长度限制,只能传递大约1024字节. 
    再次：Post就是为了将数据传送到服务器段,Get就是为了从服务器段取得数据.而Get之所以也能传送数据,只是用来设计告诉服务器,你到底需要什么样的数据.Post的信息作为http请求的内容，而Get是在Http头部传输的。

-----

首先，GET和POST都是HTTP协议中的两种发送请求的方法，由于HTTP的底层是TCP/IP。所以GET和POST的底层也是TCP/IP。GET和POST能做的事情是一样一样的。如果给GET加上request body，活着给POST带上url参数，技术上是完全行的通的。也就是说，GET和POST在本质上没什么区别。 
但是如果真的一点区别都没有，那么这个问题也就不存在了，所以，两者之间最重大的区别就是：
GET产生一个TCP数据包；POST产生两个TCP数据包。

GET在浏览器回退时是无害的，而POST会再次提交请求。
GET产生的URL地址可以被Bookmark，而POST不可以。
GET请求会被浏览器主动cache，而POST不会，除非手动设置。
GET请求只能进行url编码，而POST支持多种编码方式。
GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。
GET请求在URL中传送的参数是有长度限制的，而POST么有。
对参数的数据类型，GET只接受ASCII字符，而POST没有限制。
GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息。
GET参数通过URL传递，POST放在Request body中。

