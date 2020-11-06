# MySQL

### MySQL中的数据类型

#### 整型

| MySQL数据类型 |                 含义                 |
| :-----------: | :----------------------------------: |
|    tinyint    |        1个字节 范围(-128~127)        |
|   smallint    |      2个字节 范围(-32768~32767)      |
|   mediumint   |    3个字节 范围(-8388608~8388607)    |
|      int      | 4个字节 范围(-2147483648~2147483647) |
|    bigint     |   8个字节 范围(+-9.22*10的18次方)    |

取值范围如果加了unsigned，则最大值翻倍，如tinyint unsigned的取值范围为(0~256)。

#### 浮点型

| MySQL数据类型 |                       含义                       |
| :-----------: | :----------------------------------------------: |
|  float(m,d)   | 单精度浮点型  8位精度(4字节)   m总个数，d小数位  |
|  double(m,d)  | 双精度浮点型  16位精度(8字节)   m总个数，d小数位 |

设一个字段定义为float(5,3)，如果插入一个数123.45678,实际数据库里存的是123.457，但总个数还以实际为准，即6位。

#### 字符串

| MySQL数据类型 |              含义               |
| :-----------: | :-----------------------------: |
|    char(n)    |     固定长度，最多255个字符     |
|  varchar(n)   |    固定长度，最多65535个字符    |
|   tinytext    |     可变长度，最多255个字符     |
|     text      |    可变长度，最多65535个字符    |
|  mediumtext   | 可变长度，最多2的24次方-1个字符 |
|   longtext    | 可变长度，最多2的32次方-1个字符 |

char和varchar：
1.char(n) 若存入字符数小于n，则以空格补于其后，查询之时再将空格去掉。所以char类型存储的字符串末尾不能有空格，varchar不限于此。
2.char(n) 固定长度，char(4)不管是存入几个字符，都将占用4个字节，varchar是存入的实际字符数+1个字节（n<=255）或2个字节(n>255)，所以varchar(4),存入3个字符将占用4个字节。
3.char类型的字符串检索速度要比varchar类型的快。

varchar和text：
1.varchar可指定n，text不能指定，内部存储varchar是存入的实际字符数+1个字节（n<=255）或2个字节(n>255)，text是实际字符数+2个字节。
2.text类型不能有默认值。
3.varchar可直接创建索引，text创建索引要指定前多少个字符。varchar查询速度快于text,在都创建索引的情况下，text的索引似乎不起作用。

#### 日期时间类型

| MySQL数据类型 |             含义              |
| :-----------: | :---------------------------: |
|     date      |       日期 '2008-12-2'        |
|     time      |        时间 '12:25:36'        |
|   datetime    | 日期时间 '2008-12-2 22:06:44' |
|   timestamp   |     自动存储记录修改时间      |

若定义一个字段为timestamp，这个字段里的时间数据会随其他字段修改的时候自动刷新，所以这个数据类型的字段可以存放这条记录最后被修改的时间。

#### 数据类型的属性

| MySQL数据类型      | 含义                     |
| :----------------- | ------------------------ |
| null               | 数据列可包含NULL值       |
| not null           | 数据列不允许包含NULL值   |
| default            | 默认值                   |
| primary key        | 主键                     |
| auto_increment     | 自动递增，适用于整数类型 |
| unsigned           | 无符号                   |
| character set name | 指定一个字符集           |

#### 聚合函数

| 函数  | 说明                                   |
| ----- | -------------------------------------- |
| count | 计算所有列行数                         |
| sum   | 计算某一列的合计值，该列必须为数值类型 |
| avg   | 计算某一列的平均值，该列必须为数值类型 |
| max   | 计算某一列的最大值                     |
| min   | 计算某一列的最小值                     |

max()和min()函数并不限于数值类型。如果是字符类型,max()和min()会返回排序最后和排序最前的字符

### 使用MySQL数据库

```mysql
#登录MySQL
	mysql -h 主机名 -u 用户名 -p  
	#-h 该命令用于指定客户端所要登录的MySQL主机名，登陆当前机器该参数可以省略;

#创建数据库
	create database 数据库名[其他选项];
	#例子
	create database sqmp_db character set gbk;
	#character set gbk将数据库字符编码指定为gbk;

#查看已经创建的数据库
	show databases; 

#选择需要操作的数据库
#(一)
	mysql -D 所选择数据库名 -h 主机名 -u 用户名 -p
#(二)
	use 数据库名;
	
#创建数据库表
	create table 表名称(列表明);
	#例子
	create table students
	(
        id int unsigned not null auto_increment primary key,
        name char(8) not null,
        sex char(4) not null,
        age tinyint unsigned not null,
        tel char(13) null default "-"
    );
    #对于一些较长的语句在命令提示符下可能容易输错, 因此我们可以通过任何文本编辑器将语句输入好后保存为 createtable.sql 的文件中, 通过命令提示符下的文件重定向执行执行该脚本。
    mysql -D samp_db -u root -p < createtable.sql(完整路径)

#查看已创建的表名称
	 show tables;

#查看已创建表的详细信息
	describe 表名;
```

### 操作MySQL数据库

```mysql
#向表中插入数据
	insert [into] 表名 [(列名1,列名2,列名3,...)] values (值1,值2,值3,...);
	#其中 [] 内的内容是可选的
	insert into students values(NULL, "王刚", "男", 20, "13811371377");
	#插入部分数据
	insert into students (name, sex, age) values("孙丽华", "女", 21);

#基本查询表中数据
	select 列名称 from 表名称 [查询条件];
	#例如要查询 students 表中所有学生的名字和年龄
	select name, age from students;
	#可以使用通配符 * 查询表中所有的内容
	select * from students;
#条件查询
    select 列名称 from 表名称 where 条件;
    #查询所有性别为女的信息
    select * from students where sex="女";
    
    #where支持的运算符  =、>、<、>=、<、!=   
    #扩展运算符		  is [not] null、in、like
    #组合查询  		   or and
    
    #查询年龄在21岁以上的所有人信息
    select * from students where age > 21;
    #查询名字中带有 "王" 字的所有人信息
    select * from students where name like "%王%";
    #查询id小于5且年龄大于20的所有人信息
    select * from students where id<5 and age>20;
#投影查询
	select id,name,score from students;
#排序
	#'asc'升序' desc'倒序
	#按score从低到高
	select id,name,sex,score from students order by score;
	#按score从高到底 
	select id,name,sex,score from students order by score desc;
	#先按score列倒序，如果有相同分数的，再按sex列排序
	select id,name,sex,score from students order by score desc,sex;
#分页查询
	#查询可以通过 limit <M> offset <N>子句实现
	#limit:限制每页记录数量 
	#offset:跳过多少条记录 
	select id from students limit 4 offset 0;
	#每页需要显示的结果数量pageSize，然后根据当前页的索引pageIndex（从1开始）
	#limit总是设定为 pageSize
	#offset计算公式为 pageSize * (pageIndex - 1)
#聚合查询
	#count(*)表示查询所有列的行数
	select count(*) from students;
	#给列名设置一个别名，便于处理结果,设置结果集的列名为num
	select count(*) num from students;
	#聚合查询同样可以使用where条件
	#如果聚合查询的where条件没有匹配到任何行，count()返回0,而sum(),avg(),max(),min()返回null
	#使用聚合查询计算男生平均成绩
	select avg(score) average from students where sex = 'M';
	#分组聚合,按class分组
	select class,count(*) num from students group by class;
#多表查询
	#结果集是目标表的行数乘积
	select * from <表1> <表2>
	#设置列的别名来给两个表各自的id和name列起别名,给表设置一个别名
	select
    	s.id sid,
    	s.name,
    	s.gender,
    	s.score,
    	c.id cid,
    	c.name cname
	from students s, classes c
	where s.sex = 'M' and c.id = 1;
#连接查询
	#内连接——INNER JOIN
	select s.id, s.name, s.class_id, c.name class_name, s.gender, s.score
	from students s
	inner join classes c
	on s.class_id = c.id;
	#INNER JOIN查询的写法  只返回同时存在于两张表的行数据
	#先确定主表，仍然使用FROM <表1>的语法；
	#再确定需要连接的表，使用INNER JOIN <表2>的语法
	#后确定连接条件，使用ON <条件...>，这里的条件是s.class_id = c.id，表示students表的class_id列与classes表的id列相同的行需要连接
	
	#外连接--OUTER JOIN
	#right outer join返回右表都存在的行
	select s.id, s.name, s.class_id, c.name class_name, s.gender, s.score
	from students s
	right outer join classes c
	on s.class_id = c.id;
	#left outer join则返回左表都存在的行
	select s.id, s.name, s.class_id, c.name class_name, s.gender, s.score
	from students s
	left outer join classes c
	on s.class_id = c.id;
	#full outer join把两张表的所有记录全部选择出来
	select s.id, s.name, s.class_id, c.name class_name, s.gender, s.score
	from students s
	full outer join classes c
	on s.class_id = c.id;
	
#更新表中数据
	update 表名称 set 列名称=新值 where 更新条件;
	#将id为5的手机号改为默认的"-"
	update students set tel=default where id=5;
	#将所有人的年龄增加1
	update students set age=age+1;
	#将手机号为 13288097888 的姓名改为 "张伟鹏", 年龄改为 19
	update students set name="张伟鹏", age=19 where tel="13288097888";

#删除表中数据 
	delete from 表名称 where 删除条件;
	#删除id为2的行
	delete from students where id=2;
	#删除所有年龄小于21岁的数据
	delete from students where age<20;
	#删除表中的所有数据
	delete from students;
```

### 创建后表的修改

```mysql
#添加列
	alter table 表名 add 列名 列数据类型 [after 插入位置];
	#在表的最后追加列
	alter table students add address char(60);
	#在名为 age 的列后插入列 birthday
	alter table students add birthday date after age;

#修改列
	alter table 表名 change 列名称 列新名称 新数据类型;
	#将表 tel 列改名为 telphone
	alter table students change tel telphone char(13) default "-";
	#将 name 列的数据类型改为 char(16)
	alter table students change name name char(16) not null;

#删除列
	alter table 表名 drop 列名称;
	#删除 birthday 列
	alter table students drop birthday;

#重命名表
	alter table 表名 rename 新表名;
	#重命名 students 表为 workmates
	alter table students rename workmates;

#删除整张表
	drop table 表名;
	#删除 workmates 表
	drop table workmates;
	
#删除整个数据库
	drop database 数据库名;
	#删除 stu 数据库
	drop database stu;
```

### MySQL技巧

```mysql
#插入或替换(replace)
	#如果记录已经存在，就先删除原记录，再插入新记录
	replace into students (id, class_id, name, gender, score) values (1, 1, '小明', 'F', 99);

#插入或更新(on duplicate key update)
	#如果记录已经存在，就更新该记录
	insert into students (id, class_id, name, gender, score) values (1, 1, '小明', 'F', 99) on duplicate key update name='小明', gender='F', score=99;

#插入或忽略(ignore)
	#如果记录已经存在，就啥事也不干直接忽略
	insert ignore into students (id, class_id, name, gender, score) values (1, 1, '小明', 'F', 99);

#快照
	#复制一份当前表的数据到一个新表
	#对class_id=1的记录进行快照，并存储为新表students_of_class1
	create table students_of_class1 select * from students where class_id=1;
	
#写入查询结果集
	#查询结果集需要写入到表中，可以结合INSERT和SELECT，将SELECT语句的结果集直接插入到指定表中
	create table statistics (
    	id bigint not null auto_increment,
    	class_id bigint not null,
    	average double not null,
    	primary key (id)
	);
	insert into statistics (class_id, average) select class_id, avg(score) from students group by class_id;

#强制使用指定索引
	#指定索引的前提是索引idx_class_id必须存在
	select * from students force index (idx_class_id) where class_id = 1 order by id desc;
```

### 修改root用户密码

```mysql
mysqladmin -u 用户名 -p password 新密码
```

在 Java，Python 中双引号变单引号

我是你爹

这是一个测试