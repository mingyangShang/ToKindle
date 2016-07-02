# ToKindle
### 推送文件到Kindle的工具，支持包括中亚地区在内的所有用户

#### 虽然亚马逊已经推出了向Kindle推送文件的SendToKindle插件和客户端，但是却都不支持中亚地区的用户，推送文件时只能手动发送邮件，不免有些麻烦，这款ToKindle工具的目的就是方便用户发送附件，只要在使用前配置好使用时一个命令就能搞定。
___

### 环境要求

保证Python版本>=2.6,可使用`python -V`查看

### 如何使用

1. 首先`git clone git@github.com:mingyangShang/ToKindle.git`,或者fork一个，clone的地址改为自己仓库的地址
2. 在`config.py`文件中配置邮件相关参数，如现在项目中的例子所示：

	```
	MAIL_HOST = "smtp.163.com" # 选用的邮件服务器,这里选择163邮箱服务器
	MAIL_USER = "shang_ming_yang@163.com" # 发件人的邮箱地址
	MAIL_PWD = "password" # 发件人的邮箱密码,若像qq邮箱一样单独打开smtp服务的话要用专门的授权码

	KINDLE_MAIL = "mingyangshang@kindle.cn" # kindle邮箱,即接收文件的邮箱
	```
3. 此时进入该项目的根目录下，运行
	`python kindle.py 附件1 附件2`
	即可将附件1和附件2发送到`KINDLE_MAIL`即kindle绑定的邮箱中，附件个数不限，以空格分隔开就可以
4. 为了在任何位置都可以方便地使用该工具而不用一定要进入项目所在目录，可以用alias将命令简单化.
	- Mac用户：编辑`~/.bash_profile`文件，添加`alias kindle="python kindle.py所在位置"`，使用`source ~/.bash_profile`持久化该别名
	- Linux用户：编辑`~/.bashrc`文件，添加`alias kindle="python kindle.py所在位置"`，使用`source ~/.bashrc`持久化该别名,
	这样，在任何文件位置都可以使用 `kindle 附件全名`发送文件到Kindle了。
	

### 存在问题

1. 本工具已用163，126，gmail邮箱测试过，但如果使用的邮件服务器为qq邮箱服务器时，邮件不能正常发送到Kindle绑定邮箱，该问题尚未解决，请有需要的用户使用163等邮箱
