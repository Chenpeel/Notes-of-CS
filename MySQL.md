# 写在前面

本篇是学习数据库的基本内容的信息，作为**速览List** 



# Contents

## <a herf="#SQL分类">SQL分类</a> 

## <a herf="#SQL语法">SQL语法</a>

- <a herf="#DDL">DDL</a>
  - <a herf="#数据库">数据库</a>
  - <a herf="#表操作-查询创建">表操作-查询创建</a>
  - <a herf="#表操作-修改">表操作-修改</a>
  - <a herf="#表操作-删除">表操作-删除</a>
- <a herf="#DML">DML</a>
  - <a herf="#添加数据">添加数据</a>
  - <a herf="#修改数据">修改数据</a>
  - [删除数据](#删除数据)





## SQL分类：

### Table

| 分类 |            全称            |                           说明                           |
| :--: | :------------------------: | :------------------------------------------------------: |
| DDL  |  Data Definition Language  | 数据定义语言，用来定义数据库中的对象（数据库、表、字段） |
| DML  | Data Manipulation Language |      数据操作语言，用来对数据库表中的数据进行增删改      |
| DQL  |    Data Query Language     |          数据查询语言，用来查询数据库中表的记录          |
| DCL  |   Data Control Language    |  数据控制语言，用来创建数据库用户、控制数据库的访问权限  |

## SQL语法：

### DDL

##### 数据库

- 查询

- ```mysql
  show databases;		--显示所有库
  select database;	--当前数据库
  ```

- 创建

  ```mysql
  create database ithema default charset utf8mb4 if not exists;
  ```

- 删除

  ```mysql
  drop database if exists test
  ```

- 使用

  ```mysql
  use database
  ```

##### 表操作-查询创建

- 查询所有表

  ```mysql
  show tables
  ```

- 查询表结构

  ```mysql
  desc table_name
  ```

- 查询指定表的建表语句

  ```mysql
  show create table table_name
  ```

- 创建表

  ```mysql
  create table test_user( 
  	id int comment '编号', 
  	name varchar(50) comment '姓名', 
  	age tinyint unsigned comment 'age',
  	gender varchar(1) comment 'sex' ,
    entrydate date comment '入职时间'
  )comment 'user_table';
  ```

##### 表操作-修改

- 添加字段

  ```mysql
  alter table table_name add nick_name varchar(20) comment '昵称';
  ```

- 修改字段

  ```mysql
  alter table table_name modify nick_name varchar(21);
  ```

- 修改字段名和字段类型

  ```mysql
  alter table table_name change nick_name nickname varchar(20) ;
  ```

- 删除字段

  ```mysql
  alter table table_name drop nickname;
  ```

- 修改表名

  ```mysql
  alter table old_table_name rename to new_table_name;
  ```

##### 表操作-删除

- 删除表

  ```mysql
  drop table if exists table_name;
  ```

- 删除并重新创建

  ```mysql
  truncate table table_name;
  ```

![image-20230422232140753](https://github.com/Chenpeel/Notes-of-CS/blob/master/pics/image-20230422232140753.png)

![image-20230422232634397](https://github.com/Chenpeel/Notes-of-CS/blob/master/pics/image-20230422232634397.png)

![image-20230422232846561](https://github.com/Chenpeel/Notes-of-CS/blob/master/pics/image-20230422232846561.png)

### DML

##### 添加数据

- 给指定字段添加数据

  ```mysql
  insert into table_name (field1,field2,...) values(value1,value2,...);
  ```

- 给全部字段添加数据

  ```mysql
  insert into table_name values(value1,value2,...);
  ```

- 批量添加数据

  ```mysql
  insert into table_name (field1,field2,...) values(value1,value2,...),(value1,value2,....),...;
  insert into table_name values(value1,value2,...),(value1,value2,..);
  ```

##### 修改数据

- 修改数据

  ```mysql
  update table_name set colum1 = value1,colum2 = value2,...[where confition];
  ```

##### 删除数据

- 删除数据

  ```mysql
  delete from table_name [where condition];
  ```



### DQL

##### DQL-语法

```mysql
select  	--基础查询 
from 			--条件查询
where   	--聚合查询
group by 	--分组查询
having 		
order by 	--排序查询
limit			--分页查询
```

##### DQL-基本查询

- 查询多个字段

  ```mysql
  select field1,field2,... from table_name;
  select * from table_name;
  ```

- 设置别名

  ```mysql
  select field1 [as new_name1],field2 [as new_name2],... from table_name;
  ```

- 去重复记录

  ```mysql
  select distinct field_list from table_name;
  ```

##### DQL-条件查询

- 语法

  ```mysql
  select field_list from table_name where conditions_list;
  ```

- 条件

  |     比较运算符      |                         功能                         |
  | :-----------------: | :--------------------------------------------------: |
  |          >          |                         大于                         |
  |         >=          |                       大于等于                       |
  |          <          |                         小于                         |
  |         <=          |                       小于等于                       |
  |          =          |                         等于                         |
  |      <> 或 !=       |                        不等于                        |
  | BETWEEN ... AND ... |            在某个范围之内（包括min、max）            |
  |       IN(...)       |             在in之后的列表中的值，多选一             |
  |        LIKE         | 模糊匹配(_匹配单个字符，%匹配任意个字符，可组合使用) |
  |       IS NULL       |                是NULL（IS NOT NULL）                 |
  |      AND 或 &&      |                          且                          |
  |     OR 或 \|\|      |                          或                          |
  |       NOT 或!       |                          非                          |



##### DQL-聚合函数

- 将一列数据作为一个整体进行纵向计算

- 常见的聚合函数 (所有的NULL不参与聚合函数查询)

  | 函数  |   功能   |
  | :---: | :------: |
  | count | 统计数量 |
  |  max  |  最大值  |
  |  min  |  最小值  |
  |  avg  |  平均值  |
  |  sum  |   求和   |

##### DQL-分组查询

- 语法

  ```mysql
  select field_list from table_name [where condition] group by group_field_name [having condition]
  ```

- where 和 having 区别

  - 判断时机不同: where 是分组之前进行过滤，不满足where条件，不参与分组，而having 是分组之后进行过滤
  - 判断条件不同: where 不能对聚合函数进行判断，而having可以

- 执行顺序： where > 聚合函数 > having

- 分组之后，查询的字段一般为聚合函数和分组字段，查询其他字段无任何意义

##### DQL-排序查询

- 语法

  ```mysql
  SELECT * FROM table_name ORDER BY age asc; --升序 可省略
  SELECT * FROM table_name ORDER BY age DESC;    --降序
  SELECT * FROM table_name ORDER BY age asc , entrydate ASC; --先按age 再按entrydate
  ```

##### DQL-分页查询

- 语法

  ```mysql
  select * from table_name LIMIT begin , query_num_mark
  ```

- 不同的SQL有不同的此语法  

##### DQL-执行顺序

- ```mysql
  select 						--4
  from							--1
  where 						--2
  group by	having	--3
  order by					--5
  limit							--6
  ```



### DCL

##### DCL-管理用户

- 查询用户

  ```mysql
  use mysql;
  select * from user;
  
  ```

- 创建用户

  ```mysql
  create user 'user_name'@'host_name' IDENTIFIED BY 'password';
  ```

-  修改用户密码

  ```mysql
  alter user 'user_name'@'host_name' IDENTIFIED WITH mysql_native_password BY 'password';
  ```

- 删除用户

  ``` mysql
  drop user 'user_name'@'host_name';
  ```

##### DCL-权限控制

- |        权限        |        说明        |
  | :----------------: | :----------------: |
  | ALL,ALL PRIVILEGES |      所有权限      |
  |       SELECT       |      查询数据      |
  |       INSERT       |      插入数据      |
  |       UPDATE       |      修改数据      |
  |       DELETE       |      删除数据      |
  |       ALTER        |       修改表       |
  |        DROP        | 删除数据库/表/视图 |
  |       CREATE       |   创建数据库/表    |

  查询权限

  ```mysql
  show grants for 'user_name'@'host_name';
  ```

- 授予权限

  ```mysql
  grant 权限列表 ON database_name.table_name from 'user_name'@'host_name';
  ```

- 撤销权限

  ```mysql
  revoke 权限列表 ON database_name.table_name from 'user_name'@'host_name';
  ```

  



## 函数

##### 字符串函数

- 常用的函数

  |           函数           |                          功能                           |
  | :----------------------: | :-----------------------------------------------------: |
  |   CONCAT(S1,S2,...Sn)    |        字符串拼接，将S1,S2,...Sn拼接成一个字符串        |
  |        LOWER(str)        |                         转小写                          |
  |        UPPER(str)        |                         转大写                          |
  |     LPAD(str,n,pad)      | 左填充，用字符串pad对str左边进行填充，以达到n个字符长度 |
  |     RPAD(str,n,pad)      | 右填充，用字符串pad对str右边进行填充，以达到n个字符长度 |
  |        TRIM(str)         |                  去掉字符串头尾的空格                   |
  | SUBSTRING(str,start,len) |          返回字符串str从start起len个长度字符串          |

  

#### 数值函数

- 常用的数值函数

  |    函数    |               功能               |
  | :--------: | :------------------------------: |
  |  CEIL(x)   |             向上取整             |
  |  FLOOR(x)  |             向下取整             |
  |  MOD(x,y)  |           返回x/y的模            |
  |   RAND()   |        返回0～1内的随机数        |
  | ROUND(x,y) | 求参数x的四舍五入值，保留y位小数 |

  

##### 日期函数

- 常用的日期函数

  |               函数                |                       功能                        |
  | :-------------------------------: | :-----------------------------------------------: |
  |             CURDATE()             |                   返回当前日期                    |
  |             CURTIME()             |                   返回当前时间                    |
  |               NOW()               |                返回当前日期和时间                 |
  |            YEAR(date)             |                获取指定date的年份                 |
  |            MOUTH(date)            |                获取指定date的月份                 |
  |             DAY(date)             |                获取指定date的日期                 |
  | DATE_ADD(data,INTERVAL expo type) | 返回一个日期/时间值加上一个时间间隔expr后的时间值 |
  |       DATEDIFF(date1,date2)       |    返回起始时间date1和结束时间date2之间的天数     |

  

##### 流程函数

- 常用的流程控制函数

  |                           函数                           |                       功能                       |
  | :------------------------------------------------------: | :----------------------------------------------: |
  |                      IF(value,t,f)                       |        如果value为true，返回t，否则返回f         |
  |                  IFNULL(value1,value2)                   |     如果value1不为空，返回value1，否则value2     |
  |    CASE WHEN [val1] THEN [res1]...ELSE [default] END     |  如果val1为true，返回res1,...，否则返回default   |
  | CASE [expr] WHEN [val1] THEN [res1]...ELSE [default] END | 如果expr值等于val1，返回res1,...,否则返回default |

   





## 约束

##### 概念

- 约束是作用于表中字段上的规则，用于限制存储在表中的数据

##### 目的

- 保证数据库中数据的正确、有效性和完整性

##### 分类

|   约束   |                        描述                        |   关键字    |
| :------: | :------------------------------------------------: | :---------: |
| 非空约束 |             限制该字段的数据不能为null             |  NOT NULL   |
| 唯一约束 |       保证该字段的所有数据都是唯一、不重复的       |    UNQUE    |
| 主键约束 |      主键是一行数据的唯一标识，要求非空且唯一      | PRIMARY KEY |
| 默认约束 |   保存数据时，如果为制定该字段的值，则采用默认值   |   DEFAULT   |
| 检查约束 |              保证字段值满足某一个条件              |    CHECK    |
| 外键约束 | 用来让两张表之间建立连接，保证数据的一致性和完整性 | FOREIGN KEY |

- 一般约束

```mysql
CREATE Table key_user (
    id INT PRIMARY KEY AUTO_INCREMENT COMMENT 'ID 主键',
    name VARCHAR(10) UNIQUE NOT NULL COMMENT '姓名 非空唯一',
    age INT check(
        age > 0
        and age < 120
    ) COMMENT '年龄 0-120',
    status char(1) DEFAULT '1' COMMENT '状态',
    gender CHAR(1) COMMENT '性别'
) COMMENT '用户表';

INSERT INTO
    key_user(name, age, status, gender)
VALUES
    ('Tom', 19, '1', 'm'),
    ('Jack', 22, '1', 'm'),
    ('Tomas', 21, '0', 'm');

INSERT INTO
    key_user (name, age, status, gender)
VALUES
    ('Mina', 22, '1', 'f'),
    ('Meys', 21, '1', 'f');
    
```

- [ ] 主键自增的正确性怎么保证？



- 外键约束

  - 用来建立两表之间的联系

  - 语法

    ```MYSQL
    create table table_name (
    		name varchar(10),
    		......
    		[constraint] [foreign_key_name] foreign key (外键字段名) references 主表(主表列名)
    );
    ```

    ```mysql
    --添加外键
    alter table table_name add constraint foreign_key_name foreign key (外键字段名) references 主表(主表列名);
    --删除外键
    alter table table_name drop foreign key foreign_key_name;
    ```

  - 删除、更新行为

    |    行为     |                             说明                             |
    | :---------: | :----------------------------------------------------------: |
    |  NO ACTION  | 当在父表中删除/更新对应的记录时，首先检查记录是否有对应的外键，有则不允许删除/更新（= restrict） |
    |  RESTRICT   | 当在父表中删除/更新对应的记录时，首先检查记录是否有对应的外键，有则不允许删除/更新（=no action） |
    |   CASCADE   | 当在父表中删除/更新对应的记录时，首先检查记录是否有对应的外键，有则也删除/更新外键在子表中的记录 |
    |  SET NULL   | 当在父表中删除对应的记录时，首先检查记录是否有对应的外键，有则设置子表中的外键为null |
    | SET DEFAULT |         父表中有变更时，子表将外键列设置成一个默认值         |

    ```
    alter table table_name add constraint 
    ```

## 多表查询

##### 多表关系

- 一对多（多对一）
  - 部门和员工
- 多对多
  - 学生和课程（中间表 $n\times m$）
- 一对一
  - 多用于单表的拆分（提升操作效率）


##### 多表查询概述

- 从多张表中查询数据
- 笛卡尔积
  - 数学中两个集合的组合总数
- 分类
  - 连接查询
    - 内连接：相当于查询集合A、B的交集部分数据
    - 外连接：
      - 左外连接：查询左表所有数据，以及两表交集部分
      - 右外连接：查询右表所有数据，以及两表交集部分
    - 自连接：当前表与自身的连接查询，自连接必须使用表的别名
  - 子查询

##### 内连接

- 隐式内连接

  ```mysql
  select 字段列表 from 表1，表2 where conditions;
  ```

  

- 显式内连接

  ```mysql
  select 字段列表 from 表1 [inner] join 表2  on 连接条件;
  ```

  

##### 外连接

- 左外连接

  ```mysql
  select 字段列表 from 表1 left [outer] join 表2 on conditions;
  ```

  

- 右外连接

  ```mysql
  select 字段列表 from 表1 right [outer] join 表2 on conditions;
  ```

  

##### 自连接

- ```mysql
  select colums from table_name join table_name  on conditions
  ```

  

##### 子查询

- SQL语句中嵌套select语句，为嵌套查询（子查询）

- 结果分类

  - 标量子查询

    - 返回单值（数字、日期、字符串等等）
    - 常见操作符 =,<>,>,>=,<,<=

    

  - 列子查询

    - 返回的结果是一列（可以多行）

    - 操作符：`IN` `NOT IN` `ANY` `SOME` `ALL`

      | 操作符 |                      描述                      |
      | :----: | :--------------------------------------------: |
      |   IN   |          在指定的集合范围之内，多选一          |
      | NOT IN |              不在指定的集合范围内              |
      |  ANY   |       子查询返回列表中，任意一个满足即可       |
      |  SOME  | 与`ANY` 等同，使用`SOME` 的地方都可以使用`ANY` |
      |  ALL   |          子查询返回列表所有值必须满足          |

      

  - 行子查询

    - 返回结果是一行（可多列）
    - 常用操作符：= 、<> 、IN、NOT IN

  - 表子查询

    - 多行多列
    - 常用操作符：IN

- 位置分类

  - where 、from 、select之后



## 事务

简介：事务 是一组操作的集合，它是一个不可分割的工作单位，事务会把所有的操作作为一个整体一起向系统提交或者撤销操作请求，同时成功同时失败

##### 事务操作

- 查看/设置事务提交方式

  ```mysql
  select @@autocommit;
  set @@autocommit = 0;
  ```

  

- 提交事务

  - `commit`

- 回滚事务

  - `rollback`

##### 事务的四大特性

- 原子性(Atomicity)
  - 事务是不可分割的最小操作单元
- 一致性(Consistency)
  - 事务完成时，数据要保持一致
- 隔离性(Isolation)
  - 并发事务不会相互干扰
- 持久性(Durability)
  - 事务一旦提交或回滚，对数据库中的数据的改变就是永久的

##### 并发事务的问题

|    问题    |                             描述                             |
| :--------: | :----------------------------------------------------------: |
|    脏读    |           一个事务读到另外一个事务还没有提交的数据           |
| 不可重复读 |       一个事务先后读取同一记录，但是两次读取的数据不同       |
|    幻读    | 一个事务按照条件查询数据时，没有对应的数据行，但是在插入时，但发现这行数据已经存在了 |

##### 事务的隔离级别

|     隔离级别     | 脏读 | 不可重复读 | 幻读 |
| :--------------: | :--: | :--------: | :--: |
| read uncommitted |  y   |     y      |  y   |
|  read committed  |  n   |     y      |  y   |
| repeatable read  |  n   |     n      |  y   |
|   serializable   |  n   |     n      |  n   |

- 查看事务隔离级别：

  ```mysql
  select @@transaction_isolation; 
  ```

- 设置事务隔离级别：

  ```mysql
  set [session global] transaction isolation level {read uncommitted | read committed | repeatable read | serializable }
  ```

  



