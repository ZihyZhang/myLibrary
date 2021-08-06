在 github 上添加 SSH key 的步骤：
1、创建一个 SSH key
````
$ ssh-keygen -t rsa -C "your_email@example.com"
````

代码参数含义：
-t 指定密钥类型，默认是 rsa ，可以省略。
-C 设置注释文字，比如邮箱。
-f 指定密钥文件存储文件名。

以上代码省略了 -f 参数，因此，运行上面那条命令后会让你输入一个文件名，用于保存刚才生成的 SSH key 代码，如：
````
Generating public/private rsa key pair.
Enter file in which to save the key (/home/username/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/username/.ssh/id_rsa.
Your public key has been saved in /home/zhangzihui/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:kY2Uq8IGIUENFgAfwheYMPk6E99ik1lla76J4cbvhHo0 your_email@example.com
The key's randomart image is:
+--[ED25519 256]--+
|=o.=*.. ..       |
|+o=+o....+       |
|oB.B.* .+..      |
| +* B   o.       |
|o...o   oS       |
| . o + +o.       |
|   . =Eo..       |
|  . o..o         |
|   . .+.         |
+----[SHA256]-----+
````

创建成功
2、添加 SSH key 到 github
首先你需要拷贝 id_rsa.pub 文件的内容，可以用编辑器打开文件复制，也可以用git命令复制该文件的内容，如：
$ clip < ~/.ssh/id_rsa.pub
# Copies the contents of the id_rsa.pub file to your clipboard
登录你的github账号，从右上角的设置（ Settings ）进入，然后点击菜单栏的 SSH and GPG keys 进入页面。

点击 Add SSH key 按钮添加一个 SSH key 。把你复制的 SSH key 代码粘贴到 key 所对应的输入框中。
上面的 Title 所对应的输入框你也可以输入一个该 SSH key 显示在 github 上的一个别名，也可以不输入，默认会使用你的邮件名称。
