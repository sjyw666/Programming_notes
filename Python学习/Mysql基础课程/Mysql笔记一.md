![](F:\编程笔记\Python学习\Mysql基础课程\image\登录、访问.jpg)

打开终端窗口通过登录命令mysql -hlocahost[^主机名] -uroot[^用户名] -p

mysql不是内部或外部命令，则需要配置环境变量Path中去，将mysql.exe的bin目录放进去

修改完环境变量后重启终端才能生效

MySQL层次：不同项目对应不同数据库组成，每个数据库中有很多表，每个表中有很多数据

show databases：查看所有数据库

use 数据库名：切换到指定数据库

show tables：查看所有表

select * from 表名：查看表内容，通过终端

**退出当前数据库**：可以使用quit或者exit命令完成，也可以用\q；完成退出操作

## 卸载数据库

![](F:\编程笔记\Python学习\Mysql基础课程\image\卸载数据库.jpg)

![](F:\编程笔记\Python学习\Mysql基础课程\image\Navicat认识.jpg)

![](F:\编程笔记\Python学习\Mysql基础课程\image\MySQL操作逻辑.jpg)

![](F:\编程笔记\Python学习\Mysql基础课程\image\2059链接错误.jpg)

**第二种方法**：

1. 通过cmd登录MySQL后
2. 设置密码永不过期：alter user ‘toot‘ @ ’localhost‘ identified by ’root’ password expire never;
3. 设置（用户登录）加密规则为mysql_native_password：alter user 'root' @ 'localhost' identified with mysql_native_password by 'root';
4. 重新访问navicat，提示连接成功
5. 通过点击连接进入数据库，点击MySQL可查看表

![](F:\编程笔记\Python学习\Mysql基础课程\image\SQL语言入门.jpg)

99版后99版之后的相差不大，但是92版和99版相差很大，所以以99版为主

**SQL语言分为五个部分：**

![](F:\编程笔记\Python学习\Mysql基础课程\image\SQL语句二.jpg) 

事务：A向B转账，A减100、B加100，两个呈绑定关系[^同时成功或同时失败]，这种关系称为事务

## 创建数据库表：

![](F:\编程笔记\Python学习\Mysql基础课程\image\创建数据库表.jpg)

1. 右键连接，新建数据库，选择字符集为utf8mb4[^对应utf-8] 

2. 点击表、查询、新建查询，出现编辑窗口就可以输入SQL语句

3. 两个#号或-- [^杠杠空格]表示单行注释，/**/表示多行注释

4. 表结构
   > 创建 表 表名{
   >
   > ​	字段名一	字段类型（显示长度） ，
   >
   > ​	字段名二	字段类型，
   >
   > ​	字段名三	字段类型
   >
   > }
