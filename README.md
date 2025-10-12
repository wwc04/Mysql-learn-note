# 数据库常用命令
<p> 
  
## 1. 连接和退出MySQL
### 连接MySQL
mysql -u username -p

### 退出MySQL
exit 或 quit 或 \q

<br>

## 2. 数据库操作
### 显示所有数据库
SHOW DATABASES;

### 创建数据库
CREATE DATABASE database_name;

### 使用数据库
USE database_name;

### 删除数据库
DROP DATABASE database_name;

### 显示当前数据库
SELECT DATABASE();

<br>

## 3. 表操作
### 显示所有表
SHOW TABLES;

### 创建表
CREATE TABLE table_name (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    age INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

### 查看表结构
DESCRIBE table_name;
DESC table_name;

### 删除表
DROP TABLE table_name;

### 重命名表
RENAME TABLE old_name TO new_name;

<br>

## 4. 数据操作（CRUD）
### 插入数据
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
INSERT INTO users (name, age) VALUES ('张三', 25);

### 查询数据
#### 1)查询所有数据
SELECT * FROM table_name;
#### 2)条件查询
SELECT * FROM users WHERE age > 20;
#### 3)选择特定列
SELECT name, age FROM users;
#### 4)排序
SELECT * FROM users ORDER BY age DESC;
#### 5)限制结果数量
SELECT * FROM users LIMIT 10;

### 更新数据
UPDATE table_name SET column1 = value1 WHERE condition;
UPDATE users SET age = 26 WHERE name = '张三';

### 删除数据
DELETE FROM table_name WHERE condition;
DELETE FROM users WHERE id = 1;

<br>

## 5. 常用查询子句
### WHERE 条件
SELECT * FROM users WHERE age BETWEEN 20 AND 30;

### LIKE 模糊查询
SELECT * FROM users WHERE name LIKE '张%';

### IN 查询
SELECT * FROM users WHERE age IN (20, 25, 30);

### GROUP BY 分组
SELECT age, COUNT(*) FROM users GROUP BY age;

### HAVING 分组后过滤
SELECT age, COUNT(*) FROM users GROUP BY age HAVING COUNT(*) > 5;

<br>

## 6. 用户和权限管理
sql
-- 创建用户
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

-- 授予权限
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';

-- 撤销权限
REVOKE ALL PRIVILEGES ON database_name.* FROM 'username'@'localhost';

-- 刷新权限
FLUSH PRIVILEGES;

-- 删除用户
DROP USER 'username'@'localhost';
实用命令
sql
-- 显示MySQL版本
SELECT VERSION();

-- 显示当前用户
SELECT USER();

-- 显示服务器状态
SHOW STATUS;

-- 显示进程列表
SHOW PROCESSLIST;

-- 查看字符集设置
SHOW VARIABLES LIKE 'character_set%';
数据导入导出
sql
-- 导出数据库
mysqldump -u username -p database_name > backup.sql

-- 导入数据库
mysql -u username -p database_name < backup.sql

</P>
