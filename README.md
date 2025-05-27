# 我超级大帅哥pzt
## 这是我的第一个github仓库 
### 希望我可以不断学习 以此成为一个新起点
### 加油各位
```
print(hello Github!!!!!)
```
### 在这里我将会完善一个使用java编写并且使用数据库储存数据的学生管理系统





# Java学生管理系统开发指南

## 核心知识需求

### 1. Java基础
- 面向对象编程（类、对象、继承、多态）
- 集合框架（ArrayList, HashMap等）
- 异常处理
- 输入/输出流

### 2. MySQL数据库
- 数据库设计（表结构、关系）
- SQL语句（CRUD操作）
- JDBC连接数据库
- 数据库连接池（如HikariCP）

### 3. Java与数据库交互
- JDBC API
- PreparedStatement防SQL注入
- 事务管理

### 4. 基础前端（可选）
- 控制台界面或简单Swing GUI
- 或基础HTML/CSS/JavaScript（如果做Web版）

## 推荐学习路径（2个月计划）

| 时间段  | 学习内容     |
| ------- | ------------ |
| 第1-2周 | Java基础巩固 |
| 第3周   | MySQL学习    |
| 第4周   | JDBC连接     |
| 第5-6周 | 系统功能开发 |
| 第7周   | 界面开发     |
| 第8周   | 测试与优化   |

## 数据库设计建议

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    gender CHAR(1),
    birth_date DATE,
    class_id INT,
    phone VARCHAR(20),
    address VARCHAR(100)
);

CREATE TABLE classes (
    class_id INT PRIMARY KEY AUTO_INCREMENT,
    class_name VARCHAR(50) NOT NULL,
    major VARCHAR(50),
    grade INT
);

CREATE TABLE courses (
    course_id INT PRIMARY KEY AUTO_INCREMENT,
    course_name VARCHAR(50) NOT NULL,
    credit FLOAT
);

CREATE TABLE scores (
    score_id INT PRIMARY KEY AUTO_INCREMENT,
    student_id INT,
    course_id INT,
    score FLOAT,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);

CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(100) NOT NULL,
    role VARCHAR(20)  -- admin/teacher/student
);
