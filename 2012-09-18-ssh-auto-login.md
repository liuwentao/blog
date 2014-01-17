Date: 2012-06-24 17:43
Title: SSH自动登录
Tags: linux,ssh
Slug: ssh-auto-login
Category: Soft

### 自动ssh/scp方法

A为主机; B为远程主机, 假如ip为192.168.1.102; A和B的系统都是Linux

在A上运行命令: 
<pre>ssh-keygen -t rsa (按照提示操作就可以了)
  ssh root@192.168.1.102 "mkdir .ssh"
  scp ~/.ssh/id<em>rsa.pub root@192.168.1.102:.ssh/id</em>rsa.pub
  </pre> 在B上的命令: 

<pre>touch /root/.ssh/authorized&lt;/em>keys （认证key，可以存放多个）
  cat /root/.ssh/id<em>rsa.pub >> /root/.ssh/authorized</em>keys (将id<em>rsa.pub的内容追加到authorized</em>keys 中)
  </pre> 回到A机器: 

<pre>ssh root@192.168.1.102 (不需要密码, 登录成功)
</pre>

</p>