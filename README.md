在 Windows 上使用 Bitwise Tunnelier 通过 SSH 跨墙
=======================

准备
------
* 用来跨墙的服务器 IP、端口（默认22）、SSH 账号、密码；
* Bitwise Tunnelier，点击[这里](https://github.com/AntiGameZ/AntiNote/resources/Tunnelier-Inst.exe)下载；
* 基于 Windows 系统的电脑一台（手机的请无视此文章）；
* 最新稳定版的 Firefox；

__安装 Bitwise Tunnelier__

下载安装文件，按照向导一步到底，不需要配置什么。

__配置 Bitwise Tunnelier__

打开 Bitwise Tunnelier，需要配置 *Login*，*Options*，*Services* 三个选项卡。

* 在 Login 选项卡中；
	* Host 填写服务器 IP；
	* Username 填写 SSH 账号；
	* Initial Method 选择 password；
	* Password 填写 SSH 密码；
	* 视你个人情况，勾选 Store encrypted password in profile，以决定是否将密码存储至配置文件；

* 在 Options 选项卡中
	* 反选 Open Terminal；
	* 反选 Open SFTP；

* 在 Services 选项卡中
	* SOCKS/HTTP Proxy Forwarding 中点选 Enable；
	* List Interface 填写 127.0.0.1；
	* Listen Port 填写 7070；
	
三个选项卡的配置信息都修改好后，回到 Login 选项卡，点击 Login，出现警告窗口时，选择 Accept & Save。

这时，Bitwise Tunnelier 部分的配置已经完成，可以在左边树形菜单中，Save Profile。以后直接点击保存的 Profile 文件，即可载入之前的配置。

__配置 Firefox __

在地址栏中输入 about:config，打开 Firefox 的高级配置页，无视中间出现的警告即可。

搜索 network.proxy.socks_remote_dns，将 false 设置为 true 以打开远程 DNS 解析以规避 DNS 污染问题。设置完成后，直接关闭当前页面，Firefox 会自动保存。

__配置 AutoProxy__

确认以上步骤都以配置完成后，安装 [AutoProxy](https://addons.mozilla.org/zh-cn/firefox/addon/autoproxy/) 插件。AutoProxy 可以自动辨识一个 IP 或网址是否需要跨墙访问并自动选择是否走 Bitwise 访问，从而提升整体访问速度。

安装好 AutoProxy 并重启 Firefox 后，便会看到 AutoProxy 的欢迎页，勾选 gfwList，点选页面下方的*默认代理*，选择*ssh -D*，然后确定。

__完成__

打开 [Twitter](http://www.twitter.com) 和 [Facebook](http://www.facebook.com) 测试一下吧。


