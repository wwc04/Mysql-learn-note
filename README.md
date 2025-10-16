# 数据库常用命令

<p> 
  
## DDL（数据定义语言，用来定义数据库对象（数据库，表，字段））
### 数据库
#### --1.查询所有数据库
```jsx title="src/components/HelloDocusaurus.js"
show databases;
```
#### --2.查询当前数据库
```jsx title="src/components/HelloDocusaurus.js"
select database;
```
#### --3.使用/切换数据库
```jsx title="src/components/HelloDocusaurus.js"
use 数据库名;
```
#### --4.创建数据库
```jsx title="src/components/HelloDocusaurus.js"
create database [if not exists] 数据库名 [default charest utf8mb4];
```
#### --5.删除数据库
```jsx title="src/components/HelloDocusaurus.js"
drop database [if exist] 数据库名;
```

## 表
#### --1.表创建
```jsx title="src/components/HelloDocusaurus.js"
create table tablename(
   字段1 字段类型 [约束] [comment 字段1的注解]
   字段2 字段类型 [约束] [comment 字段2的注解]
   ......
)[comment 表注解]
```
 表创建：[表设计](document/resource/mysql_DDL1.png)

<br>

## DML（数据操作语言，用来对数据库表中的数据进行增删改）

<br>

## DQL（数据查询语言，用来查询数据库中的表记录）
