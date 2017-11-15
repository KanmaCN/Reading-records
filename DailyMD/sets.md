##1.git设置代理

git config --global http.proxy "http://www-proxy.us.oracle.com:80"
git config --global https.proxy "http://www-proxy.us.oracle.com:80"

这些设置最终会保存在用户目录下的 .gitconfig 文件中，打开这个文件可以看到类似的几行配置
    [http]
            proxy = http://www-proxy.us.oracle.com:80
    [https]
            proxy = http://www-proxy.us.oracle.com:80
如果端口有变动也可以直接在这里修改。

取消代理：

git config --global --unset http.proxy
git config --global --unset https.proxy

git config --list

##2.npm的代理设置
npm config set proxy http://www-proxy.us.oracle.com:80

##3.环境变量的设置
1.node.js
export PATH=$PATH:/scratch/kanma/apps/node/node-v6.11.3-linux-x64/bin

echo $SHELL

cshrc

set path =(/scratch/kanma/apps/node/node-v6.11.3-linux-x64/bin $path)


##4.git
1.cat ~/.ssh/id_rsa.pub
2.$ git config --global user.name "kang.ma@oracle.com"
 $ git config --global user.email "kang.ma@oracle.com"


##自执行匿名函数：
```
常见格式：(function() { /* code */ })();
解释：包围函数（function(){})的第一对括号向脚本返回未命名的函数，随后一对空括号立即执行返回的未命名函数，括号内为匿名函数的参数。
作用：可以用它创建命名空间，只要把自己所有的代码都写在这个特殊的函数包装内，那么外部就不能访问，除非你允许(变量前加上window，这样该函数或变量就成为全局)。各JavaScript库的代码也基本是这种组织形式。
总结一下，执行函数的作用主要为 匿名 和 自动执行,代码在被解释时就已经在运行了。

其他写法
(function () { /* code */ } ()); 
!function () { /* code */ } ();
~function () { /* code */ } ();
-function () { /* code */ } ();
+function () { /* code */ } ();

用(function(){xxx})()是利用匿名函数和闭包用来执行xxx里面的代码，同时所有的定义比如变量的作用域都在闭包里，不会污染到外部命名空间。

```
#相对路径
```
相对路径是指相对于当前目录的位置。相对路径使用两种特殊符号，单点 (.) 和双点 (..)，通过它们可以转换到当前目录或父目录。双点用于在目录等级中上移。单点表示当前目录本身。

```
#window.location
```
window.location 对象所包含的属性
属性	描述
hash	 从井号 (#) 开始的 URL（锚）
host	 主机名和当前 URL 的端口号
hostname 当前 URL 的主机名
href	 完整的 URL
pathname 当前 URL 的路径部分
port	 当前 URL 的端口号
protocol 当前 URL 的协议
search	 从问号 (?) 开始的 URL（查询部分）

例如：
location.search是从当前URL的?号开始的字符串
如:http://www.51js.com/viewthread.php?tid=22720
它的search就是?tid=22720

```

###OpenSSH_5.3p1, OpenSSL 1.0.1e-fips 11 Feb 2013
usage: ssh [-1246AaCfgKkMNnqsTtVvXxYy] [-b bind_address] [-c cipher_spec]
           [-D [bind_address:]port] [-e escape_char] [-F configfile]
           [-I pkcs11] [-i identity_file]
           [-L [bind_address:]port:host:hostport]
           [-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
           [-R [bind_address:]port:host:hostport] [-S ctl_path]
           [-W host:port] [-w local_tun[:remote_tun]]
           [user@]hostname [command]

# ssh://kang.ma%40oracle.com@alm.oraclecorp.com:2222/cloudvis_fnd-patterns-jet_5817/fnd-patterns-jet.git
  https://kang.ma%40oracle.com@alm.oraclecorp.com/cloudvis/s/cloudvis_fnd-patterns-jet_5817/scm/fnd-patterns-jet.git
  alm.oraclecorp.com:2222

#处理git clone命令的非标准SSH端口连接

使用git clone命令clone项目时，如果repository的SSH端口不是标准22端口时（例如，SSH tunnel模式，等等），可以使用如下命令：

git clone ssh://git@hostname:port/.../xxx.git
举例如下：

git clone ssh://git@10.137.20.113:2222/root/test.git


###Usage: /etc/init.d/sshd {start|stop|restart|reload|force-reload|condrestart|try-restart|status}
sudo /etc/init.d/sshd restart


tar xpvf /path/to/my_archive.tar.xz -C /path/to/extract

Simple install procedure
========================

  % tar xf gtk+-3.20.10.tar.xz          # unpack the sources
  % cd gtk+-3.20.10                     # change to the toplevel directory
  % ./configure                        # run the `configure' script
  % make                               # build GTK+
  [ Become root if necessary ]
  % make install                       # install GTK+

##ssh -v -v server


when i can't clone codes using ssh in my vm, the outputs the following message :

 Permission denied (keyboard-interactive,publickey).
 fatal: The remote end hung up unexpectedly
