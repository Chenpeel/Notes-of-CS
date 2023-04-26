# SQL分类：

## Table

| 分类 |            全称            |                           说明                           |
| :--: | :------------------------: | :------------------------------------------------------: |
| DDL  |  Data Definition Language  | 数据定义语言，用来定义数据库中的对象（数据库、表、字段） |
| DML  | Data Manipulation Language |      数据操作语言，用来对数据库表中的数据进行增删改      |
| DQL  |    Data Query Language     |          数据查询语言，用来查询数据库中表的记录          |
| DCL  |   Data Control Language    |  数据控制语言，用来创建数据库用户、控制数据库的访问权限  |

# SQL语法：

## DDL

#### 数据库

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

#### 表操作-查询创建

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

#### 表操作-修改

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

#### 表操作-删除

- 删除表

  ```mysql
  drop table if exists table_name;
  ```

- 删除并重新创建

  ```mysql
  truncate table table_name;
  ```

![image-20230422232140753](/Users/alpha/Library/Application Support/typora-user-images/image-20230422232140753.png)

![image-20230422232634397](/Users/alpha/Library/Application Support/typora-user-images/image-20230422232634397.png)

![image-20230422232846561](/Users/alpha/Library/Application Support/typora-user-images/image-20230422232846561.png)

## DML

#### DML-添加数据

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

#### DML-修改数据

- 修改数据

  ```mysql
  update table_name set colum1 = value1,colum2 = value2,...[where confition];
  ```

#### DML-删除数据

- 删除数据

  ```mysql
  delete from table_name [where condition];
  ```



## DQL

#### DQL-语法

```mysql
select  	--基础查询 
from 			--条件查询
where   	--聚合查询
group by 	--分组查询
having 		
order by 	--排序查询
limit			--分页查询
```

#### DQL-基本查询

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

#### DQL-条件查询

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



#### DQL-聚合函数

- 将一列数据作为一个整体进行纵向计算

- 常见的聚合函数 (所有的NULL不参与聚合函数查询)

  | 函数  |   功能   |
  | :---: | :------: |
  | count | 统计数量 |
  |  max  |  最大值  |
  |  min  |  最小值  |
  |  avg  |  平均值  |
  |  sum  |   求和   |

#### DQL-分组查询

- 语法

  ```mysql
  select field_list from table_name [where condition] group by group_field_name [having condition]
  ```

- where 和 having 区别

  - 判断时机不同: where 是分组之前进行过滤，不满足where条件，不参与分组，而having 是分组之后进行过滤
  - 判断条件不同: where 不能对聚合函数进行判断，而having可以

- 执行顺序： where > 聚合函数 > having

- 分组之后，查询的字段一般为聚合函数和分组字段，查询其他字段无任何意义

#### DQL-排序查询

- 语法

  ```mysql
  SELECT * FROM table_name ORDER BY age asc; --升序 可省略
  SELECT * FROM table_name ORDER BY age DESC;    --降序
  SELECT * FROM table_name ORDER BY age asc , entrydate ASC; --先按age 再按entrydate
  ```

#### DQL-分页查询

- 语法

  ```mysql
  select * from table_name LIMIT begin , query_num_mark
  ```

- 不同的SQL有不同的此语法  

#### DQL-执行顺序

- ```mysql
  select 						--4
  from							--1
  where 						--2
  group by	having	--3
  order by					--5
  limit							--6
  ```



## DCL

#### DCL-管理用户

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

#### DCL-权限控制

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

  



# 函数：











