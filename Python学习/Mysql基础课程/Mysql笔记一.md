## MySQL登录、访问、退出操作

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

## 使用navicat连接Mysql

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
   > ​	字段名一	字段类型（数据显示长度[^超过限定长度也可以，会做兼容]） ，
   >
   > ​	字段名二	字段类型，
   >
   > ​	字段名三	字段类型
   >
   > }

5. > int : 整数类型
   >
   > var[^变量]char[^字符类型] ：变量字符类型
   >
   > char ：字符类型
   >
   > date：？

6. 选中后右键运行，或点击运行

7. 创建完成后可在左侧表中进行查看，点击表名可查看表内容

8. 查看表结构，展示表的字段详细信息：desc 表名；

9. 查看表中数据：select *[^所有的] from 表名；

10. 查看建表语句：show create table 表名；（生成的建表语句会在生成表的语句上增加一些底层的东西，可用于发送给其他程序员）

11. 在mybase中通过右键插入代码块，选择sql，插入代码

## 数据库表列类型

1. ![](/image/数据类型1.jpg)

2. ![](/image/字符串类型.jpg)
3. CHAR 和 VARCHAR 类型相似，均用于存于较短的字符串，主要的不同之处在于存储方式。 CHAR 类型长度固定， VARCHAR 类型的长度可变因为 VARCHAR 类型能够根据字符串的实际长度来动态改变所占字节的大小，所以在不能明确该字段具体需要多少字符时推荐使用 VARCHAR 类型，这样可节约磁盘空间、提高存储效率。
4. CHAR和VARCHAR表示的是字符的个数，而不是字节的个数
5. <font color=red>疑问：字符和字节的区别？</font>
6. ![](/image/日期和时间类型.jpg)
7. ![](/image/两种时间类型的不同之处.jpg)
8. 在实际开发中哪种合适用哪种，看情况选取

## 添加数据

1. 在navicat中通过保存快捷键创建查询，在以后做联系的时候也能够重新查看
2. 查看表内容
3. 在数据库中插入数据：insert into 表名 values （数据[^一条记录/行数据] ,数据2）；
4. ![](/image/插入数据注意事项.jpg)
5. 按照注意事项将数据内容修改后新增，查看是否可行
6. now（）为函数，将now（）替换插入数据中的内容，可在插入数据的时候直接替换为当前时间
7. 运行后的信息中编号开头的是错误编号，后面是报错
8. 插入指定字段数据：insert into 表名 （字段名1，字段名2）values （数据1，数据2），没指定的字段会为空
9. 人为创建错误查看是否成立

## 修改、删除数据

1. 修改表中数据：

   >  修改所有的数据：update 表名 set 字段名=数据；
   >
   > 修改指定记录的数据：update 表名 set 字段名=数据 where 字段名=指定值； 

2. 修改字段数据中的大小写，发现指定记录后修改内容不区分大小写

3. 删除操作

   > 删除表中所有数据：delete from 表名 ；
   >
   > 删除指定数据：delete from 表名 where 字段名=值；

## 修改、删除数据库表

