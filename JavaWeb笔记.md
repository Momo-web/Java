# JavaWeb

[TOC]



## JavaWeb整体介绍

![image-20230207110425900](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071104996.png)



![image-20230207110530424](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071105487.png)



## 1.数据库

### 1.数据库相关概念

![ ](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071109338.png)

![image-20230207112013670](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071120737.png)



### 2.MySQL数据库

#### MySQL安装（略）



#### MySQL数据模型

![image-20230207114136562](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071141626.png)



![image-20230207114355071](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071143124.png)



### 3.SQL简介&通用语法&分类

![image-20230207170339217](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071703269.png)



![image-20230207170845112](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071708149.png)



![image-20230207170908494](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071709544.png)

![image-20230207171135384](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302071711454.png)



### 4.DDL - 数据定义语言

![image-20230207210705100](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072107158.png)

 ![image-20230207211647474](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072116507.png)



![image-20230207211924520](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072119553.png)



![image-20230207212346739](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072123776.png)



![image-20230207213642826](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072136859.png)





![image-20230207213440033](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072134158.png)





![image-20230207213706123](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072137162.png)



```mysql
CREATE TABLE student(
	id INT PRIMARY KEY AUTO_INCREMENT,
	`name` VARCHAR(10),
	sex CHAR(1),
	birthday DATE,
	score DOUBLE(5,2),
	email VARCHAR(64),
	phone VARCHAR(64),
	state TINYINT);
	
DESC student;
```



![image-20230207214618387](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072146410.png)



![image-20230207214717074](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072147106.png)



![image-20230207214939845](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072149896.png)

### 5.Navicat安装使用（略）

![image-20230207215717407](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072157455.png)

### 6.DML - 数据操作语言

![image-20230207220529181](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072205211.png)

![image-20230207220550428](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072205486.png)



```mysql
-- 给指定列添加数据 
-- INSERT INTO 表名(列名1,列名2,...) VALUES(值1,值2,...);
INSERT INTO student ( id, `name` )
VALUES
	( 1, "小天" );
ALTER TABLE student RENAME TO stu;
SELECT
	* 
FROM
	stu;-- 给所有列添加数据
INSERT INTO stu
VALUES
	( 3, "smith", "男", "1998-1-2", 20.98, "123@gmail.com", "123654321", 1 ),
	( 4, "jack", "男", "1996-9-2", 99.98, "123@gmail.com", "123654321", 1 ),
	( 5, "tom", "男", "1997-5-26", 27.98, "123@gmail.com", "123654321", 2 );
```



![image-20230207222433629](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072224668.png)

```mysql
-- 将jack性别修改为女
UPDATE stu 
SET sex = "女" 
WHERE
	`name` = "jack";-- 将tom生日改为1999-3-3，分数改为99.99
UPDATE stu 
SET birthday = "1999-3-3",
score = 99.99 
WHERE
	`name` = "tom";-- 注意，如果update没有加入条件，则修改所有记录
SELECT
	* 
FROM
	stu;
```



![image-20230207223235864](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302072232900.png)

```mysql
-- 删除momo的记录
DELETE FROM stu WHERE `name` = "momo";
```



### 7.DQL - 数据查询语言

![image-20230208104642656](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081046726.png)



![image-20230208104718179](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081047225.png)



```mysql
CREATE TABLE stu(
id int,
`name` VARCHAR(20),
age int,
sex VARCHAR(5),
address VARCHAR(100),
math DOUBLE(5,2),
english DOUBLE(5,2),
hire_date date);

INSERT INTO stu(id,`name`,age,sex,address,math,english,hire_date)
VALUES
(1,"马云",55,"男","杭州",66,78,"1995-09-01"),
(2,"马化腾",55,"女","深圳",98,87,"1998-09-01"),
(3,"马什克",55,"男","香港",56,78,"1999-09-02"),
(4,"六百",55,"男","湖南",76,65,"1997-09-05"),
(5,"刘庆",55,"女","湖南",86,NULL,"1998-09-01"),
(6,"柳大华",55,"男","香港",99,99,"1998-09-01"),
(7,"张学友",55,"男","香港",99,99,"1998-09-01"),
(8,"德玛西亚",55,"男","南京",56,65,"1994-09-02");

SELECT * FROM stu;

-- 基础查询

-- 查询name age 两列
SELECT `name`,age FROM stu;

-- 查询所有
SELECT * FROM stu;

-- 查询地址 去重
SELECT DISTINCT address FROM stu;

SELECT * from stu;

-- 查询姓名、数学成绩、英语成绩 起别名
SELECT `name`,math as 数学成绩,english as 英语成绩 FROM stu;
```

![image-20230208110758148](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081107181.png)



![image-20230208144635825](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081446881.png)



```mysql
-- 条件查询

SELECT * FROM stu;

-- 1.查询年龄大于20岁的学员信息
SELECT * FROM stu WHERE age > 20;

-- 2.查询年龄大于等于20岁的学员信息
SELECT * FROM stu WHERE age >= 20;

-- 3.查询年龄大于等于20岁并且年龄小于等于30岁的学员信息
SELECT * FROM stu WHERE age >= 20 AND age <= 30;
SELECT * FROM stu WHERE age BETWEEN 20 AND 30;

-- 4.查询入学日期在1998-09-01 到 1999-9-1之间的学员信息
SELECT * FROM stu WHERE hire_date BETWEEN "1998-9-1" AND "1999-9-1";

-- 5.查询年龄等于18岁的学员信息
SELECT * from stu WHERE age = 18;

-- 6.查询年龄不等于18岁的学员信息
SELECT * FROM stu WHERE age != 18;

-- 7.查询年龄等于18岁或者年龄等于20岁或者年龄等于22岁的学员信息
SELECT * FROM stu WHERE age IN(20,18,55);

-- 8.查询英语成绩为null的学员信息
SELECT * FROM stu WHERE english IS NULL;

-- 模糊查询

/*
  通配符：
	1._代表单个任意字符
	2.%代表任意个数字符
*/

-- 1.查询姓“马”的学员信息
SELECT * FROM stu WHERE `name` LIKE "马%";

-- 2.查询第二个字是“化”的学员信息
SELECT * FROM stu WHERE `name` LIKE "_化%";

-- 3.查询名字中包含”大“的学员信息
SELECT * FROM stu WHERE `name` LIKE "%大%";
```



![image-20230208152530752](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081525805.png)

```mysql
/* 排序方式：
		* ASC:升序排列（默认值）
		* DESC:降序排列
*/

-- 1.查询学生信息，按照年龄升序排列
SELECT * FROM stu ORDER BY age asc;

-- 2.查询学生信息，按照数学成绩降序排列
SELECT * FROM stu ORDER BY math DESC;

-- 3.查询学生信息，按照数学成绩降序排列，如果一样则按照英语成绩升序排列
SELECT * FROM stu ORDER BY math desc,english asc;
```



![image-20230208153807131](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081538194.png)



 ```mysql
 -- 聚合函数
 
 -- count():统计数量
 -- 取值：
 -- 1.主键
 -- 2.*
 
 -- 1.统计班级一共有多少个学生
 SELECT COUNT(*) FROM stu;-- count()统计的列名不能为null
 
 -- 2.查询数学成绩的最高分
 SELECT MAX(math) FROM stu;
 
 -- 3.查询数学成绩最低分
 SELECT MIN(math) FROM stu;
 
 -- 4.查询数学成绩总分
 SELECT SUM(math) FROM stu;
 
 -- 5.查询数学成绩平均分
 SELECT AVG(math) FROM stu;
 
 -- 6.查询英语成绩最低分
 SELECT MIN(english) FROM stu;-- 所有聚合函数，null值不参与运算
 ```



![image-20230208155059253](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081550309.png)

```mysql
/* 
	分组函数
*/

-- 1.查询男同学和女同学各自的数学平均分
SELECT sex,AVG(math) FROM stu GROUP BY sex;
-- 分组之后，查询的字段为聚合函数和分组字段，查询其他字段无任何意义

-- 2.查询男同学和女同学各自的数学平均分，以及各自人数
SELECT sex,COUNT(*) as 人数,AVG(math)   FROM stu GROUP BY sex;

-- 3.查询男同学和女同学各自的数学平均分，以及各自人数：要求：分数低于70分的不参与分组
SELECT sex,COUNT(*) as 人数,AVG(math)   FROM stu WHERE math >= 70 GROUP BY sex;

-- 4.查询男同学和女同学各自的数学平均分，以及各自人数：要求：分数低于70分的不参与分组，
SELECT sex,COUNT(*) as 人数,AVG(math)   FROM stu WHERE math >= 70 GROUP BY sex HAVING COUNT(*) > 2;
```



![image-20230208181053703](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081810759.png)

```mysql
-- 分页查询

SELECT * FROM stu;

-- 1.从0开始查询，查询3条数据
SELECT * FROM stu LIMIT 0,3;

-- 2.每页显示3条数据，查询第一页数据
SELECT * FROM stu LIMIT 0,3;

-- 3.每页显示3条数据，查询第二页数据
SELECT * FROM stu LIMIT 3,3;

-- 4.每页显示3条数据，查询第三页数据
SELECT * FROM stu LIMIT 6,3;

-- 起始索引 = （当前页码 - 1） * 每页显示条数
```



**小结**

![image-20230208182435592](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081824658.png)





![image-20230208182546803](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081825853.png)



![image-20230208182740528](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081827583.png)



![image-20230208182916766](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081829812.png)



![image-20230208183110458](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081831529.png)



![image-20230208183232222](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081832295.png)



![image-20230208183417194](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081834243.png)



![image-20230208183539586](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081835631.png)



![image-20230208183604124](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081836168.png)



### 8.约束

#### 1.约束概念&分类

![image-20230208184835269](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081848342.png)



#### 2.非空约束

![image-20230208191840056](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081918112.png)



#### 3.唯一约束

![image-20230208192029834](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081920891.png)



#### 4.主键约束

![image-20230208192055178](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081920235.png)



#### 5.默认约束

![image-20230208192133939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081921993.png)



![image-20230208185421214](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081854266.png)

```mysql
--约束

CREATE TABLE emp(
	id INT PRIMARY KEY auto_increment,
	ename varchar(50) NOT NULL UNIQUE,
	joindate DATE NOT NULL,
	salary DOUBLE(7,2) NOT NULL,
	bonus DOUBLE(7,2) NOT NULL DEFAULT 0);
	
	SELECT * FROM emp;
	
-- 演示主键约束，非空且唯一
	
	INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(1,"张三","1999-11-11",8800,5000);
	
	INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(null,"张三","1999-11-11",8800,5000);
	
		INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(1,"张三","1999-11-11",8800,5000);
		
		INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(2,"李四","1999-11-11",8800,5000);
		
-- 演示非空约束
	INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(null,"张三","1999-11-11",8800,5000);

-- 演示唯一约束
		INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(1,"张三","1999-11-11",8800,5000);
		
-- 演示默认约束
		INSERT INTO emp(id,ename,joindate,salary) VALUES(3,"王五","1999-11-11",8800);
		
		INSERT INTO emp(id,ename,joindate,salary,bonus) VALUES(4,"胡琪","1999-11-11",8800,NULL);
		
-- 自增长：auto_increment 数字类型且为唯一约束
```



#### 6.外键约束

![image-20230208192229813](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081922862.png)

![image-20230208195128590](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302081951672.png)



```mysql
-- 外键约束

-- 部门表
CREATE TABLE dept(
	id INT PRIMARY KEY auto_increment,
	dep_name VARCHAR(20),
	addr VARCHAR(20));
	
	
DROP TABLE if EXISTS emp;

-- 员工表
CREATE TABLE emp(
	id int PRIMARY KEY auto_increment,
	`name` VARCHAR(20),
	age int,
	dep_id INT,
	-- 添加外键
	CONSTRAINT fk_emp_dept FOREIGN KEY(dep_id) REFERENCES dept(id));
	
-- 添加两个部门
INSERT INTO dept(dep_name,addr) VALUES("研发部","广州"),("销售部","深圳");

-- 添加员工，dep_id表示员工所在部门
INSERT INTO emp(`name`,age,dep_id) VALUES
("张三",20,1),
("李四",20,1),
("王五",20,1),
("赵六",20,2),
("孙琪",22,2),
("周八",18,2);

SELECT * FROM emp;

SELECT * FROM dept;

DROP TABLE if EXISTS dept;

DROP TABLE if EXISTS emp;

-- 删除外键
ALTER TABLE emp DROP FOREIGN KEY fk_emp_dept;

-- 添加外键（建完表后）
ALTER TABLE emp add CONSTRAINT fk_emp_dept FOREIGN KEY(dep_id) REFERENCES dept(id);
```



### 9.数据库设计

#### 1.数据库设计简介

![image-20230209104134872](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091041971.png)



#### 2.表关系之一对多

![image-20230209104427976](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091044016.png)

![image-20230209104440403](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091044442.png)



![image-20230209105212352](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091052400.png)



#### 3.表关系之多对多

![image-20230209104607615](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091046645.png)



![image-20230209104618183](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091046228.png)

![image-20230209105929090](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091059161.png)

```mysql
-- 订单表
CREATE TABLE tb_order(
	id INT primary KEY auto_increment,
	payment DOUBLE(10,2),
	payment_type TINYINT,
	status TINYINT);
	
-- 商品表
CREATE TABLE tb_goods(
	id INT PRIMARY KEY auto_increment,
	title VARCHAR(100),
	price DOUBLE(10,2));
	
-- 订单商品中间表
CREATE TABLE tb_order_goods(
	id int PRIMARY KEY auto_increment,
	order_id int,
	goods_id int,
	count INT);
	
-- 添加外键

ALTER TABLE tb_order_goods add CONSTRAINT fk_order_id FOREIGN KEY(order_id) REFERENCES tb_order(id);

ALTER TABLE tb_order_goods ADD CONSTRAINT fk_goods_id FOREIGN KEY(goods_id) REFERENCES tb_goods(id);

ALTER TABLE tb_order_goods drop FOREIGN KEY fk_order_goods;
```



#### 4.表关系之一对一

![image-20230209104904392](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091049426.png)



![image-20230209104914489](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091049550.png)

![image-20230209112348850](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091123927.png)



![image-20230209105007390](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091050441.png)



![image-20230209112445277](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091124330.png)

#### 5.数据库设计案例

   ![image-20230209134542215](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091345296.png)



![image-20230209134613455](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091346515.png)



![image-20230209134643970](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091346009.png)



![image-20230209134717197](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091347236.png)



![image-20230209134732351](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091347398.png)



```mysql
-- 案例分析

-- 音乐专辑表名 Music
CREATE TABLE music(
	id INT PRIMARY KEY auto_increment,
	title VARCHAR(32),
	alias VARCHAR(32),
	image VARCHAR(64),
	style VARCHAR(8),
	type VARCHAR(4),
	medium VARCHAR(4),
	publish_time date,
	publisher VARCHAR(16),
	number TINYINT,
	barcode BIGINT,
	summary VARCHAR(1024),
	artist VARCHAR(16));
	
-- 曲目表名 Song
CREATE TABLE song(
	id INT PRIMARY KEY auto_increment,
	name VARCHAR(32),
	serial_number TINYINT);

-- 评论表名 Review
CREATE TABLE review(
	content VARCHAR(256),
	rating TINYINT,
	review_time DATETIME);
	
-- 用户表名 User
CREATE TABLE user(
	id int PRIMARY KEY auto_increment,
	username VARCHAR(16),
	image VARCHAR(64),
	signature VARCHAR(64),
	nickname VARCHAR(16));
	
-- 专辑1 —— 曲目m
ALTER TABLE song add music_id int;

SELECT * FROM song;

ALTER TABLE song add CONSTRAINT fk_music_song FOREIGN KEY(music_id) REFERENCES music(id);

-- 专辑m —— 用户m
-- 建立中间表 music_user
CREATE TABLE music_user(
	id int PRIMARY KEY auto_increment,
	music_id int,
	user_id int);
	
	
ALTER TABLE music_user ADD CONSTRAINT fk_music_id FOREIGN KEY(music_id) REFERENCES music(id);

ALTER TABLE music_user ADD CONSTRAINT fk_user_id FOREIGN KEY(user_id) REFERENCES user(id);

-- 专辑1 —— 短评m
alter TABLE review add music_id int;

ALTER TABLE review add CONSTRAINT fk_music_review FOREIGN KEY(music_id) REFERENCES music(id);


-- 用户1 —— 短评m
ALTER TABLE review add user_id int;

ALTER TABLE review add CONSTRAINT fk_user_review FOREIGN KEY(user_id) REFERENCES user(id);

```

![image-20230209141837523](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091418578.png)



### 10.多表查询

![image-20230209145355519](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091453575.png)

#### 1.内连接&外连接

![image-20230209145557699](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091455766.png)

```mysql
-- 隐式内连接
SELECT * FROM emp,dept WHERE emp.dept_id = dept.did;

-- 查询emp的name，gender，dept表的dname
SELECT emp.`name`,emp.gender,dept.dname FROM emp,dept WHERE emp.dept_id = dept.did;

SELECT t1.`name`,t1.gender,t2.dname FROM emp t1,dept t2 WHERE t1.dept_id = t2.did;

-- 显示内连接
SELECT * FROM emp INNER JOIN dept on emp.dept_id = dept.did;
```



![image-20230209150346606](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091503668.png)



```mysql
-- 左外链接
-- 查询emp表所有数据和对应的部门信息
SELECT * FROM emp LEFT JOIN dept on emp.dept_id = dept.did;


-- 右外链接
-- 查询dept表所有数据和对应的员工信息
SELECT * FROM emp RIGHT JOIN dept on emp.dept_id = dept.did;
```



#### 2.子查询



![image-20230209151444068](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091514118.png)

```mysql
-- 子查询（嵌套查询）
-- 查询工资高于猪八戒的员工信息

SELECT name,salary from emp WHERE name = "猪八戒";

SELECT * FROM emp WHERE salary > (SELECT salary from emp WHERE name = "猪八戒"); 

```

![image-20230209152325356](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091523395.png)

![image-20230209152157134](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302091521195.png)

```mysql
-- 查询财务部和市场部所有员工信息
SELECT did FROM dept WHERE dname = "财务部" or dname = "市场部";

SELECT * FROM emp WHERE dept_id in (SELECT did FROM dept WHERE dname = "财务部" or dname = "市场部");

-- 查询入职日期是"2011-11-11"之后的员工信息和部门信息
SELECT * FROM emp where join_date > "2011-11-11";

SELECT * FROM (SELECT * FROM emp where join_date > "2011-11-11") as temp,dept WHERE temp.dept_id = dept.did;
```





#### 3.案例

![image-20230209220358441](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302092203489.png)



```mysql
-- 多表查询练习
drop table if EXISTS emp;
DROP TABLE IF EXISTS dept;
DROP TABLE IF EXISTS job;
DROP TABLE IF EXISTS salarygrade;

-- 部门表
CREATE TABLE dept(
	id int PRIMARY KEY,
	dname VARCHAR(50),
	loc VARCHAR(50));

-- 职务表
CREATE TABLE job(
	id int PRIMARY KEY,
	jname VARCHAR(20),
	description VARCHAR(50)
	);
	
-- 员工表
CREATE TABLE emp(
	id int PRIMARY KEY,
	ename VARCHAR(50),
	job_id int,
	mgr int,
	joindate date,
	salary DECIMAL(7,2),
	bonus DECIMAL(7,2),
	dept_id int,
	CONSTRAINT emp_jobid_ref_job_id_fk FOREIGN KEY(job_id) REFERENCES job(id),
	CONSTRAINT emp_deptid_ref_dept_id_fk FOREIGN KEY(dept_id) REFERENCES dept(id));
	
-- 工资等级表
CREATE TABLE salarygrade(
	grade int PRIMARY KEY,
	losalary int,
	hisalary int);
	
-- 添加4个部门
INSERT into dept(id,dname,loc) VALUES
(10,"教研部","北京"),
(20,"学工部","上海"),
(30,"销售部","广州"),
(40,"财务部","深圳");

-- 添加4个职务
INSERT INTO job(id,jname,description) VALUES
(1,"董事长","管理整个公司，接单"),
(2,"经理","管理部门员工"),
(3,"销售员","向客人推销产品"),
(4,"文员","使用办公软件");

-- 添加员工
INSERT INTO emp(id,ename,job_id,mgr,joindate,salary,bonus,dept_id) VALUES
(1001,"孙悟空",4,1004,"2000-12-17","8000.00",NULL,20),
(1002,"卢俊义",3,1006,"2001-02-20","16000.00","3000.00",30),
(1003,"林冲",3,1006,"2001-02-22","12500.00","5000.00",30),
(1004,"唐僧",2,1009,"2001-04-02","29750.00",NULL,20),
(1005,"李逵",4,1006,"2001-09-28","12500.00","14000.00",30),
(1006,"宋江",2,1009,"2001-05-01","28500.00",NULL,20),
(1007,"刘备",2,1009,"2001-09-01","24500.00",NULL,10),
(1008,"猪八戒",4,1004,"2007-04-19","30000.00",NULL,20),
(1009,"罗贯中",1,NULL,"2001-11-17","50000.00",NULL,10),
(1010,"吴用",3,1006,"2001-09-08","15000.00","0.00",30),
(1011,"沙僧",4,1004,"2007-05-23","11000.00",NULL,20),
(1012,"李逵",4,1006,"2001-12-03","9500.00",NULL,30),
(1013,"小白龙",4,1004,"2001-12-03","30000.00",NULL,20),
(1014,"关羽",4,1007,"2002-01-23","13000.00",NULL,10);

-- 添加5个工资等级
INSERT into salarygrade(grade,losalary,hisalary) VALUES
(1,10000,12000),
(2,12010,14000),
(3,14010,16000),
(4,16010,20000),
(5,30010,99990);

-- 1.查询所有员工信息，查询员工编号，员工姓名，工资，职务名称，职务描述
/*
		员工编号，员工姓名，工资 emp表
		职务名称，职务描述 job表
		
*/

-- 隐式内连接
SELECT emp.id,emp.ename,emp.salary,job.jname,job.description FROM emp,job WHERE emp.job_id = job.id;

-- 显示内连接
SELECT emp.id,emp.ename,emp.salary,job.jname,job.description FROM emp INNER JOIN job ON emp.job_id = job.id;

-- 2.查询员工编号，员工姓名，工资，职务名称，职务描述，部门名称，部门位置
/*
		员工编号，员工姓名，工资 emp表
		职务名称，职务描述 job表
		部门名称，部门位置 dept表
		
*/
-- 隐式内连接
SELECT
	emp.id,
	emp.ename,
	emp.salary,
	job.jname,
	job.description,
	dept.dname,
	dept.loc 
FROM
	job,
	dept,
	emp 
WHERE
	emp.dept_id = dept.id 
	AND emp.job_id = job.id;
	
-- 显示内连接
SELECT
	emp.id,
	emp.ename,
	emp.salary,
	job.jname,
	job.description,
	dept.dname,
	dept.loc 
FROM
	emp
	INNER JOIN
	job ON emp.job_id = job.id
	INNER JOIN
	dept ON emp.dept_id = dept.id;

-- 3.查询员工姓名，工资，工资等级
drop table salarygrade;

SELECT salary FROM emp;
SELECT emp.ename,emp.salary,salarygrade.grade FROM emp,salarygrade WHERE emp.salary BETWEEN losalary AND hisalary;

-- 4.查询员工姓名，工资，职务名称，职务描述，部门名称，部门位置，工资等级
SELECT
	emp.id,
	emp.ename,
	emp.salary,
	job.jname,
	job.description,
	dept.dname,
	dept.loc,
	salarygrade.grade 
FROM
	job,
	dept,
	emp,
	salarygrade 
WHERE
	emp.dept_id = dept.id 
	AND emp.job_id = job.id
	AND emp.salary BETWEEN losalary AND hisalary;


-- 5.查询出部门编号，部门名称，部门位置，部门人数
SELECT * FROM dept;
SELECT dept.id,dept.dname,dept.loc,count(*) FROM emp,dept WHERE emp.dept_id = dept.id GROUP BY emp.dept_id;
	
```





### 11.事务

#### 1.事务简介

![image-20230209225416660](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302092254759.png)





#### 2.事务操作

```mysql
DROP TABLE IF EXISTS account;

-- 创建账户表
CREATE TABLE account(
	id int PRIMARY KEY auto_increment,
	name VARCHAR(10),
	money DOUBLE(10,2));
	
-- 添加数据
INSERT into account(name,money) VALUES("张三",1000);
INSERT into account(name,money) VALUES("李四",1000);

SELECT * FROM account;

-- 转账操作
-- 1.查询李四余额
-- 2.李四金额 -500
-- 3.张三余额 +500

-- 开启事务
BEGIN;

UPDATE account set money = money - 500  WHERE name = "李四";

-- 123abc

UPDATE account set money = money + 500  WHERE name = "张三";

-- 提交事务
COMMIT;

-- 回滚事务
ROLLBACK;
```





#### 3.事务四大特征

![image-20230209231014026](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302092310083.png)

![image-20230209231101739](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302092311794.png)

```mysql
-- 1.查询事务的默认提交方式
SELECT @@autocommit;
-- 2.修改事务的提交方式 手动提交
set @@autocommit = 0;
```





## 2.JDBC

![image-20230210101413721](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101014811.png)



#### 1.JDBC简介

![image-20230210103553690](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101035796.png)



#### 2.JDBC快速入门

![image-20230210104016447](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101040519.png)

```java
package com.itheima.jdbc;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

/**
 * @author momo~
 * @version 1.0
 * jdbc快速入门
 */
public class JDBCDemo {
    public static void main(String[] args) throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.jdbc.Driver");

        //在mysql-connector-java 5以后的版本中(不包括5)
        // 使用的都是com.mysql.cj.jdbc.Driver
        Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        String url = "jdbc:mysql://127.0.0.1:3306/exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //3.定义sql
        String sql = "update account set money = 2000 where id = 1";

        //4.获取执行sql对象Statement
        Statement statement = connection.createStatement();

        //5.执行sql
        int count = statement.executeUpdate(sql);

        //6.处理结果
        System.out.println(count);

        //7.释放资源
        statement.close();
        connection.close();
    }
}
```





#### 3.JDBC API详解

##### DriverManager

![image-20230210132813607](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101328650.png)

###### 1.注册驱动

![image-20230210131432515](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101314592.png)



![image-20230210111107397](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101111453.png)

![image-20230210131807392](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101318437.png)



###### 2.获取连接

![image-20230210131705783](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101317847.png)

![image-20230210132903207](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101329282.png)



##### Connection

![image-20230210132939180](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101329221.png)



###### 1.获取执行SQL的对象

![image-20230210133211004](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101332061.png)



###### 2.事务管理

![image-20230210133436818](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101334886.png)



```java
        try {

            //开启事务
            connection.setAutoCommit(false);

            //5.执行sql
            int count1 = statement.executeUpdate(sql1);

            //6.处理结果
            System.out.println(count1);

            //异常
            int i = 3/0;

            //5.执行sql
            int count2 = statement.executeUpdate(sql2);

            //6.处理结果
            System.out.println(count2);

            //提交事务
            connection.commit();

        } catch (Exception e) {
            //回滚事务
            connection.rollback();

            throw new RuntimeException(e);
        }
```



##### Statement

![image-20230210134657624](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101346685.png)



```java
    //执行DML语句
    @Test
    public void testDML() throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.jdbc.Driver");

        //在mysql-connector-java 5以后的版本中(不包括5)
        // 使用的都是com.mysql.cj.jdbc.Driver
        //Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        //如果连接的是本机mysql并且端口是默认的3306可以简化书写
        String url = "jdbc:mysql:///exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //3.定义sql
        String sql = "update account set money = 3300 where id = 1";

        //4.获取执行sql对象Statement
        Statement statement = connection.createStatement();

        //5.执行sql
        int count = statement.executeUpdate(sql);
        //count 修改完成后受影响行数

        //6.处理结果
        //System.out.println(count);
        if (count > 0){
            System.out.println("修改成功");
        } else {
            System.out.println("修改失败");
        }

        //7.释放资源
        statement.close();
        connection.close();
    }


    //执行DDL语句
    @Test
    public void testDDL() throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.jdbc.Driver");

        //在mysql-connector-java 5以后的版本中(不包括5)
        // 使用的都是com.mysql.cj.jdbc.Driver
        //Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        //如果连接的是本机mysql并且端口是默认的3306可以简化书写
        String url = "jdbc:mysql:///exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //3.定义sql
        String sql = "CREATE DATABASE exercise02 ";

        //4.获取执行sql对象Statement
        Statement statement = connection.createStatement();

        //5.执行sql
        int count = statement.executeUpdate(sql);
        //count 修改完成后受影响行数

        //6.处理结果
        System.out.println(count);
//        if (count > 0){
//            System.out.println("修改成功");
//        } else {
//            System.out.println("修改失败");
//        }

        //7.释放资源
        statement.close();
        connection.close();
    }
```



##### ResultSet

![image-20230210140405628](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101404711.png)



![image-20230210140603241](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101406299.png)

```java
package com.itheima.jdbc;

import org.junit.jupiter.api.Test;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

/**
 * @author momo~
 * @version 1.0
 * jdbc API 详解 ResultSet
 */
public class JDBCDemo5_ResultSet {

    /*
      执行DQL
     */
    @Test
    public void testResultSet() throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.jdbc.Driver");

        //在mysql-connector-java 5以后的版本中(不包括5)
        // 使用的都是com.mysql.cj.jdbc.Driver
        //Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        //如果连接的是本机mysql并且端口是默认的3306可以简化书写
        String url = "jdbc:mysql:///exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //3.定义SQL
        String sql = "select * from account";

        //4.获取statement对象
        Statement statement = connection.createStatement();

        //5.执行SQL
        ResultSet resultSet = statement.executeQuery(sql);

        //6.处理结果
        //6.1 光标向下移动一行，并且判断当前行是否有数据
//        while (resultSet.next()){
//            //6.2 获取数据 getXxx()
//            int id = resultSet.getInt(1);
//            String name = resultSet.getString(2);
//            double money = resultSet.getDouble(3);
//
//            System.out.println(id);
//            System.out.println(name);
//            System.out.println(money);
//
//            System.out.println("---------");
//        }

        while (resultSet.next()){
            //6.2 获取数据 getXxx()
            int id = resultSet.getInt("id");
            String name = resultSet.getString("name");
            double money = resultSet.getDouble("money");

            System.out.println(id);
            System.out.println(name);
            System.out.println(money);

            System.out.println("---------");
        }

        //7.关闭资源
        resultSet.close();
        statement.close();
        connection.close();
    }
}

```

![image-20230210141716145](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101417206.png)





![image-20230210141739498](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101417559.png)







```java
/*
      1.定义实体类Account
      2.查询数据，封装到Account中
      3.将Accout对象存入ArrayList集合中
     */
    @Test
    public void testResultSet2() throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.jdbc.Driver");

        //在mysql-connector-java 5以后的版本中(不包括5)
        // 使用的都是com.mysql.cj.jdbc.Driver
        //Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        //如果连接的是本机mysql并且端口是默认的3306可以简化书写
        String url = "jdbc:mysql:///exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //3.定义SQL
        String sql = "select * from account";

        //4.获取statement对象
        Statement statement = connection.createStatement();

        //5.执行SQL
        ResultSet resultSet = statement.executeQuery(sql);

        //6.处理结果
        //6.1 光标向下移动一行，并且判断当前行是否有数据
//        while (resultSet.next()){
//            //6.2 获取数据 getXxx()
//            int id = resultSet.getInt(1);
//            String name = resultSet.getString(2);
//            double money = resultSet.getDouble(3);
//
//            System.out.println(id);
//            System.out.println(name);
//            System.out.println(money);
//
//            System.out.println("---------");
//        }

        //创建集合
        List<Account> list = new ArrayList<>();

        while (resultSet.next()){

            Account account = new Account();

            //6.2 获取数据 getXxx()
            int id = resultSet.getInt("id");
            String name = resultSet.getString("name");
            double money = resultSet.getDouble("money");

            //赋值
            account.setId(id);
            account.setName(name);
            account.setMoney(money);

            //存入集合
            list.add(account);
        }

        System.out.println(list);

        //7.关闭资源
        resultSet.close();
        statement.close();
        connection.close();
    }
```

![image-20230210143315020](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101433077.png)



##### PreparedStatement

![image-20230210143430889](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101434982.png)



![image-20230210144037205](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101440267.png)



![image-20230210150651333](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101506405.png)



![image-20230210151017844](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101510935.png)



```java
@Test
    public void testPreparedStatement() throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        //如果连接的是本机mysql并且端口是默认的3306可以简化书写
        String url = "jdbc:mysql:///exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //接收用户输入
        String name = "zhangsan";
        String pwd = "' or ' 1 ' = ' 1 ";

        //定义SQL
        String sql = "select * from tb_user where username = ? and password = ?";

        //获取Prepare
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        //设置?的值
        preparedStatement.setString(1,name);
        preparedStatement.setString(2,pwd);

        ResultSet resultSet = preparedStatement.executeQuery();

        //判断登录是否成功
        if (resultSet.next()){
            System.out.println("登录成功");
        } else {
            System.out.println("登录失败");
        }

        //7.关闭资源
        resultSet.close();
        preparedStatement.close();
        connection.close();
    }




/*
        演示sql注入
     */
    @Test
    public void testLogin_Inject() throws Exception {
        //1.注册驱动
        //Class.forName("com.mysql.cj.jdbc.Driver");

        //2.获取连接
        //如果连接的是本机mysql并且端口是默认的3306可以简化书写
        String url = "jdbc:mysql:///exercise01";
        String username = "root";
        String password = "root";
        Connection connection = DriverManager.getConnection(url, username, password);

        //接收用户输入
        String name = "zsadfafaf";
        String pwd = "' or ' 1 ' = ' 1 ";

        String sql = "select * from tb_user where username = '"+ name +"' and password = '"+ pwd + "'";

        Statement statement = connection.createStatement();

        ResultSet resultSet = statement.executeQuery(sql);

        //判断登录是否成功
        if (resultSet.next()){
            System.out.println("登录成功");
        } else {
            System.out.println("登录失败");
        }

        //7.关闭资源
        resultSet.close();
        statement.close();
        connection.close();
    }
```



![image-20230210153435206](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101534291.png)



#### 4.数据库连接池

![image-20230210153547064](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101535144.png)



![image-20230210154158323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101541387.png)



![image-20230210154251598](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101542654.png)

```java
package com.itheima.Druid;

import com.alibaba.druid.pool.DruidDataSourceFactory;

import javax.sql.DataSource;
import java.io.FileInputStream;
import java.sql.Connection;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 演示数据库连接池 Druid德鲁伊
 */
public class DruidDemo {
    public static void main(String[] args) throws Exception {
        //1.导入jar包

        //2.定义配置文件

        //3.加载配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src/com/itheima/druid.properties"));

        //4.获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        //5.获取对应数据库连接
        Connection connection = dataSource.getConnection();

        System.out.println(connection);
    }
}

```

![image-20230210160232063](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101602112.png)



#### 5.JDBC练习

![image-20230210160330850](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302101603911.png)



![image-20230210205742794](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302102057856.png)

```mysql
-- 删除tb_brand表
DROP TABLE if EXISTS tb_brand;

-- 创建tb_brand表
CREATE TABLE tb_brand(
	id INT PRIMARY KEY auto_increment,
	brand_name VARCHAR(20),
	company_name VARCHAR(20),
	ordered INT,
	desciption VARCHAR(100),
	status INT);
	
-- 添加数据
INSERT into tb_brand(brand_name,company_name,ordered,desciption,status) VALUES
("三只松鼠","三只松鼠股份有限公司",5,"好吃不上火",0),
("华为","华为技术有限公司",100,"华为致力于把数字世界带千家万户",1),
("小米","小米科技有限公司",50,"are you ok",1);

SELECT * FROM tb_brand;
```



```java
package com.itheima.pojo;

/**
 * @author momo~
 * @version 1.0
 * 品牌
 *
 * alt + 鼠标左键，整列编辑
 */
public class Brand {
    private Integer id;
    private String brandName;
    private String companyName;
    private Integer ordered;
    private String description;
    private Integer status;

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getBrandName() {
        return brandName;
    }

    public void setBrandName(String brandName) {
        this.brandName = brandName;
    }

    public String getCompanyName() {
        return companyName;
    }

    public void setCompanyName(String companyName) {
        this.companyName = companyName;
    }

    public Integer getOrdered() {
        return ordered;
    }

    public void setOrdered(Integer ordered) {
        this.ordered = ordered;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public Integer getStatus() {
        return status;
    }

    public void setStatus(Integer status) {
        this.status = status;
    }

    @Override
    public String toString() {
        return "Brand{" +
                "id=" + id +
                ", brandName='" + brandName + '\'' +
                ", companyName='" + companyName + '\'' +
                ", ordered=" + ordered +
                ", description='" + description + '\'' +
                ", status=" + status +
                '}';
    }
}

```



![image-20230210212214150](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302102122213.png)

```java
/**
 * @author momo~
 * @version 1.0
 * 品牌数据的查询所有操作
 */
public class BrandTest {
    /*
        查询所有
        1.SQL:select * from tb_brand;
        2.参数：不需要
        3.结果：List<Brand>
     */

    @Test
    public void testSelectAll() throws Exception {
        //1.获取Connection
        //3.加载配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src/com/itheima/druid.properties"));

        //4.获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        //5.获取数据库连接
        Connection connection = dataSource.getConnection();

        //定义SQL
        String sql = "select * from tb_brand";

        //获取preparedStatement
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        //设置参数

        //执行SQL
        ResultSet resultSet = preparedStatement.executeQuery();

        //处理结果
        Brand brand = null;

        List<Brand> brands = new ArrayList<>();

        while (resultSet.next()){
            //获取数据
            int id = resultSet.getInt("id");
            String brandName = resultSet.getString("brand_name");
            String companyName = resultSet.getString("company_name");
            int ordered = resultSet.getInt("ordered");
            String description = resultSet.getString("description");
            int status = resultSet.getInt("status");

            //封装Brand对象
            brand = new Brand();
            brand.setId(id);
            brand.setBrandName(brandName);
            brand.setCompanyName(companyName);
            brand.setOrdered(ordered);
            brand.setDescription(description);
            brand.setStatus(status);

            //装载集合
            brands.add(brand);

        }
        System.out.println(brands);

        //释放资源
        resultSet.close();
        preparedStatement.close();
        connection.close();
    }
}
```



![image-20230210220113055](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302102201137.png)







```java
//增
    /*
        1.SQL:insert into tb_brand(brand_name,company_name,ordered,description,status) values(?,?,?,?,?);
        2.参数：需要，除了id之外所有的参数信息
        3.结果：boolean
     */
    @Test
    public void testAdd() throws Exception {
        //接收页面提交参数
        String brandName = "香飘飘";
        String companyName = "香飘飘";
        int ordered = 1;
        String description = "绕地球一圈";
        int status = 1;

        //1.获取Connection
        //3.加载配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src/com/itheima/druid.properties"));

        //4.获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        //5.获取数据库连接
        Connection connection = dataSource.getConnection();

        //定义SQL
        String sql = "insert into tb_brand(brand_name,company_name,ordered,description,status) values(?,?,?,?,?)";

        //获取preparedStatement
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        //设置参数
        preparedStatement.setString(1,brandName);
        preparedStatement.setString(2,companyName);
        preparedStatement.setInt(3,ordered);
        preparedStatement.setString(4,description);
        preparedStatement.setInt(5,status);

        //执行SQL
        int count = preparedStatement.executeUpdate();

        //处理结果
        if (count > 0){
            System.out.println("成功");
        } else {
            System.out.println("失败");
        }

        //释放资源
        preparedStatement.close();
        connection.close();
    }
```





![image-20230210221348820](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302102213903.png)



```java
//修改
    /*
        1.SQL:update tb_brand set brand_name = ?,
              company_name = ?,ordered = ?,description = ?,
              status = ? where id = ?;
        2.参数：需要，所有数据
        3.结果：boolean
     */
    @Test
    public void testUpdate() throws Exception {
        //接收页面提交参数
        String brandName = "香飘飘";
        String companyName = "香飘飘";
        int ordered = 1000;
        String description = "绕地球san圈";
        int status = 1;
        int id = 4;

        //1.获取Connection
        //3.加载配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src/com/itheima/druid.properties"));

        //4.获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        //5.获取数据库连接
        Connection connection = dataSource.getConnection();

        //定义SQL
        String sql = "update tb_brand set brand_name = ?,\n" +
                "              company_name = ?,ordered = ?,description = ?,\n" +
                "              status = ? where id = ?";

        //获取preparedStatement
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        //设置参数
        preparedStatement.setString(1,brandName);
        preparedStatement.setString(2,companyName);
        preparedStatement.setInt(3,ordered);
        preparedStatement.setString(4,description);
        preparedStatement.setInt(5,status);
        preparedStatement.setInt(6,id);

        //执行SQL
        int count = preparedStatement.executeUpdate();

        //处理结果
        if (count > 0){
            System.out.println("成功");
        } else {
            System.out.println("失败");
        }

        //释放资源
        preparedStatement.close();
        connection.close();
    }
```



![image-20230210222126092](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302102221169.png)



```java
//删除
    /*
        1.SQL:delete from tb_brand where id = ?
        2.参数：需要，id
        3.结果：boolean
     */
    @Test
    public void testDelete() throws Exception {
        //接收页面提交参数
        int id = 4;

        //1.获取Connection
        //3.加载配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src/com/itheima/druid.properties"));

        //4.获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        //5.获取数据库连接
        Connection connection = dataSource.getConnection();

        //定义SQL
        String sql = "delete from tb_brand where id = ?";

        //获取preparedStatement
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        //设置参数
        preparedStatement.setInt(1,id);

        //执行SQL
        int count = preparedStatement.executeUpdate();

        //处理结果
        if (count > 0){
            System.out.println("成功");
        } else {
            System.out.println("失败");
        }

        //释放资源
        preparedStatement.close();
        connection.close();
    }
```



## 3.Maven

  ![image-20230211103029216](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111030351.png)



 ![image-20230211103342185](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111033267.png)



![image-20230211103901768](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111039865.png)



### 1.Maven简介

![image-20230211104815185](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111048270.png)



![image-20230211105634341](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111056422.png)





### 2.Maven安装配置

![image-20230211105714249](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111057316.png)

#### 1.解压apache-maven即安装完成

![image-20230211110630039](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111106074.png)



#### 2.配置环境变量

![image-20230211110744237](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111107273.png)



![image-20230211110821643](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111108687.png)



![image-20230211110706853](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111107902.png)



#### 3.修改本地仓库



![image-20230211111143465](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111111515.png)



![image-20230211111118340](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111111378.png)



![image-20230211111800836](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111118874.png)

#### 4.配置阿里云私服

```xml
    <morror>
      <id>alimaven</id>
      <name>aliyun maven</name>
      <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
      <mirrorOf>central</mirrorOf>
    </morror>>
```



### 3.Maven基本使用

#### 1.Maven常用命令

![image-20230211152217263](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111522326.png)



#### 2.Maven生命周期

![image-20230211153237931](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111532003.png)

![image-20230211153303317](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111533424.png)





### 4.IDEA配置Maven

#### 1.IDEA配置Maven环境

![image-20230211153546741](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111535828.png)





#### 2.Maven坐标详解

![image-20230211154312717](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111543789.png)





#### 3.IDEA创建Maven项目

![image-20230211160616797](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111606890.png)





#### 4.IDEA导入Maven项目

![image-20230211160847488](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111608575.png)



![image-20230211160933223](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111609306.png)



### 5.依赖管理&依赖范围

![image-20230211171641818](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111716901.png)



![image-20230211171657319](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111716398.png)





![image-20230211171750712](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111717787.png)



![image-20230211172955913](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302111729034.png)





## 4.MyBatis

![image-20230211203847073](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302112038184.png)



![image-20230211204129782](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302112041938.png)



![image-20230211204602434](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302112046618.png)





### 1.MyBatis快速入门

![image-20230211205420960](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302112054041.png)

![image-20230211222000307](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302112220383.png)





```java
package com.itheima;

import com.itheima.pojo.User;
import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 * MyBatis快速入门
 */
public class MyBatisDemo {
    public static void main(String[] args) throws IOException {
        //1.加载mybatis核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.执行SQL
        List<User> users = sqlSession.selectList("test.selectAll");

        System.out.println(users);

        //4.关闭资源
        sqlSession.close();
    }
}

```



```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <!--
        CONSOLE ：表示当前的日志信息是可以输出到控制台的。
    -->
    <appender name="Console" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>[%level] %blue(%d{HH:mm:ss.SSS}) %cyan([%thread]) %boldGreen(%logger{15}) - %msg %n</pattern>
        </encoder>
    </appender>

    <logger name="com.itheima" level="DEBUG" additivity="false">
        <appender-ref ref="Console"/>
    </logger>


    <!--

      level:用来设置打印级别，大小写无关：TRACE, DEBUG, INFO, WARN, ERROR, ALL 和 OFF
     ， 默认debug
      <root>可以包含零个或多个<appender-ref>元素，标识这个输出位置将会被本日志级别控制。
      -->
    <root level="DEBUG">
        <appender-ref ref="Console"/>
    </root>
</configuration>
```





```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="root"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <!-- 加载SQL映射文件 -->
        <mapper resource="UserMapper.xml"/>
    </mappers>
</configuration>
```



```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="test">
    <select id="selectAll" resultType="com.itheima.pojo.User">
        select * from tb_user;
    </select>
</mapper>
```



![image-20230211222431755](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302112224839.png)



### 2.Mapper代理开发

![image-20230212100123055](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121001163.png)

 ![image-20230212100208188](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121002285.png)

![image-20230212102011552](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121020643.png)

**UserMapper**

```java
package com.itheima.mapper;

import com.itheima.pojo.User;

import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public interface UserMapper {

    List<User> selectAll();
}

```



**UserMapper.xml**

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.itheima.mapper.UserMapper">
    <select id="selectAll" resultType="com.itheima.pojo.User">
        select * from tb_user;
    </select>
</mapper>
```



**mybatis-config.xml**

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="root"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <!-- 加载SQL映射文件 -->
        <!--<mapper resource="com/itheima/mapper/UserMapper.xml"/>-->

        <!--Mapper代理方式-->
        <!--包扫描方式-->
        <package name="com.itheima.mapper"/>
    </mappers>
</configuration>
```







```java
public class MyBatisDemo2 {
    public static void main(String[] args) throws IOException {
        //1.加载mybatis核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.执行SQL
        //List<User> users = sqlSession.selectList("test.selectAll");

        //3.1获取UserMapper接口的代理对象
        UserMapper userMapper = sqlSession.getMapper(UserMapper.class);
        for (User user : userMapper.selectAll()) {
            System.out.println(user);
        }
        
        //4.关闭资源
        sqlSession.close();
    }
}
```





### 3.MyBatis核心配置文件

![image-20230212103825417](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121038501.png)



```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>

    <!--类型别名可为 Java 类型设置一个缩写名字。
    它仅用于 XML 配置，意在降低冗余的全限定类名书写-->
    <typeAliases>
        <package name="com.itheima.pojo"/>
    </typeAliases>
    
    
    <!--MyBatis 可以配置成适应多种环境，这种机制有助于将 SQL 映射应用于多种数据库之中，
    现实情况下有多种理由需要这么做。例如，开发、测试和生产环境需要有不同的配置；
    或者想在具有相同 Schema 的多个生产数据库中使用相同的 SQL 映射。
    还有许多类似的使用场景。不过要记住：尽管可以配置多个环境，但每个 SqlSessionFactory 实例
    只能选择一种环境。-->
    <environments default="development">
        <!--开发环境-->
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="root"/>
            </dataSource>
        </environment>

        <!--测试环境-->
        <environment id="test">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="root"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <!-- 加载SQL映射文件 -->
        <!--<mapper resource="com/itheima/mapper/UserMapper.xml"/>-->

        <!--Mapper代理方式-->
        <!--包扫描方式-->
        <package name="com.itheima.mapper"/>
    </mappers>
</configuration>
```





### 4.配置文件完成增删改查

![image-20230212104736501](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121047598.png)



![image-20230212110950719](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121109793.png)



![image-20230212111032022](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121110081.png)



```mysql
-- 删除tb_brand表
DROP TABLE if EXISTS tb_brand;

CREATE TABLE tb_brand(
	id int PRIMARY KEY auto_increment,
	brand_name VARCHAR(20),
	company_name VARCHAR(20),
	ordered INT,
	description VARCHAR(100),
	status INT);
	
INSERT INTO tb_brand(brand_name,company_name,ordered,description,status) VALUES
("三只松鼠","三只松鼠股份有限公司",5,"好吃不上火",0),
("华为","华为技术有限公司",100,"华为致力于xxx",1),
("小米","小米科技有限公司",50,"谁tm买小米",2);

SELECT * FROM tb_brand;
```







![image-20230212123659264](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121236351.png)

![image-20230212125307675](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121253784.png)



![image-20230212125415354](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121254429.png)



#### A. 查询

![image-20230212125845610](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121258692.png)



![image-20230212134525705](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121345771.png)

![image-20230212134231677](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121342757.png)

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.itheima.mapper.BrandMapper">

    <!--数据库表的字段名称和实体类的属性名称不一样，则不能自动封装-->
    <!--Brand{id=1, brandName='null', companyName='null', ordered=5, description='好吃不上火', status=0}-->

    <!--解决办法-->
    <!--1.起别名-->
    <!--2.SQL片段-->


<!--    <sql id="brand_column">
        id,brand_name as brandName,company_name as companyName,ordered,description,status
    </sql>

    <select id="selectAll" resultType="com.itheima.pojo.Brand">
        &lt;!&ndash;select * from tb_brand;&ndash;&gt;

        select <include refid="brand_column"/> from tb_brand;
    </select>-->

    <!--3.restMap-->
    <!--
        1.定义resultMap标签
        2.在<select>标签中使用resultMap属性替换resultType属性
    -->
    <!--
        id:唯一标识
        type：映射的类型，支持别名
    -->
    <resultMap id="brandResultMap" type="com.itheima.pojo.Brand">
        <!--
            id：完成主键字段的映射
                column：表的列名
                property：实体类的属性名
            result：完成一般字段的映射
                column：表的列名
                property：实体类的属性名
        -->
        <result column="brand_name" property="brandName"/>
        <result column="company_name" property="companyName"/>
    </resultMap>
    
    <select id="selectAll" resultMap="brandResultMap">
        select * from tb_brand;
    </select>
</mapper>
```





![image-20230212134839519](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121348604.png)

![image-20230212140532503](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121405583.png)



```xml
<!--
          * 参数占位符
          1.#{} 将其替换为？
          2.${} 拼SQL，会存在sql注入问题
          3.参数传递时使用#{}
            表名或列名不固定时使用${}
          4.参数类型：parameterType:可以省略
          5.特殊字符处理
            转义字符
            CDATA区
    -->
    <select id="selectById" resultMap="brandResultMap">
        select * from tb_brand where id = #{id};
    </select>

<!--    <select id="selectById" resultMap="brandResultMap">
        select * from tb_brand where id &lt; #{id};

        select * from tb_brand where
        id <![CDATA[
            <
        ]]> #{id}
    </select>-->
```



![image-20230212141326115](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121413208.png)



![image-20230212141305851](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121413927.png)





![image-20230212144419642](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121444731.png)



```java
package com.itheima.mapper;

import com.itheima.pojo.Brand;
import org.apache.ibatis.annotations.Param;

import java.util.List;
import java.util.Map;

/**
 * @author momo~
 * @version 1.0
 */
public interface BrandMapper {

    /*
       查询所有数据
     */
    List<Brand> selectAll();

    /*
        查看详情
     */

    Brand selectById(int id);

    /**
     * 条件查询
     * 参数接收：
     *      1.散装参数，如果方法中有多个参数，需要使用@Param("参数占位符")
     *      2.对象参数,对象的属性名称要和参数占位符名称一致
     *      3.map集合参数
     *
     * @param status
     * @param companyName
     * @param brandName
     * @return
     */
//    List<Brand> selectByCondition(@Param("status") int status,
//                                  @Param("companyName") String companyName,
//                                  @Param("brandName") String brandName);


//    List<Brand> selectByCondition(Brand brand);

    List<Brand> selectByCondition(Map map);


}

```



```java
package com.itheima.test;

import com.itheima.mapper.BrandMapper;
import com.itheima.pojo.Brand;
import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;
import org.junit.Test;

import java.io.IOException;
import java.io.InputStream;
import java.util.HashMap;
import java.util.Map;

/**
 * @author momo~
 * @version 1.0
 */
public class MyBatisTest {

    @Test
    public void testSelectAll() throws IOException {
        //1.加载mybatis核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.获取Mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4.执行方法
        for (Brand brand : brandMapper.selectAll()) {
            System.out.println(brand);
        }

        //5.释放资源
        sqlSession.close();
    }

    @Test
    public void testSelectById() throws IOException {
        //接收参数
        int id = 1;

        //1.加载mybatis核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.获取Mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4.执行方法
        Brand brand = brandMapper.selectById(id);
        System.out.println(brand);

        //5.释放资源
        sqlSession.close();
    }

    @Test
    public void testSelectByCondition() throws IOException {
        //接收参数
        int status = 1;
        String companyName = "华为";
        String brandName = "华为";

        //处理参数
        companyName = "%" + companyName + "%";
        brandName = "%" + brandName + "%";

        //封装对象
//        Brand brand = new Brand();
//        brand.setStatus(status);
//        brand.setBrandName(brandName);
//        brand.setCompanyName(companyName);

        Map map = new HashMap();
        map.put("status",status);
        map.put("companyName",companyName);
        map.put("brandName",brandName);

        //1.加载mybatis核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.获取Mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4.执行方法
//        for (Brand brand : brandMapper.selectByCondition(status, companyName, brandName)) {
//            System.out.println(brand);
//        }

        for (Brand brand1 : brandMapper.selectByCondition(map)) {
            System.out.println(brand1);
        }

        //5.释放资源
        sqlSession.close();
    }
}

```



![image-20230212145004754](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121450840.png)

![image-20230212145143104](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121451247.png)



**动态SQ**L

动态 SQL 是 MyBatis 的强大特性之一。如果你使用过 JDBC 或其它类似的框架，你应该能理解根据不同条件拼接 SQL 语句有多痛苦，例如拼接时要确保不能忘记添加必要的空格，还要注意去掉列表最后一个列名的逗号。利用动态 SQL，可以彻底摆脱这种痛苦。

- if
- choose (when, otherwise)
- trim (where, set)
- foreach





![image-20230212151242074](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121512162.png)

```xml
    <!--动态条件查询-->
    <!--
          if:条件查询
          问题：恒等式 1 = 1
          <where>替换where
    -->
    <select id="selectByCondition" resultMap="brandResultMap">
        select * from tb_brand
        <!--where 1 = 1-->
        <where>
        <if test="status != null">and status = #{status}</if>
        <if test="companyName != null and companyName != ''">and company_name like #{companyName}</if>
        <if test="brandName != null and brandName != ''">and brand_name like #{brandName}</if>
        </where>
    </select>
```



![image-20230212151353575](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121513676.png)



```xml
    <select id="selectByConditionSingle" resultMap="brandResultMap">
        select * from tb_brand
        <where>
        <choose>
            <when test="status != null">
                status = #{status}
            </when>
            <when test="companyName != null and companyName != ''">
                company_name like #{companyName}
            </when>
            <when test="brandName != null and brandName != ''">
                brand_name like #{brandName}
            </when>
        </choose>
        </where>
    </select>
```





#### B.添加

![image-20230212152909419](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302121529529.png)



```xml
    <insert id="add">
        insert into tb_brand(brand_name,company_name,ordered,description,status)
        values(#{brandName},#{companyName},#{ordered},#{description},#{status})
    </insert>
```





```java
@Test
    public void testAdd() throws IOException {
        //接收参数
        int status = 1;
        String companyName = "博导手机";
        String brandName = "博导";
        String description = "手机中的战斗机";
        int ordered = 100;

        //封装对象
        Brand brand = new Brand();
        brand.setStatus(status);
        brand.setBrandName(brandName);
        brand.setCompanyName(companyName);
        brand.setDescription(description);
        brand.setOrdered(ordered);


        //1.加载mybatis核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.获取SqlSession对象
        //SqlSession sqlSession = sqlSessionFactory.openSession();
        //openSession(true):自动提交事务
        SqlSession sqlSession = sqlSessionFactory.openSession(true);

        //3.获取Mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4.执行方法
//        for (Brand brand : brandMapper.selectByCondition(status, companyName, brandName)) {
//            System.out.println(brand);
//        }
        brandMapper.add(brand);

        //提交事务
        //sqlSession.commit();
        
        //5.释放资源
        sqlSession.close();
    }
```



![image-20230212204235038](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122042167.png)



![image-20230212204644451](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122046523.png)



```xml
    <insert id="add" useGeneratedKeys="true" keyProperty="id">
        insert into tb_brand(brand_name,company_name,ordered,description,status)
        values(#{brandName},#{companyName},#{ordered},#{description},#{status})
    </insert>
```



#### C.修改

![image-20230212204809389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122048485.png)

```xml
    <update id="update">
        update tb_brand set
        brand_name = #{brandName},
        company_name = #{companyName},
        ordered = #{ordered},
        description = #{description},
        status = #{status}
        where id = #{id}
    </update>
```



![image-20230212205911750](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122059863.png)



```xml
    <update id="update">
        update tb_brand
        <set>
        <if test="brandName != null and brandName != ''">
            brand_name = #{brandName},
        </if>
        <if test="companyName != null and companyName != ''">
            company_name = #{companyName},
        </if>
        <if test="ordered != null">
            ordered = #{ordered},
        </if>
        <if test="description != null and description != ''">
            description = #{description},
        </if>
        <if test="status != null">
            status = #{status}
        </if>
        </set>
        where id = #{id}
    </update>
```





#### D.删除

![image-20230212210832693](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122108795.png)

```xml
    <delete id="deleteById">
        delete from tb_brand where id = #{id};
    </delete>
```



![image-20230212212534971](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122125067.png)

```xml
    <delete id="deleteByIds">
        delete from tb_brand where id in (
        <foreach collection="ids" item="id" separator=",">
            #{id}
        </foreach>);
    </delete>
```



```java
    /**
     * 批量删除
     */
    void deleteByIds(@Param("ids") int[] ids);
```





### 5.MyBatis参数传递

![image-20230212212904804](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122129909.png)



![image-20230212214636875](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122146988.png)





![image-20230212214748839](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122147931.png)

### 6.注解开发

![image-20230212214957513](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302122149668.png)



```java
    @Select("select * from tb_user where id = #{id}")
    User selectById(int id);
```



## 5.HTML

![image-20230213100250765](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131002832.png)

### 1.HTML快速入门

![image-20230213100524823](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131005898.png)



![image-20230213101316000](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131013069.png)



```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>html快速入门</title>
</head>
<body>
<font color="red">乾坤未定，你我皆是黑马</font>
</body>
</html>
```



![image-20230213101729567](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131017634.png)



### 2.基础标签

![image-20230213102248695](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131022774.png)



```html
<!--html5标识-->
<!DOCTYPE html>
<html lang="en">
<head>
    <!--定义字符集-->
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<h1>我是标题 h1</h1>
<h2>我是标题 h2</h2>
<h3>我是标题 h3</h3>
<h4>我是标题 h4</h4>
<h5>我是标题 h5</h5>
<h6>我是标题 h6</h6>
<hr>
<!--
    html表示颜色：
        1.英文单词 red,pink,blue...
        2.rgb(值1，值2，值3) 取值范围：0~255 rgb(255,0,0)
        3.#值1值2值3
-->
<font face="楷体" size="5" color="#ffc0cb">传智教育</font>

<hr>

<p>
    “文明与地域紧密相关，山水之间界定了我们的家园。
</p>
<p>
    ”纪录片《扎什伦布》立足于宏阔的人文视野，
    从中华文明多元一体的历史格局出发，以藏传佛教格鲁派“六大寺院”之一、历代班禅的驻锡地——扎什伦布寺为切入点
</p>
<p>
    以扎什伦布寺近600年岁月沧桑为主轴，系统呈现了藏传佛教中国化的时光脚步，生动讲述了历代班禅爱国爱教、护国利民的故事。
</p>
<hr>

纪录片《扎什伦布》立足于宏阔的人文视野<br>
<b>纪录片《扎什伦布》立足于宏阔的人文视野</b><br>
<i>纪录片《扎什伦布》立足于宏阔的人文视野</i><br>
<u>纪录片《扎什伦布》立足于宏阔的人文视野</u>
<hr>

<center>纪录片《扎什伦布》立足于宏阔的人文视野</center>

</body>
</html>
```



![image-20230213105346181](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131053245.png)

![image-20230213105507905](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131055995.png)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<h1>公司简介</h1>
<hr color="yellow">

<p>
    <font color="red">传智教育</font>
    (股票代码 003032)，隶属江苏传智播客教育科技股份有限公司，注册资本4亿元，是第一个实现A股IPO的教育企业，公司致力于培养高精尖数字化人才，主要培养人工智能、python+大数据开发、智能制造、软件、互联网、区块链等数字化专业人才及数据分析、网络营销、新媒体等数字化应用人才。公司由一批拥有10年以上开发管理经验，且来自互联网或研究机构的IT精英组成，负责研究、开发教学模式和课程内容。公司具有完善的课程研发体系，一直走在整个行业发展的前端，在行业内竖立起了良好的品质口碑。
</p>
<P>
    民族振兴靠人才，中华民族正处于伟大复兴之路上，要赢得国际竞争，需要拥有大量的科技人才，我们将肩负起民族使命，在三尺讲台诲人不倦
    著书立说，为科技行业培养出大量的优秀人才，促进民族伟大复兴！我们的使命是：
    <b>
        为中华民族伟大复兴而讲课，为千万学生少走弯路而著书。
    </b>
</P>
<p>
    探索教育之路，长途漫漫。传智教育希望可以通过自己的努力，寻找出一条更符合人类自然成长规律的教育之路，建立起一个新的教育生态环境，让中国的家长和孩子们在现有的教育体系之外，再多一些选择的机会。因此“
    <b>
        探索教育本源，开辟教育新生态
    </b>
    ”便成为了所有传智人为之奋斗的终极愿景，也是所有传智人共同努力的目标。为此，15年来，传智人不曾有一丝懈怠，相信在传智人的不懈努力下，大道不远，终在脚下。
</p>
<hr color="yellow">
<center>
    <font size="1">
        江苏传智播客教育科技股份有限公司<br>
        版权所有Copyright 2006-2018©, All Rights Reserved 苏ICP备16007882
    </font>
</center>
<hr>
</body>
</html>
```



### 3.图片、音频、视频标签

![image-20230213115352948](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131153028.png)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<!--资源路径
        1.绝对路径
        2.相对路径:相对位置关系
            xxx/html/html-图片音频视频.html
            xxx/html/a.jpg

            ./a.jpg & a.jpg
    尺寸单位：
        1.px:像素
        2.百分比：
-->
<img src="img/a.jpg" width="200" height="400">

<audio src="b.mp3" controls></audio>

<img src="https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131153028.png">

<video src="c.mp4" controls width="500" height="300"></video>
<br>
<img src="img/preview.jpg">
</body>
</html>
```



![image-20230213121435242](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131214307.png)

![image-20230213121657926](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131216961.png)

### 4.超链接标签

![image-20230213121937985](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131219045.png)

```html
<a href="https://www.itcast.cn" target="_blank">点我,再打开一个网页</a>
<a href="https://www.itcast.cn" target="_self">点我,覆盖打开</a>
```

   

### 5.列表标签

![image-20230213122527865](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131225930.png)



![image-20230213123028146](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131230189.png)



### 6.表格标签

![image-20230213123104028](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131231114.png)



![image-20230213124713960](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131247008.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<table border="1" cellspacing="0" width="500">
  <tr>
    <th>序号</th>
    <th>品牌logo</th>
    <th>品牌名称</th>
    <th>企业名称</th>
  </tr>
  <tr align="center">
    <td>010</td>
    <td><img src="../img/三只松鼠.png" width="60" height="50"></td>
    <td>三只松鼠</td>
    <td>三只松鼠</td>
  </tr>
  <tr align="center">
    <td>009</td>
    <td><img src="../img/优衣库.png" width="60" height="50"></td>
    <td>优衣库</td>
    <td>优衣库</td>
  </tr>
  <tr align="center">
    <td>008</td>
    <td><img src="../img/小米.png" width="60" height="50"></td>
    <td>小米</td>
    <td>小米科技优秀公司</td>
  </tr>
</table>
<br>
<hr>
<br>
<table border="1" cellspacing="0" width="500">
  <tr>
    <th colspan="2">品牌logo</th>
    <th>品牌名称</th>
    <th>企业名称</th>
  </tr>
  <tr align="center">
    <td>010</td>
    <td><img src="../img/三只松鼠.png" width="60" height="50"></td>
    <td>三只松鼠</td>
    <td>三只松鼠</td>
  </tr>
  <tr align="center">
    <td rowspan="2">009</td>
    <td><img src="../img/优衣库.png" width="60" height="50"></td>
    <td>优衣库</td>
    <td>优衣库</td>
  </tr>
  <tr align="center">
    <td>008</td>
    <td><img src="../img/小米.png" width="60" height="50"></td>
    <td>小米</td>
  </tr>
</table>
</body>
</html>
```



### 7.布局标签

![image-20230213124909170](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131249220.png)

```html
<div>我是div</div>
<div>我是div</div>
<span>我是span</span>
<span>我是span</span>
```



![image-20230213125133454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131251492.png)



### 8.表单标签

![image-20230213125443227](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131254372.png)





```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>

<!--
    action:指定表单数据提交url
        * 表单数据提交需要指定name属性
    method: 指定表单提交方式
        1.get（默认）：
            * 请求参数会拼接在url后面（不安全）
            * url长度有限制
        2.post
            * 请求参数会在http请求协议的请求体中
            * 请求参数无限制
-->
<form action="#" method="post">
    <input type="text" name="username">
    <input type="submit">
</form>
</body>
</html>
```



![image-20230213131020197](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131310272.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<form action="#" method="post">
    <input type="hidden" name="id" value="1">

    <label for="username-label">用户名：</label>
    <input type="text" name="username" id="username-label">
    <label for="password-label">密码：</label>
    <input type="password" name="password" id="password-label">
    <br>
    <br>
    性别：
    <label for="man-label">男</label>
    <input type="radio" name="gender" value="1" id="man-label">
    <label for="woman-label">女</label>
    <input type="radio" name="gender" value="2" id="woman-label">
    <br>
    <br>

    爱好：
    <label for="check01">旅游</label>
    <input type="checkbox" name="hobby" value="1" id="check01">
    <label for="check02">电影</label>
    <input type="checkbox" name="hobby" value="2" id="check02">
    <label for="check03">游戏</label>
    <input type="checkbox" name="hobby" value="3" id="check03">
    <br>
    <br>

    头像：
    <input type="file">

    <select name="city">
        <option value="beijing">北京</option>
        <option value="shanghai">上海</option>
        <option value="guangzhou">广州</option>
    </select>

    <br>
    <br>
    个人描述：
    <textarea cols="20" rows="5" name="desc"></textarea>

    <br>
    <br>
    <input type="submit" value="免费注册">

    <input type="reset" value="重置">

    <input type="button" value="一个按钮">

</form>
</body>
</html>
```



![image-20230213134249899](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131342950.png)



## 6.css

![image-20230213140812971](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131408053.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
  <style>
    div{
        color: red;
    }
  </style>
</head>
<body>
<div>
  Hello CSS~
</div>
</body>
</html>
```



### 1.css导入方式

![image-20230213141419537](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131414614.png)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        span{
            color: red;
        }
    </style>

    <link href="../css/demo.css" rel="stylesheet">
</head>
<body>

<div style="color: red">hello css</div>

<p>hello css</p>

<span>hello css</span>
</body>
</html>
```



```css
p{
    color: red;
}
```



### 2.css选择器

![image-20230213142113038](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131421120.png)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*元素选择器*/
        div{
            color: red;
        }

        /*id选择器*/
        #name{
            color: pink;
        }

        /*类选择器*/
        .cls{
            color: aqua;
        }
    </style>
</head>
<body>

<div>div1</div>
<div id="name">div2</div>
<div>div3</div>

<span class="cls">span</span>
</body>
</html>
```



### 3.css属性（略）



## 7.JavaScript

![image-20230213143040401](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131430498.png)

### 1.JavaScript引入方式

![image-20230213144012213](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131440271.png)

![image-20230213144106287](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131441356.png)

![image-20230213144137611](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131441678.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

</head>
<body>

<!--<script>
    alert("hello js");
</script>-->
<script src="../js/demo.js"></script>
</body>
</html>
```



### 2.JavaScript基础语法

#### 书写语法

![image-20230213145036493](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131450563.png)

#### 输出语句

![image-20230213145230019](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131452089.png)

```html
<script>
    window.alert("hello js");

    document.write("hello js2");

    console.log("hello js3");
</script>
```



#### 变量

![image-20230213145646071](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131456160.png)





```html
<script>
    // var test = 20;
    // test = "张三";
    //
    // alert(test);

    /*
        var:
            1.作用域：全局变量
            2.变量可以重复定义
     */
    {
        var age = 30;
        // var age = 40;

        let sex = 3;
        // let sex = 4;
    }
    alert(age);

    const pi = 3.14;
    //pi = 3;
</script>
```



#### 数据类型

![image-20230213150629900](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131506978.png)





```html
<script>
    //number
    // var age = 20;
    // var price = 99.8;
    // alert(typeof age);
    // alert(typeof price);

    //string
    // var ch = "a";
    // var name = '张三';
    // var addr = "北京";
    // alert(typeof ch);
    // alert(typeof name);
    // alert(typeof addr);

    //boolean
    // var flag = true;
    // var flag2 = false;
    //
    // alert(typeof flag);
    // alert(typeof flag2);

    //null
    // var obj = null;
    // alert(typeof obj);//object
    //注释：您也许会问，为什么typeof运算符对于null值会返回"Object"。
    // 这实际上是JavaScript最初实现中的一个错误，然后被ECMAScript沿用了。
    // 现在，null被认为是对象的占位符，从而解释了这一矛盾，
    // 但从技术上来说，它仍然是原始值。

    var a;
    alert(typeof a);

</script>
```





#### 运算符

![image-20230213152022206](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131520277.png)

![image-20230213154206913](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131542996.png)



#### 流程控制

![image-20230213184108078](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131841147.png)

```html
<script>
  //1.if
  // var count = 3;
  // if (count == 3){
  //   alert(count)
  // }

  //2.switch
  // var num = 3;
  // switch (num) {
  //     case 1:{
  //         alert("星期一");
  //     }
  //     case 2:{
  //         alert("星期二")
  //     }
  //     default:{}
  //         alert("输入星期有误");
  //         break;
  // }

  //3.for
  // var sum = 0;
  // for (let i = 1;i <= 100;i++){
  //     sum += i;
  // }
  // alert(sum);

  //4.while
  // var sum = 0;
  // var i = 1;
  // while (i <= 100){
  //     sum += i;
  //     i++;
  // }
  // alert(sum);

  //5.do...while
  var sum = 0;
  var i = 1;
  do{
      sum += i;
      i++;
  }
  while (i <= 100);
  alert(sum);
</script>
```



#### 函数

![image-20230213184210579](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131842656.png)



![image-20230213184717976](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302131847045.png)

```html
<script>
  // function add(a,b){
  //     return a + b;
  // }
  //
  // var result = add(1,2);
  // alert(result);

  var add = function (a,b){
      return a + b;
  }

  var result = add(1,2);
  alert(result);

</script>
```



### 3.JavaScript常用对象

#### 1.Array

![image-20230213212520530](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132125607.png)



![image-20230213213704497](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132137607.png)



```html
<script>
    //方式1
    // var arr = new Array(1,2,3);
    // alert(arr);

    //方式2
    var arr = [1,2,3];
    // alert(arr);

    //数组访问
    arr[0] = 10;
    // alert(arr)

    //JS数组 = Java集合，长度类型可变

    //变长
    arr[10] = 10;
    // alert(arr[9]);

    //变类型
    arr[5] = "hello";
    // alert(arr);

    //属性 length:数组中元素个数
    // var arr4 = [1,2,3];
    // for (let i = 0; i < arr4.length; i++) {
    //     alert(arr4[i]);
    // }

    //方法
    //push:添加方法
    var arr5 = [1,2,3];
    // arr5.push(10);
    // alert(arr5)

    //splice：删除方法
    arr5.splice(0,1);
    alert(arr5);

</script>
```



#### 2.String

![image-20230213213917904](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132139982.png)

```html
<script>
    //方式1
    var str1 = new String("abc");

    //方式2
    var str2 = "abc";
    var str3 = 'abc';

    //属性 length 字符串长度
    // alert(str1.length);

    //trim() 取出字符串前后两端空白字符
    var str4 = "  abc   ";
    alert(1 + str4.trim() + 1);
</script>
```



#### 3.自定义对象

![image-20230213214631194](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132146284.png)

```html
<script>

    var person = {
        name : "zhangsan",
        age : 23,
        eat:function (){
            alert("干饭")
        }
    }

    alert(person.name);
    alert(person.age);
    person.eat();

</script>
```



#### 4.BOM

![image-20230213215039562](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132150637.png)

![image-20230213215302902](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132153986.png)



```html
<script>

    //alert
    // window.alert("abc");
    // alert("bbb");

    //confirm 点击确定返回true，取消返回false
    // var flag = confirm("确认删除吗？");
    // alert(flag);
    //
    // if (flag){
    //     //删除逻辑
    // }

    //定时器
    /*
        setTimeout(function,毫秒值): 只执行一次

        setInterval(function,毫秒值)l: 循环执行
     */

    // setTimeout(function (){
    //     alert("hehe")
    // },3000)

    setInterval(function (){
        alert("hhe")
    },2000)

</script>
```



![image-20230213220332409](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132203481.png)

```html
<script>

    function on(){
        document.getElementById('myImage').src='../imgs/on.gif';
    }

    function off(){
        document.getElementById('myImage').src='../imgs/off.gif'
    }

    var x = 0;

    //根据一个变化的数字产生固定个数的值：2 x % 2
    //定时器
    setInterval(function (){
        if (x % 2 == 0){
            on();
        } else {
            off();
        }
        x++;
    },1000)

</script>
```



![image-20230213221715145](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132217216.png)



![image-20230213221809805](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132218877.png)

```html
<script>

  // alert("要跳转了");
  //
  // location.href = "https://www.baidu.com";

  //3秒跳转首页

  document.write("3秒跳转首页");
  setTimeout(function (){
      location.href = "https://www.baidu.com";
  },3000);
</script>
```





#### 5.DOM

![image-20230213222211660](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132222751.png)

![image-20230213222511481](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132225572.png)

![image-20230213222529947](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132225038.png)



##### 1.获取Element

![image-20230213223138059](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132231151.png)

```html
<script>
  /*
    * getElementById:根据id属性值获取，返回一个Element对象
    * getElementsByTagName：根据标签名获取，返回Element对象数组
    * getElementsByName：根据name属性值获取，返回Element对象数组
    * getElementsByClassName：根据class属性值获取，返回Element对象数组
   */
  //1.getElementById
  var img = document.getElementById("light");
  // alert(img);

  //2.getElementsByTagName
  var divs = document.getElementsByTagName("div");
  // alert(divs.length)
  // for (let i = 0; i < divs.length; i++) {
  //     alert(divs[i])
  // }

  //3.getElementsByName
  var hobbys = document.getElementsByName("hobby");
  // for (let i = 0; i < hobbys.length; i++) {
  //     alert(hobbys[i])
  // }

  //4.getElementsByClassName
  var clss = document.getElementsByClassName("cls");
  // for (let i = 0; i < clss.length; i++) {
  //     alert(clss[i])
  // }
  
</script>
```



##### 2.常见HTML Element对象的使用

![image-20230213230439788](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132304852.png)

```html
<script>
  /*
    * getElementById:根据id属性值获取，返回一个Element对象
    * getElementsByTagName：根据标签名获取，返回Element对象数组
    * getElementsByName：根据name属性值获取，返回Element对象数组
    * getElementsByClassName：根据class属性值获取，返回Element对象数组
   */
  //1.getElementById
  var img = document.getElementById("light");
  // alert(img);
  img.src = "../imgs/on.gif";

  //2.getElementsByTagName
  var divs = document.getElementsByTagName("div");
  /*
    style:设置元素css样式
    innerHTML:设置元素内容
   */
  // alert(divs.length)
  for (let i = 0; i < divs.length; i++) {
      //divs[i].style.color = "red";
      divs[i].innerHTML = "hhe";
  }

  //3.getElementsByName
  var hobbys = document.getElementsByName("hobby");
  for (let i = 0; i < hobbys.length; i++) {
      // alert(hobbys[i])
      hobbys[i].checked = true;
  }

  //4.getElementsByClassName
  var clss = document.getElementsByClassName("cls");
  // for (let i = 0; i < clss.length; i++) {
  //     alert(clss[i])
  // }
</script>
```

![image-20230213230517870](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132305920.png)



#### 6.事件监听

![image-20230213230602761](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132306835.png)

##### 1.事件绑定

![image-20230213230914769](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132309855.png)



```html
<body>

<input type="button" value="点我" onclick="on()"><br>
<input type="button" value="再点我" id="btn">

<script>

    function on(){
        alert("我被点了")
    }

    document.getElementById("btn").onclick = function (){
        alert("我被点了")
    }

</script>

</body>
```



##### 2.常见事件

![image-20230213233429609](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302132334708.png)



```html
<body>

<form id="register" action="#">
    <input type="text" name="username">

    <input type="submit" value="提交">
</form>

<script>
    document.getElementById("register").onsubmit = function (){
        return false;
    }
</script>
```





### 4.表单验证

![image-20230214100341075](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141003172.png)



![image-20230214101039997](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141010095.png)

```html
<script>

    //1. 验证用户名是否符合规则
    //1.1 获取用户名的输入框
    var usernameInput =  document.getElementById("username");

    //1.2 绑定onblur事件 失去焦点
    usernameInput.onblur = checkUsername;
        function checkUsername() {
        //1.3 获取用户输入的用户名
        var username = usernameInput.value.trim();

        //1.4 判断用户名是否符合规则:长度6~12
        var flag = username.length >= 6 && username.length <= 12;
        if (flag){
            //符合规则
            document.getElementById("username_err").style.display = "none";
        } else {
            //不符合规则
            document.getElementById("username_err").style.display = "";
        }
        return flag;
    }

    //1. 验证密码是否符合规则
    //1.1 获取密码的输入框
    var passwordInput =  document.getElementById("password");

    //1.2 绑定onblur事件 失去焦点
    passwordInput.onblur = checkPassword;
        function checkPassword() {
        //1.3 获取用户输入的密码
        var password = passwordInput.value.trim();

        var flag = password.length >= 6 && password.length <= 12;
        //1.4 判断密码是否符合规则:长度6~12
        if (flag){
            //符合规则
            document.getElementById("password_err").style.display = "none";
        } else {
            //不符合规则
            document.getElementById("password_err").style.display = "";
        }
        return flag;
    }

    //1. 验证手机号是否符合规则
    //1.1 获取手机号的输入框
    var telInput =  document.getElementById("tel");

    //1.2 绑定onblur事件 失去焦点
    telInput.onblur = checkTel;
        function checkTel() {
        //1.3 获取用户输入的手机号
        var tel = telInput.value.trim();

        //1.4 判断手机号是否符合规则:长度11
        var flag = tel.length == 11;
        if (flag){
            //符合规则
            document.getElementById("tel_err").style.display = "none";
        } else {
            //不符合规则
            document.getElementById("tel_err").style.display = "";
        }
        return flag;
    }


    //表单验证
    //1.获取表单对象
    var regForm = document.getElementById("reg-form");
    //2.绑定onsubmit事件
    regForm.onsubmit = function () {
        //挨个判断每一个表单项是否都符合要求
        var flag = checkUsername() && checkPassword() && checkTel();
        return flag;
    }
</script>
```





### 5.正则表达式

![image-20230214105613699](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141056790.png)



```html
<script>
    //1. 验证用户名是否符合规则
    //1.1 获取用户名的输入框
    var usernameInput =  document.getElementById("username");

    //1.2 绑定onblur事件 失去焦点
    usernameInput.onblur = checkUsername;
        function checkUsername() {
        //1.3 获取用户输入的用户名
        var username = usernameInput.value.trim();

        //1.4 判断用户名是否符合规则:长度6~12,单词字符
        var reg = /^\w{6,12}$/;
        var flag = reg.test(username)

        if (flag){
            //符合规则
            document.getElementById("username_err").style.display = "none";
        } else {
            //不符合规则
            document.getElementById("username_err").style.display = "";
        }
        return flag;
    }

    //1. 验证密码是否符合规则
    //1.1 获取密码的输入框
    var passwordInput =  document.getElementById("password");

    //1.2 绑定onblur事件 失去焦点
    passwordInput.onblur = checkPassword;
        function checkPassword() {
        //1.3 获取用户输入的密码
        var password = passwordInput.value.trim();
        //1.4 判断密码是否符合规则:长度6~12
        var reg = /^\w{6,12}$/;
        var flag = reg.test(password);

        if (flag){
            //符合规则
            document.getElementById("password_err").style.display = "none";
        } else {
            //不符合规则
            document.getElementById("password_err").style.display = "";
        }
        return flag;
    }

    //1. 验证手机号是否符合规则
    //1.1 获取手机号的输入框
    var telInput =  document.getElementById("tel");

    //1.2 绑定onblur事件 失去焦点
    telInput.onblur = checkTel;
        function checkTel() {
        //1.3 获取用户输入的手机号
        var tel = telInput.value.trim();
        //1.4 判断手机号是否符合规则:长度11,数字，第一位1开头
        var reg = /^[1]\d{10}$/;
        var flag = reg.test(tel);
        
        if (flag){
            //符合规则
            document.getElementById("tel_err").style.display = "none";
        } else {
            //不符合规则
            document.getElementById("tel_err").style.display = "";
        }
        return flag;
    }
    
    //表单验证
    //1.获取表单对象
    var regForm = document.getElementById("reg-form");
    //2.绑定onsubmit事件
    regForm.onsubmit = function () {
        //挨个判断每一个表单项是否都符合要求
        var flag = checkUsername() && checkPassword() && checkTel();
        return flag;
    }
</script>
```



## 8.Web核心

![image-20230214124829954](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141248059.png)



![image-20230214125646596](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141256695.png)



![image-20230214130132629](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141301722.png)



## 9.HTTP

![image-20230214131148013](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141311100.png)



### HTTP-请求数据格式

![image-20230214131818283](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141318379.png)



### HTTP-响应数据格式

![image-20230214135247188](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141352277.png)



#### 一、状态码大类

| 状态码分类 | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| 1xx        | **响应中**——临时状态码，表示请求已经接受，告诉客户端应该继续请求或者如果它已经完成则忽略它 |
| 2xx        | **成功**——表示请求已经被成功接收，处理已完成                 |
| 3xx        | **重定向**——重定向到其它地方：它让客户端再发起一个请求以完成整个处理。 |
| 4xx        | **客户端错误**——处理发生错误，责任在客户端，如：客户端的请求一个不存在的资源，客户端未被授权，禁止访问等 |
| 5xx        | **服务器端错误**——处理发生错误，责任在服务端，如：服务端抛出异常，路由出错，HTTP版本不支持等 |

状态码大全：https://cloud.tencent.com/developer/chapter/13553 



#### 二、常见的响应状态码

| 状态码 | 英文描述                               | 解释                                                         |
| ------ | -------------------------------------- | ------------------------------------------------------------ |
| 200    | **`OK`**                               | 客户端请求成功，即**处理成功**，这是我们最想看到的状态码     |
| 302    | **`Found`**                            | 指示所请求的资源已移动到由`Location`响应头给定的 URL，浏览器会自动重新访问到这个页面 |
| 304    | **`Not Modified`**                     | 告诉客户端，你请求的资源至上次取得后，服务端并未更改，你直接用你本地缓存吧。隐式重定向 |
| 400    | **`Bad Request`**                      | 客户端请求有**语法错误**，不能被服务器所理解                 |
| 403    | **`Forbidden`**                        | 服务器收到请求，但是**拒绝提供服务**，比如：没有权限访问相关资源 |
| 404    | **`Not Found`**                        | **请求资源不存在**，一般是URL输入有误，或者网站资源被删除了  |
| 428    | **`Precondition Required`**            | **服务器要求有条件的请求**，告诉客户端要想访问该资源，必须携带特定的请求头 |
| 429    | **`Too Many Requests`**                | **太多请求**，可以限制客户端请求某个资源的数量，配合 Retry-After(多长时间后可以请求)响应头一起使用 |
| 431    | **` Request Header Fields Too Large`** | **请求头太大**，服务器不愿意处理请求，因为它的头部字段太大。请求可以在减少请求头域的大小后重新提交。 |
| 405    | **`Method Not Allowed`**               | 请求方式有误，比如应该用GET请求方式的资源，用了POST          |
| 500    | **`Internal Server Error`**            | **服务器发生不可预期的错误**。服务器出异常了，赶紧看日志去吧 |
| 503    | **`Service Unavailable`**              | **服务器尚未准备好处理请求**，服务器刚刚启动，还未初始化好   |
| 511    | **`Network Authentication Required`**  | **客户端需要进行身份验证才能获得网络访问权限**               |



## 10.Tomcat

### 1.简介

![image-20230214145120166](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141451251.png)



![image-20230214145655308](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141456381.png)



![image-20230214145804897](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141458964.png)



### 2.安装、卸载、启动、关闭、配置、部署项目

![image-20230214145830370](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141458451.png)



![image-20230214151310745](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141513835.png)



```xml
    <Connector port="8080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
```



![image-20230214152451335](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141524397.png)

### **3.IDEA中创建Maven Web项目**

![image-20230214153135784](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141531867.png)



![image-20230214162606074](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141626166.png)



![image-20230214164119145](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141641238.png)



### 4.IDEA中使用Tomcat

![image-20230214164658094](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141646182.png)



![image-20230214165735533](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141657591.png)



![image-20230214165559996](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141656057.png)



![image-20230214164740378](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302141647464.png)





```xml
  <build>
    <plugins>
      <!--tomcat插件-->
      <plugin>
        <groupId>org.apache.tomcat.maven</groupId>
        <artifactId>tomcat7-maven-plugin</artifactId>
        <version>2.2</version>
        <configuration>
          <port></port>
        </configuration>
      </plugin>
    </plugins>
  </build>
```



## 11.Servlet

![image-20230214204835350](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142048454.png)





### 1.快速入门

![image-20230214205302376](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142053458.png)



```java
package com.momo.web;

import javax.servlet.*;
import javax.servlet.annotation.WebServlet;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet("/demo1")
public class ServletDemo1 implements Servlet {

    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("servlet hello world~");
    }
    
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
    }
    
    @Override
    public ServletConfig getServletConfig() {
        return null;
    }
    
    @Override
    public String getServletInfo() {
        return null;
    }
    
    @Override
    public void destroy() {
    }
}

```





### 2.Servlet执行流程

![image-20230214211706179](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142117354.png)



### 3.Servlet生命周期

![image-20230214214340918](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142143007.png)



![image-20230214213319005](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142133078.png)



![image-20230214213249687](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142132776.png)

```java
package com.momo.web;

import javax.servlet.*;
import javax.servlet.annotation.WebServlet;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet(urlPatterns = "/demo2",loadOnStartup = 1)
public class ServletDemo2 implements Servlet {

    /**
    * 初始化方法
    * 1.调用时机：默认情况下，Servlet被第一次访问时，调用
    *   loadOnStartup
    * 2.调用次数：1次
    * */
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
        System.out.println("init...");
    }

    /**
     * 提供服务
     * 1.调用时机：每一次Servlet被调用时
     * 2.调用次数：多次
     * @param servletRequest
     * @param servletResponse
     * @throws ServletException
     * @throws IOException
     */
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("servlet hello world~");
    }

    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    @Override
    public String getServletInfo() {
        return null;
    }

    /**
     * 销毁方法：
     * 1.调用时机：内存释放或者服务器关闭的时候，Servlet对象会被销毁
     * 2.调用次数：1次
     */
    @Override
    public void destroy() {
        System.out.println("destroy~");
    }
}

```



![image-20230214214442250](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142144331.png)

```java
    private ServletConfig config;

    /**
    * 初始化方法
    * 1.调用时机：默认情况下，Servlet被第一次访问时，调用
    *   loadOnStartup
    * 2.调用次数：1次
    * */
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
        this.config = servletConfig;
        System.out.println("init...");
    }

    /**
     * 提供服务
     * 1.调用时机：每一次Servlet被调用时
     * 2.调用次数：多次
     * @param servletRequest
     * @param servletResponse
     * @throws ServletException
     * @throws IOException
     */
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("servlet hello world~");
    }

    @Override
    public ServletConfig getServletConfig() {
        return config;
    }
```





### 4.Servlet体系结构

![image-20230214215320663](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142153790.png)

![image-20230214224249027](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142242100.png)

```java
@WebServlet("/demo4")
public class ServletDemo4 extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("get...");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("post...");
    }
}
```





### 5.Servlet urlPattern配置

![image-20230214224508022](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142245098.png)

```java
/**
 * @author momo~
 * @version 1.0
 * urlPattern:一个Servlet可以配置多个访问路径
 */
@WebServlet(urlPatterns = {"/demo7","/demo8"})
public class ServletDemo7 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("demo7 get...");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```



![image-20230214231217116](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142312210.png)



```java
 *  精确匹配
 */
@WebServlet(urlPatterns = "/user/select")
```



```java
 *  目录匹配 ：/user/*
 */
@WebServlet(urlPatterns = "/user/*")
```



```java
 *  扩展名匹配 ：*.do
 */
@WebServlet(urlPatterns = "*.do")
```



```java
 *  任意匹配 ：/
 */
@WebServlet(urlPatterns = "/")
```



```java
 *  任意匹配 ：/*
 */
@WebServlet(urlPatterns = "/*")
```



### 6.XML配置方式编写Servlet

![image-20230214234802683](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302142348772.png)

```xml
  <!--Servlet全类名-->

  <servlet>
    <servlet-name>demo13</servlet-name>
    <servlet-class>com.momo.web.ServletDemo13</servlet-class>
  </servlet>

  <!--Servlet访问路径-->
  <servlet-mapping>
    <servlet-name>demo13</servlet-name>
    <url-pattern>/demo13</url-pattern>
  </servlet-mapping>
```



## 12.Request & Response

![image-20230215102529534](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151025633.png)



```java
package com.momo.web;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet("/demo1")
public class ServletDemo1 extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //使用request对象获取请求数据
        String name = req.getParameter("name");

        //使用response对象 设置响应数据
        resp.setHeader("content-type","text/html;charset=utf-8");
        resp.getWriter().write("<h1>" + name + ",欢饮您！");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("post...");
    }
}

```





![image-20230215102453589](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151024647.png)



### 1.Request继承体系

![image-20230215103359230](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151033326.png)



```java
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println(req);
    }
```



![image-20230215103616370](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151036416.png)



### 2.Request获取请求数据

![image-20230215111139419](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151111548.png)



```java
package com.momo.web;

import javax.jws.soap.SOAPBinding;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet("/req1")
public class RequestDemo1 extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //String getMethod():获取请求方式：GET
        String method = req.getMethod();
        System.out.println(method);//GET

        //获取虚拟目录，项目访问路径
        String contextPath = req.getContextPath();
        System.out.println(contextPath);///request-demo

        //获取URL(统一资源定位符)
        StringBuffer requestURL = req.getRequestURL();
        System.out.println(requestURL.toString());
        //http://localhost:8080/request-demo/req1

        //获取URI(统一资源标识符)
        String requestURI = req.getRequestURI();
        System.out.println(requestURI);
        ///request-demo/req1

        //获取请求参数（GET方式）
        String queryString = req.getQueryString();
        System.out.println(queryString);
        //name=momo

        //获取请求头 user-agent：浏览器版本信息
        String header = req.getHeader("user-agent");
        System.out.println(header);
        //Mozilla/5.0 (Windows NT 10.0; Win64; x64)
        // AppleWebKit/537.36 (KHTML, like Gecko)
        // Chrome/110.0.0.0 Safari/537.36

    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取post请求体:请求参数
        //1.获取字符输入流
        BufferedReader bufferedReader = req.getReader();
        //2.读取数据
        String line = bufferedReader.readLine();
        System.out.println(line);
        //username=wujunhua7&password=123
    }
}

```



![image-20230215111615797](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151116914.png)



![image-20230215114822202](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151148289.png)

```java
package com.momo.web;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.util.Map;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet("/req2")
public class RequestDemo2 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //GET请求逻辑
//        System.out.println("get...");

        //1.获取所有参数的Map集合
        Map<String, String[]> parameterMap = req.getParameterMap();
        for (String key : parameterMap.keySet()) {
            //username:zhangsan
            System.out.print(key+":");

            //获取值
            for (String value : parameterMap.get(key)) {
                System.out.print(value + " ");
            }
            System.out.println();

        }

        //2.根据key获取参数值，数组
        for (String hobby : req.getParameterValues("hobby")) {
            System.out.println(hobby);
        }

        //3.根据key获取单个参数值
        String username = req.getParameter("username");
        String password = req.getParameter("password");
        System.out.println(username);
        System.out.println(password);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //POST请求逻辑
        this.doGet(req,resp);
    }
}

```



![image-20230215114946222](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151149317.png)

```java
package com.momo.web; /**
 * @author momo~
 * @version 1.0
 */

import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.*;
import java.io.IOException;

@WebServlet("/RequestServlet5")
public class RequestServlet5 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```





**请求参数中文乱码问题**

![image-20230215125313297](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151253395.png)





```java
package com.momo.web; /**
 * @author momo~
 * @version 1.0
 * 中文乱码问题
 */

import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.*;
import java.io.IOException;
import java.nio.charset.StandardCharsets;

@WebServlet("/req5")
public class RequestServlet5 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.解决乱码问题(post请求方式)
        request.setCharacterEncoding("UTF-8");//设置字符输入流的编码

        //2.获取username
        String username = request.getParameter("username");
        System.out.println("解决乱码前：" + username);

        //3.GET,获取参数的方式：getQueryString
        //乱码原因：tomcat进行URL解码，默认的字符集是ISO-8859-1

        //解决乱码问题(get请求方式)
        //先转为字节数组，后字节数组解码
        username = new String(username.getBytes("ISO-8859-1"), StandardCharsets.UTF_8);

        System.out.println("解决乱码后：" + username);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```



![image-20230215125424531](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151254640.png)



### 3.Request请求转发

![image-20230215131113070](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151311153.png)





```java
@WebServlet("/reqF")
public class RequestServlet_Forward extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demoForward");

        //存储数据
        request.setAttribute("msg","hello");

        //请求转发
        request.getRequestDispatcher("/req6").forward(request,response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```



```java
@WebServlet("/req6")
public class RequestServlet6 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo6");

        //获取数据
        Object msg = request.getAttribute("msg");
        System.out.println(msg);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```



![image-20230215131012451](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151310531.png)



### 4.Response设置响应数据

![image-20230215131645802](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151316887.png)



### 5.Response完成重定向

![image-20230215132259205](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151322290.png)

![image-20230215140122552](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302151401711.png)



```java
package com.momo.web.response; /**
 * @author momo~
 * @version 1.0
 */

import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.*;
import java.io.IOException;

@WebServlet("/resp1")
public class ResponseServletDemo1 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("resp1...");

        //重定向
        //1.设置响应状态码 302
//        response.setStatus(302);
//        //2.设置响应头
//        response.setHeader("Location","/request-demo/resp2");

        //简化
        response.sendRedirect("/request-demo/resp2");
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```



![image-20230216121946170](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161219328.png)

```java
//动态获取虚拟目录
String contextPath = request.getContextPath();
response.sendRedirect(contextPath+"/resp2");
```



### 6.Response响应字符数据

![image-20230216123407340](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161234447.png)

```java
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html;charset=utf-8");
        //1.获取字符输出流
        PrintWriter writer = response.getWriter();
        //content-type
        //response.setHeader("content-type","text/html");

        writer.write("宁哈");
        writer.write("<h1>bbb</h1>");

        //细节：流不需要关闭

    }
```



### 7.Response响应字节数据

![image-20230216130707153](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161307274.png)



```xml
    <dependency>
      <groupId>commons-io</groupId>
      <artifactId>commons-io</artifactId>
      <version>2.6</version>
    </dependency>
  </dependencies>
```



```java
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        //读取文件
        FileInputStream fileInputStream = new FileInputStream("d://a.jpg");


        //获取字节输出流
        ServletOutputStream outputStream = response.getOutputStream();

        //完成流的copy
//        byte[] bytes = new byte[1024];
//        int len = 0;
//
//        while ((len = fileInputStream.read(bytes) )!= -1){
//            outputStream.write(bytes,0,len);
//        }

        //IOUtils工具类使用
        IOUtils.copy(fileInputStream,outputStream);

        fileInputStream.close();
    }
```



#### **案例：用户登录，用户注册准备**

![image-20230216131318818](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161313914.png)



![image-20230216132929642](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161329715.png)

##### 1.复制静态页面到webapp目录下

![image-20230216133500229](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161335279.png)

![image-20230216133437627](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161334688.png)





##### 2.创建db1数据库，创建tb_user表，创建User实体类

![image-20230216133658078](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161336123.png)

```mysql
-- 创建用户表
CREATE TABLE tb_user(
	id int primary key auto_increment,
	username varchar(20) unique,
	password varchar(32)
);

-- 添加数据
INSERT INTO tb_user(username,password) values('zhangsan','123'),('lisi','234');

SELECT * FROM tb_user;

```



##### 3.导入MyBatis坐标，MySQL驱动坐标

```xml
    <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis</artifactId>
      <version>3.5.5</version>
    </dependency>

    <dependency>
      <groupId>mysql</groupId>
      <artifactId>mysql-connector-java</artifactId>
      <version>8.0.32</version>
    </dependency>
```



##### 4.创建mybatis-config,xml核心配置文件，UserMapper.xml映射文件，UserMapper接口

![image-20230216134109492](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161341542.png)

![image-20230216134310158](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161343227.png)



```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
    <!--起别名-->
    <typeAliases>
        <package name="com.itheima.pojo"/>
    </typeAliases>

    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///db1?useSSL=false&amp;useServerPrepStmts=true"/>
                <property name="username" value="root"/>
                <property name="password" value="root"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <!--扫描mapper-->
        <package name="com.momo.mapper"/>
    </mappers>
</configuration>
```





#### 用户登录

![image-20230216134521162](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161345260.png)

![image-20230216140902820](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161409870.png)



![image-20230216141124414](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161411462.png)

```java
public interface UserMapper {

    /**
     * 根据用户名和密码查询用户
     * @param username
     * @param password
     * @return
     */
    @Select("select  * from tb_user where username = #{username} and password = #{password}")
    User select(@Param("username") String username,@Param("password") String password);
}
```





```java
package com.momo.web; /**
 * @author momo~
 * @version 1.0
 */

import com.momo.mapper.UserMapper;
import com.momo.pojo.User;
import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.*;
import java.io.IOException;
import java.io.InputStream;
import java.io.PrintWriter;

@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.接收用户名密码
        String username = request.getParameter("username");
        String password = request.getParameter("password");

        //2.调用对应MyBatis
        //2.1获取SqlSessionFactory对象
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.2获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //2.3获取Mapper
        UserMapper userMapper = sqlSession.getMapper(UserMapper.class);

        //2.4调用方法
        User user = userMapper.select(username, password);

        //2.5释放资源
        sqlSession.close();

        //获取字符输出流，并设置content type
        response.setContentType("text/html;charset=utf-8");
        PrintWriter writer = response.getWriter();
        //3.判断user是否为null
        if (user != null){
            //登录成功
            writer.write("登陆成功");
        } else {
            //登录失败
            writer.write("登录失败");
        }
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```



![image-20230216141153716](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161411769.png)

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.momo.mapper.UserMapper">

</mapper>
```



![image-20230216141222672](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161412775.png)



![image-20230216141236015](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161412057.png)



#### 用户注册

![image-20230216141854896](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161418992.png)



```java
    /**
     * 新增
     * @param user
     * @return
     */
    @Insert("insert into tb_user values(null,#{username},#{password})")
    int add(User user);
```



```java
package com.momo.web; /**
 * @author momo~
 * @version 1.0
 */

import com.momo.mapper.UserMapper;
import com.momo.pojo.User;
import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.*;
import java.io.IOException;
import java.io.InputStream;
import java.io.PrintWriter;

@WebServlet("/RegisterServlet")
public class RegisterServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.接收用户名密码
        request.setCharacterEncoding("utf-8");
        String username = request.getParameter("username");
        String password = request.getParameter("password");

        //2.调用对应MyBatis
        //2.1获取SqlSessionFactory对象
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.2获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //2.3获取Mapper
        UserMapper userMapper = sqlSession.getMapper(UserMapper.class);

        //2.4调用方法
        User user = userMapper.select(username, password);




        User user1 = new User();
        user1.setUsername(username);
        user1.setPassword(password);

        //获取字符输出流，并设置content type
        response.setContentType("text/html;charset=utf-8");
        PrintWriter writer = response.getWriter();

        if (user != null){
            //注册失败
            writer.write("已经该用户");
        } else {
            //开始调用add()
            int count = userMapper.add(user1);
            sqlSession.commit();
            //2.5释放资源
            sqlSession.close();
            if (count > 0){
                writer.write("新增成功" + user1);
            } else {
                writer.write("新增失败");
            }
        }


    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```



![image-20230216153012037](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161530098.png)



#### 代码优化

![image-20230216155106067](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302161551152.png)

 

```java
package com.momo.util;

import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;

/**
 * @author momo~
 * @version 1.0
 */
public class SqlSessionFactoryUtils {
    private static SqlSessionFactory sqlSessionFactory;


    static {
        //2.1获取SqlSessionFactory对象
        //静态代码块会随着类的加载而自动执行，且只执行一次
        try {
            String resource = "mybatis-config.xml";
            InputStream inputStream = Resources.getResourceAsStream(resource);
            sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }

    public static SqlSessionFactory getSqlSessionFactory(){
        return sqlSessionFactory;
    }
}

```



## 13.JSP

![image-20230216211405304](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162114395.png)



### 1.JSP快速入门

![image-20230216211848258](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162118347.png)



```xml
    <!--JSP坐标-->
    <dependency>
      <groupId>javax.servlet.jsp</groupId>
      <artifactId>jsp-api</artifactId>
      <version>2.2</version>
      <scope>provided</scope>
    </dependency>
```



```jsp
<%--
  Created by IntelliJ IDEA.
  User: mo
  Date: 2023/2/16
  Time: 18:02
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>

<h1>jsp,hello world</h1>

<%
    System.out.println("hello,jsp~");
%>

</body>
</html>

```



### 2.JSP原理

![image-20230216213144318](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162131415.png)



![image-20230216213404052](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162134153.png)





### 3.JSP脚本

![image-20230216214033931](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162140006.png)

```jsp
<%--
  Created by IntelliJ IDEA.
  User: mo
  Date: 2023/2/16
  Time: 18:02
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>

<h1>jsp,hello world</h1>

<%
    System.out.println("hello,jsp~");
    int i = 3;
%>

<%="hello"%>
<%=i%>

<%!
    void show(){};
    String name = "zhangsan";
%>

</body>
</html>

```



![image-20230216214145323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162141382.png)

![image-20230216220509408](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162205495.png)

```jsp
<%@ page import="com.itheima.pojo.Brand" %>
<%@ page import="java.util.ArrayList" %>
<%@ page import="java.util.List" %><%--
  Created by IntelliJ IDEA.
  User: mo
  Date: 2023/2/16
  Time: 21:46
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%
    //查询数据库
    List<Brand> brands = new ArrayList<Brand>();
    brands.add(new Brand(1,"三只松鼠","三只松鼠",100,"三只松鼠，好吃不上火",1));
    brands.add(new Brand(2,"优衣库","优衣库",200,"优衣库，服适人生",0));
    brands.add(new Brand(3,"小米","小米科技有限公司",1000,"为发烧而生",1));
%>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<input type="button" value="新增"><br>
<hr>
<table border="1" cellspacing="0" width="800">
    <tr>
        <th>序号</th>
        <th>品牌名称</th>
        <th>企业名称</th>
        <th>排序</th>
        <th>品牌介绍</th>
        <th>状态</th>
        <th>操作</th>

    </tr>


    <%
        for (int i = 0; i < brands.size(); i++) {
            Brand brand = brands.get(i);
    %>
    <tr align="center">
        <td><%=brand.getId()%></td>
        <td><%=brand.getBrandName()%></td>
        <td><%=brand.getCompanyName()%></td>
        <td><%=brand.getOrdered()%></td>
        <td><%=brand.getDescription()%></td>
        <%
            if (brand.getStatus() == 1){
        %>
        <td><%="启用"%></td>
        <%
            } else {
        %>
        <td><%="禁用"%></td>
        <%
            }
        %>
        <td><a href="#">修改</a> <a href="#">删除</a></td>
    </tr>
    <%
        }
    %>
</table>

</body>
</html>
```



### 4.EL表达式

![image-20230216221747361](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162217458.png)





![image-20230216233249533](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162332630.png)

```java
package com.itheima.web; /**
 * @author momo~
 * @version 1.0
 */

import com.itheima.pojo.Brand;

import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.*;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

@WebServlet("/demo1")
public class ServletDemo1 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.准备数据
        List<Brand> brands = new ArrayList<Brand>();
        brands.add(new Brand(1,"三只松鼠","三只松鼠",100,"三只松鼠，好吃不上火",1));
        brands.add(new Brand(2,"优衣库","优衣库",200,"优衣库，服适人生",0));
        brands.add(new Brand(3,"小米","小米科技有限公司",1000,"为发烧而生",1));

        //2.存储到request域中
        request.setAttribute("brands",brands);

        //3.转发到el-demo.jsp
        request.getRequestDispatcher("/el-demo.jsp").forward(request,response);

    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```



```jsp
<%--
  Created by IntelliJ IDEA.
  User: mo
  Date: 2023/2/16
  Time: 22:19
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" isELIgnored="false" %>
<html>
<head>
    <title>Title</title>
</head>
<body>

    ${brands}

</body>
</html>

```

![image-20230216233434695](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162334758.png)



### 5.JSTL标签

![image-20230216233721809](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162337965.png)





![image-20230216233743318](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302162337405.png)



```xml
    <!--JSTL标签库-->
    <dependency>
      <groupId>javax.servlet.jsp.jstl</groupId>
      <artifactId>jstl</artifactId>
      <version>1.2</version>
    </dependency>

    <dependency>
      <groupId>taglibs</groupId>
      <artifactId>standard</artifactId>
      <version>1.1.2</version>
    </dependency>
```



```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```



```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" isELIgnored="false"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<html>
<head>
    <title>Title</title>
</head>
<body>

    <%--
        c:if 完成逻辑判断，替换if else
    --%>

<%--    <c:if test="true">--%>
<%--        <h1>true</h1>--%>
<%--    </c:if>--%>

<%--    <c:if test="false">--%>
<%--        <h1>false</h1>--%>
<%--    </c:if>--%>

    <c:if test="${status == 1}">
        启用
    </c:if>

    <c:if test="${status == 0}">
        禁用
    </c:if>

</body>
</html>
```



![image-20230217104411572](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171044677.png)



```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" isELIgnored="false"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<input type="button" value="新增"><br>
<hr>
<table border="1" cellspacing="0" width="800">
    <tr>
        <th>序号</th>
        <th>品牌名称</th>
        <th>企业名称</th>
        <th>排序</th>
        <th>品牌介绍</th>
        <th>状态</th>
        <th>操作</th>

    </tr>

    <c:forEach items="${brands}" var="brand" varStatus="status">
        <tr align="center">
<%--            <td>${brand.id}</td>--%>
            <td>${status.index}</td>
            <td>${brand.brandName}</td>
            <td>${brand.companyName}</td>
            <td>${brand.ordered}</td>
            <td>${brand.description}</td>

            <c:if test="${brand.status == 1}">
                <td>启用</td>
            </c:if>
            <c:if test="${brand.status != 1}">
                <td>禁用</td>
            </c:if>
            <td><a href="#">修改</a> <a href="#">删除</a></td>
        </tr>
    </c:forEach>

</table>
    <c:forEach begin="1" end="10" step="1" var="i">
        <a href="#">${i}</a>
    </c:forEach>
</body>
</html>
```



![image-20230217104920158](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171049210.png)



### 6.MVC模式和三层架构

![image-20230217105531380](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171055474.png)



![image-20230217110212778](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171102889.png)





![image-20230217110349158](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171103244.png)



### 7.案例

![image-20230217150437952](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171504039.png)



#### 1.准备环境

![ ](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171505148.png)

![image-20230217152037975](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171520029.png)



![image-20230217152101927](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171521971.png)



![image-20230217152123344](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171521392.png)



```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>org.example</groupId>
  <artifactId>brand-demo</artifactId>
  <version>1.0-SNAPSHOT</version>

  <packaging>war</packaging>

  <name>brand-demo Maven Webapp</name>
  <!-- FIXME change it to the project's website -->
  <url>http://www.example.com</url>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.7</maven.compiler.source>
    <maven.compiler.target>1.7</maven.compiler.target>
  </properties>

  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>

    <!--MyBatis-->
    <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis</artifactId>
      <version>3.5.5</version>
    </dependency>

    <!--mysql-->
    <dependency>
      <groupId>mysql</groupId>
      <artifactId>mysql-connector-java</artifactId>
      <version>8.0.32</version>
    </dependency>

    <!--servlet-->
    <dependency>
      <groupId>javax.servlet</groupId>
      <artifactId>javax.servlet-api</artifactId>
      <version>4.0.1</version>
      <scope>provided</scope>
    </dependency>

    <!--jsp-->
    <dependency>
      <groupId>javax.servlet.jsp</groupId>
      <artifactId>jsp-api</artifactId>
      <version>2.2</version>
    </dependency>

    <!--jstl-->
    <dependency>
      <groupId>jstl</groupId>
      <artifactId>jstl</artifactId>
      <version>1.2</version>
    </dependency>

    <dependency>
      <groupId>taglibs</groupId>
      <artifactId>standard</artifactId>
      <version>1.1.2</version>
    </dependency>
  </dependencies>

    
  <!--tomcat-->
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.tomcat.maven</groupId>
        <artifactId>tomcat7-maven-plugin</artifactId>
        <version>2.2</version>
      </plugin>
    </plugins>
  </build>
</project>

```



![image-20230217152540924](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171525977.png)



![image-20230217152701062](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171527106.png)



![image-20230217152729105](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171527148.png)





![image-20230217154002012](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171540096.png)



#### 2.查询

![image-20230217154954028](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302171549135.png)



```java
public interface BrandMapper {

    @Select("select * from tb_brand")
    @ResultMap("brandResultMap")
    List<Brand> selectAll();
}
```



#### 3.添加

![image-20230217212630425](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302172126531.png)



```java
@WebServlet("/addServlet")
public class AddServlet extends HttpServlet {

    private BrandService service = new BrandService();

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        //处理乱码
        request.setCharacterEncoding("utf-8");

        //接收表单提交的数据，封装为对象
        String brandName = request.getParameter("brandName");
        String companyName = request.getParameter("companyName");
        String ordered = request.getParameter("ordered");
        String description = request.getParameter("description");
        String status = request.getParameter("status");

        //封装为对象
        Brand brand = new Brand();
        brand.setBrandName(brandName);
        brand.setCompanyName(companyName);
        brand.setOrdered(Integer.parseInt(ordered));
        brand.setDescription(description);
        brand.setStatus(Integer.parseInt(status));

        //调用service，完成添加
        service.add(brand);

        //转发
        request.getRequestDispatcher("/selectAllServlet").forward(request,response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```







#### 4.修改

![image-20230217220508808](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302172205911.png)



![image-20230217224229824](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302172242921.png)



## 14.会话

![image-20230218185418747](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181854886.png)



### 1.Cookie

![image-20230218194013301](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181940469.png)





```java
        //发送cookie
        //1.创建cookie对象
        Cookie cookie = new Cookie("username", "zs");

        //2.发送cookie
        response.addCookie(cookie);
```



![image-20230218193115907](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181931973.png)





```java
        //获取cookie
        //1.获取cookie数组,并且遍历
        for (Cookie cookie : request.getCookies()) {

            //2.获取数据
            String name = cookie.getName();

            if ("username".equals(name)){
                String value = cookie.getValue();
                System.out.println(name + ":" + value);
                break;
            }
        }
```

![image-20230218193953624](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181939688.png)



#### **Cookie原理**

![image-20230218194718063](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181947200.png)



![image-20230218195059121](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181950168.png)





![image-20230218195011959](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302181950011.png)





#### Cookie细节

![image-20230218201154998](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182011091.png)



```java
        //设置存活时间  7天
        cookie.setMaxAge(60*60*24*7);
```

![image-20230218200041205](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182000273.png)





```java
//url编码
value = URLEncoder.encode(value, "utf-8");
```



```java
//URL解码
value = URLDecoder.decode(value, "utf-8");
```



### 2.Session

![image-20230218202509137](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182025237.png)



```java
//存储数据到session中
//1.获取Session对象
HttpSession session = request.getSession();
//2.存储数据
session.setAttribute("username","zs");
```



```java
//获取数据
//1.获取session对象
HttpSession session = request.getSession();
//2.获取数据
Object username = session.getAttribute("username");
System.out.println(username);
```



#### session原理

![image-20230218203322341](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182033426.png)

![image-20230218203503664](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182035724.png)





#### session细节

![image-20230218204813568](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182048662.png)



```xml
  <session-config>
    <session-timeout>30</session-timeout>
  </session-config>
```



```java
//session销毁
session.invalidate();
```



![image-20230218205933092](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182059250.png)



### 3.案例

![image-20230218210444844](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182104942.png)



#### 1.用户登录

![image-20230218222946454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182229635.png)



```java


```





#### 2.记住用户

![image-20230218224900939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182249035.png)









#### 3.用户注册

![image-20230218231916654](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302182319762.png)



#### 4.验证码

![image-20230219115028477](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191150562.png)



```java

@WebServlet("/checkCodeServlet")
public class CheckCodeServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        ServletOutputStream os = response.getOutputStream();
        CheckCodeUtil.outputVerifyImage(100, 50, os, 4);

    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}

```



```jsp
            <tr>
                <td>验证码</td>
                <td class="inputs">
                    <input name="checkCode" type="text" id="checkCode">
                    <img id="checkCodeImage" src="/brand-demo/checkCodeServlet">
                    <a href="#" id="changeImg" >看不清？</a>
                </td>
            </tr>


<script>
    document.getElementById("changeImg").onclick = function () {
        document.getElementById("checkCodeImage").src = "/brand-demo/checkCodeServlet?" + new Date().getMilliseconds();
    }
</script>
```



![image-20230219120449454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191204565.png)



```java
//生成验证码
ServletOutputStream os = response.getOutputStream();
String checkCode = CheckCodeUtil.outputVerifyImage(100, 50, os, 4);

//存入session
HttpSession session = request.getSession();
session.setAttribute("checkCodeGen",checkCode);
```



```java
//获取用户输入验证码
String checkCode = request.getParameter("checkCode");

//获取程序生成验证码:从session中获取
HttpSession session = request.getSession();
String checkCodeGen = (String) session.getAttribute("checkCodeGen");

//比对
if (!checkCodeGen.equalsIgnoreCase(checkCode)){

    request.setAttribute("register_msg","验证码错误");
    request.getRequestDispatcher("/register.jsp").forward(request,response);

    //不允许注册
    return;
}
```



## 15.Filter

![image-20230219121235201](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191212302.png)



![image-20230219121526941](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191215040.png)



```java
package com.momo.web.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
   Filter快速入门
 */
@WebFilter("/*")
public class FilterDemo implements Filter {

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("FilterDemo...");

        //放行
        filterChain.doFilter(servletRequest,servletResponse);
    }


    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
    }
    
    @Override
    public void destroy() {
    }
}

```



![image-20230219123835016](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191238125.png)



```java
package com.momo.web.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
@WebFilter("/*")
public class FilterDemo implements Filter {

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("FilterDemo1...");

        //放行前：对request数据进行处理

        //放行
        filterChain.doFilter(servletRequest,servletResponse);

        //放行后：对response数据进行处理
        System.out.println("FilterDemo3...");
    }


    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
    }

    @Override
    public void destroy() {
    }
}

```



```jsp
<body>

<h1>hello jsp</h1>

<%
    System.out.println("2.hello jsp");
%>
</body>
```

![image-20230219123943346](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191239427.png)





![image-20230219125846920](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191258016.png)

![image-20230219130456825](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191304944.png)





![image-20230219132642849](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191326954.png)

```java
package com.itheima.web.filter; /**
 * @author momo~
 * @version 1.0
 * 登录验证过滤器
 */

import javax.servlet.*;
import javax.servlet.annotation.*;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpSession;
import java.io.IOException;

@WebFilter("/*")
public class LoginFilter implements Filter {
    public void init(FilterConfig config) throws ServletException {
    }

    public void destroy() {
    }

    @Override
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws ServletException, IOException {
        HttpServletRequest req = (HttpServletRequest) request;

        //判断访问资源路径是否跟登录注册相关
        String[] urls = {"/login.jsp","/imgs","/css","/loginServlet","register.jsp"
        ,"/registerServlet","checkCodeServlet"};
        //获取当前访问资源路劲
        String url = req.getRequestURL().toString();

        for (String u : urls){
            if (url.contains(u)){
                //放行
                chain.doFilter(request, response);
                return;
            }
        }

        //判断是否登录：session中是否有user
        HttpSession session = req.getSession();
        Object user = session.getAttribute("user");

        //判断user是否为null
        if (user != null){
            //已经登录
            chain.doFilter(request, response);
        } else {
            //没有登录，跳转登录页面且提示
            req.setAttribute("login_msg","您尚未登陆");
            req.getRequestDispatcher("/login.jsp").forward(request,response);
        }
    }
}

```





## 16.Listener

![image-20230219133056241](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191330350.png)



![image-20230219134030872](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191340969.png)



```java
@WebListener
public class ContextLoaderListener implements ServletContextListener {

    @Override
    public void contextInitialized(ServletContextEvent sce) {
        //加载资源
        System.out.println("ServletContextListener...");
    }

    @Override
    public void contextDestroyed(ServletContextEvent sce) {
        //释放资源
    }
}
```





## 17.AJAX

### 1.AJAX概述

![image-20230219150219609](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191502716.png)





![image-20230219150506538](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191505644.png)



![image-20230219150846946](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191508038.png)

### 2.AJAX快速入门

![image-20230219151357491](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191513602.png)



```java
@WebServlet("/ajaxServlet")
public class AjaxServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //响应数据
        response.getWriter().write("hello ajax");
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```



```html
<script>
    //创建核心对象
    var xhttp;
    if (window.XMLHttpRequest) {
        xhttp = new XMLHttpRequest();
    } else {
        // code for IE6, IE5
        xhttp = new ActiveXObject("Microsoft.XMLHTTP");
    }

    //发送请求
    xhttp.open("GET", "http://localhost:8080/ajax-demo/ajaxServlet");
    xhttp.send();

    //获取响应
    xhttp.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
            alert(this.responseText);
        }
    };
</script>
```





![image-20230219153415021](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191534083.png)



![image-20230219153511270](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191535327.png)



### 3.案例-验证用户是否存在

![image-20230219155848688](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191558794.png)

```java
@WebServlet("/selectUserServlet")
public class SelectUserServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        //接收用户名
        String username = request.getParameter("username");

        //调用service查询User对象
        boolean flag = true;

        //响应标记
        response.getWriter().write("" + flag);

    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```



```html
<script>
    //绑定失去焦点事件
    document.getElementById("username").onblur = function () {

        //获取用户输入
        var username = this.value;

        //发送ajax请求
        //创建核心对象
        var xhttp;
        if (window.XMLHttpRequest) {
            xhttp = new XMLHttpRequest();
        } else {
            // code for IE6, IE5
            xhttp = new ActiveXObject("Microsoft.XMLHTTP");
        }

        //发送请求
        xhttp.open("GET", "http://localhost:8080/ajax-demo/selectUserServlet?username=" + username);
        xhttp.send();

        //获取响应
        xhttp.onreadystatechange = function() {
            if (this.readyState == 4 && this.status == 200) {
                //alert(this.responseText);
                //判断
                if (this.responseText == "true"){
                    //用户名存在
                    //显示提示信息
                    document.getElementById("username_err").style.display = "";
                } else {
                    //用户名不存在，清除提示信息
                    document.getElementById("username_err").style.display = "none";
                }
            }
        };
    }
</script>
```



![image-20230219155959279](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191559347.png)





### 4.Axios异步框架

![image-20230219160352186](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191603286.png)



![image-20230219183258909](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191832040.png)





```html
<script>
    //get
    axios({
        method:"get",
        url:"http://localhost:8080/ajax-demo/axiosServlet?username=zhangsan"
    }).then(function (resp) {
        alert(resp.data)
    })

    //post
    axios({
        method: "post",
        url: "http://localhost:8080/ajax-demo/axiosServlet",
        data:"username"
    }).then(function (resp) {
        alert(resp.data)
    })

</script>
```



![image-20230219185046278](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191850389.png)





```html
<script>
axios.get("http://localhost:8080/ajax-demo/axiosServlet?username=zhangsan").then(function (resp) {
alert(resp.data)
})

axios.post("http://localhost:8080/ajax-demo/axiosServlet","username=zhangsan").then(function (resp) {
alert(resp.data)
})
</script>
```



![image-20230219190020454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191900560.png)



```html
<script>
axios({
            method: "get",
            url: "http://localhost:8080/ajax-demo/selectUserServlet?username=" + username
        }).then(function (resp) {
            if (resp.data.toString() == "true") {
                //console.log(1);
                //用户名存在
                //显示提示信息
                document.getElementById("username_err").style.display = "";
            } else {
                //用户名不存在，清除提示信息
                //console.log(2);
                document.getElementById("username_err").style.display = "none";
            }
        })
</script>
```



```java
@WebServlet("/selectUserServlet")
public class SelectUserServlet extends HttpServlet {

    private UserService userService = new UserService();

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {


        //接收用户名
        String username = request.getParameter("username");
        
        //调用service查询User对象
        User user = userService.selectByUsername(username);

        if (user != null){
            //响应标记
            response.getWriter().write("" + true);
        } else {
            //响应标记
            response.getWriter().write("" + false);
        }

    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```





## 18.JSON

![image-20230219195241376](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191952479.png)



### 1.JSON基础语法

![image-20230219195612169](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302191956264.png)

```html
<script>
    //定义json
    var json = {
        "name":"zhangsan",
        "age":23,
        "addr":["北京","上海","天津"]
    }

    //获取值
    alert(json.name)
</script>
```



### 2.JSON数据与Java对象转换

![image-20230219200212014](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302192002118.png)

![image-20230219200237389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302192002499.png)



```xml
    <dependency>
      <groupId>com.alibaba</groupId>
      <artifactId>fastjson</artifactId>
      <version>2.0.24</version>
    </dependency>
```



```java
public class FastJsonDemo {
    public static void main(String[] args) {
        //将Java对象转成JSON字符串
        User user = new User();

        user.setId(1);
        user.setUsername("zhangsan");
        user.setPassword("123");

        String jsonString = JSON.toJSONString(user);
        System.out.println(jsonString);

        //将JSON字符串转成Java对象
        User u = JSON.parseObject("{\"id\":1,\"password\":\"123\",\"username\":\"zhangsan\"}", User.class);
        System.out.println(u);

    }
}
```



![image-20230219201355370](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302192013474.png)



### 3.案例

![image-20230219201459854](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302192014952.png)



![image-20230219201711252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302192017370.png)



```html
<script>
    //当页面加载完成后发送ajax请求
    window.onload = function (){
        //
        axios({
            method:"get",
            url:"http://localhost:8080/brand-demo/selectAllServlet"
        }).then(function (resp) {
            //获取数据
            let brands = resp.data;

            let tableData = "\n" +
                "    <tr>\n" +
                "        <th>序号</th>\n" +
                "        <th>品牌名称</th>\n" +
                "        <th>企业名称</th>\n" +
                "        <th>排序</th>\n" +
                "        <th>品牌介绍</th>\n" +
                "        <th>状态</th>\n" +
                "        <th>操作</th>\n" +
                "    </tr>";
            for (let i = 0; i < brands.length; i++) {
                let brand = brands[i];

                tableData += "\n" +
                    "    <tr align=\"center\">\n" +
                    "        <td>"+(i+1)+"</td>\n" +
                    "        <td>"+brand.brandName+"</td>\n" +
                    "        <td>"+brand.companyName+"</td>\n" +
                    "        <td>"+brand.ordered+"</td>\n" +
                    "        <td>"+brand.description+"</td>\n" +
                    "        <td>"+brand.status+"</td>\n" +
                    "\n" +
                    "        <td><a href=\"#\">修改</a> <a href=\"#\">删除</a></td>\n" +
                    "    </tr>"


            }
            document.getElementById("brandTable").innerHTML = tableData;
        })
    }
</script>
```



```java
@WebServlet("/selectAllServlet")
public class SelectAllServlet extends HttpServlet {
    private BrandService brandService = new BrandService();

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //调用service查询
        List<Brand> brands = brandService.selectAll();

        //将集合转换为JSON数据 序列化  反序列化
        String jsonString = JSON.toJSONString(brands);

        //把字符串显示
        response.setContentType("text/json;charset=utf-8");
        response.getWriter().write(jsonString);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doGet(request, response);
    }
}
```





![image-20230219205212907](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302192052030.png)





## 19.Vue

![image-20230220100755513](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201007630.png)



### 1.Vue快速入门

![image-20230220100940614](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201009700.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>

<div id="app">

    <input v-model="username">{{username}}

</div>

<script src="js/vue.js"></script>

<script>

    //1.创建vue核心对象
    new Vue({
        el:"#app",
        data(){
            return {
                username:""
            }
        }
        // data:function () {
        //     return {
        //         username:""
        //     }
        // }
    })

</script>

</body>
</html>
```

![image-20230220102408615](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201024676.png)





### 2.Vue常用指令

![image-20230220102516295](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201025386.png)



![image-20230220102531341](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201025429.png)



```html
<div id="app">

    <!--<a v-bind:href="url">点击</a>-->
    <a :href="url">点击</a>

    <input v-model="url">

</div>

<script src="js/vue.js"></script>

<script>

    //1.创建vue核心对象
    new Vue({
        el:"#app",
        data(){
            return {
                username:"",
                url:"https://www.baidu.com"
            }
        }
    });

</script>
```



![image-20230220105056696](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201050782.png)



```html
<div id="app">
    
    <input type="button" value="一个按钮" v-on:click="show()"><br>
    <input type="button" value="一个按钮" @click="show()">

</div>

<script src="js/vue.js"></script>

<script>
    //1.创建vue核心对象
    new Vue({
        el:"#app",
        data(){
            return {
                username:"",
                url:"https://www.baidu.com"
            }
        },
        methods:{
            show(){
                alert("我被点了");
            }
        }
    });
</script>
```



![image-20230220110542429](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201105518.png)

```html
<div id="app">

    <div v-if="count == 3">div1</div>
    <div v-else-if="count == 4">div2</div>
    <div v-else>div3</div>

    <hr>
    <div v-show="count == 3">div v-show</div>

    <br>
    <input v-model="count">

</div>

<script src="js/vue.js"></script>

<script>
    //1.创建vue核心对象
    new Vue({
        el:"#app",
        data(){
            return {
                username:"",
                url:"https://www.baidu.com",
                count:3
            }
        },
        methods:{
            show(){
                alert("我被点了");
            }
        }
    });
</script>
```



![image-20230220111647861](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201116914.png)

![image-20230220111802430](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201118497.png)



![image-20230220111830800](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201118892.png)

```html
<div id="app">
    <div v-for="addr in address">
        {{addr}} <br>
    </div>

    <hr>

    <div v-for="(addr,i) in address">
        {{i+1}}--{{addr}} <br>
    </div>
</div>

<script src="js/vue.js"></script>

<script>
    //1.创建vue核心对象
    new Vue({
        el:"#app",
        data(){
            return {
                username:"",
                url:"https://www.baidu.com",
                count:3,
                address:["北京","上海","西安"]
            }
        },
        methods:{
            show(){
                alert("我被点了");
            }
        }
    });
</script>
```



![image-20230220112517093](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201125150.png)



### 3.Vue生命周期

![image-20230220112707144](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201127232.png)

![image-20230220112835713](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201128808.png)



```html
<script>
    //1.创建vue核心对象
    new Vue({
        el:"#app",
        data(){
            return {
                username:"",
                url:"https://www.baidu.com",
                count:3,
                address:["北京","上海","西安"]
            }
        },
        methods:{
            show(){
                alert("我被点了");
            }
        },
        mounted(){
            alert("加载完成.。。")
        }
    });
</script>
```



![image-20230220113125338](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201131403.png)



### 4.案例

![image-20230220113213564](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201132654.png)

![image-20230220113329588](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201133684.png)





```html
<div id="app">

    <a href="addBrand.html"><input type="button" value="新增"></a><br>
    <hr>
    <table id="brandTable" border="1" cellspacing="0" width="100%">
        <tr>
            <th>序号</th>
            <th>品牌名称</th>
            <th>企业名称</th>
            <th>排序</th>
            <th>品牌介绍</th>
            <th>状态</th>
            <th>操作</th>
        </tr>

        <!--v-for-->

        <tr v-for="(brand,i) in brands" align="center">
            <td>{{i+1}}</td>
            <td>{{brand.brandName}}</td>
            <td>{{brand.companyName}}</td>
            <td>{{brand.ordered}}</td>
            <td>{{brand.description}}好吃不上火</td>
            <td>{{brand.statusStr}}</td>
            <td><a href="#">修改</a> <a href="#">删除</a></td>
        </tr>
    </table>
</div>
```





```html
<script>
    new Vue({
        el:"#app",
        data(){
            return{
                brands:[]
            }
        },
        mounted(){
            //页面加载完成后，发送异步请求，查询数据
            var _this = this;
            axios({
                method:"get",
                url:"http://localhost:8080/brand-demo/selectAllServlet"
            }).then(function (resp) {
                _this.brands = resp.data;
            })
        }
    })
</script>
```



![image-20230220122423157](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201224240.png)



![image-20230220122750308](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201227471.png)



```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>添加品牌</title>
</head>
<body>
<div id="app">
<h3>添加品牌</h3>
<form action="" method="post">
    品牌名称：<input v-model="brand.brandName" id="brandName" name="brandName"><br>
    企业名称：<input v-model="brand.companyName" id="companyName" name="companyName"><br>
    排序：<input v-model="brand.ordered" id="ordered" name="ordered"><br>
    描述信息：<textarea v-model="brand.description" rows="5" cols="20" id="description" name="description"></textarea><br>
    状态：
    <input v-model="brand.status" type="radio" name="status" value="0">禁用
    <input v-model="brand.status" type="radio" name="status" value="1">启用<br>

    <input @click="submitFrom" type="button" id="btn"  value="提交">
</form>
</div>
<script src="js/axios-0.18.0.js"></script>
<script src="js/vue.js"></script>

<script>

    new Vue({
        el:"#app",
        data(){
            return{
                brand:{}
            }
        },
        methods:{
            submitFrom(){
                var _this = this;
                //发送ajax请求
                axios({
                    method:"post",
                    url:"http://localhost:8080/brand-demo/addServlet",
                    data:_this.brand
                }).then(function (resp) {
                    //判断响应数据是否为success
                    if (resp.data == "success"){
                        location.href = "http://localhost:8080/brand-demo/brand.html"
                    }
                })
            }
        }
    })
    </script>
</body>
</html>
```



## 20.Element

![image-20230220124449864](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201244971.png)



### 1.Element快速入门

![image-20230220124524251](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201245346.png)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app">
    <el-row>
        <el-button type="danger">删除</el-button>
    </el-row>
</div>

<script src="js/vue.js"></script>
<script src="element-ui/lib/index.js"></script>
<link rel="stylesheet" href="element-ui/lib/theme-chalk/index.css">

<script>
    new Vue({
        el: "#app"
    })
</script>

</body>
</html>
```



![image-20230220125924138](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201259207.png)

### 2.Element布局

![image-20230220125939445](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201259535.png)





![image-20230220131201957](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201312029.png)



![image-20230220131136770](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201311847.png)



### 3.Element组件

![image-20230220131513741](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302201315849.png)

## 21.最终web案例

 ![image-20230220213237268](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202132419.png)

### 1.环境搭建

![image-20230220214313434](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202143511.png)

![image-20230220214353327](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202143386.png)





### 2.查询所有

![image-20230220222150604](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202221715.png)



```vue
    new Vue({
        el: "#app",
        //当页面加载完成后，发送异步请求获取数据
        mounted(){
            var _this = this;

            axios({
                method:"get",
                url:"http://localhost:8080/brand-case/selectAllServlet"
            }).then(function (resp) {
                _this.tableData = resp.data;
            })
        }
     })
```



![image-20230220230842812](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202308986.png)



![image-20230220231117656](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202311766.png)



![image-20230220231311390](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302202313554.png)





### 3.新增

![image-20230221104132167](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302211041314.png)



![image-20230221104353061](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302211043167.png)



![image-20230221104457483](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302211044573.png)



![image-20230221104655019](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302211046173.png)



![image-20230221104749649](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302211047793.png)



![image-20230221104943572](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302211049888.png)



```html
<script>
            // 添加数据
            addBrand(){
                //console.log(this.brand);
                //发送ajax异步请求，添加异步数据
                var _this = this;

                axios({
                    method: "post",
                    url: "http://localhost:8080/brand-case/addBrandServlet",
                    data: _this.brand
                }).then(function (resp) {
                    if (resp.data == "success"){
                        //添加成功

                        //关闭窗口
                        _this.dialogVisible = false;

                        //新增后刷新页面
                        _this.selectAll();

                        _this.$message({
                            message: '恭喜你，添加成功',
                            type: 'success'
                        });
                    }
                })
            },
</script>
```



### 4.Servlet代码优化

![image-20230222204909441](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302222049582.png)



```html
<script>
	            //查询所有方法
            selectAll(){
                var _this = this;

                axios({
                    method:"get",
                    url:"http://localhost:8080/brand-case/brand/selectAll"
                }).then(function (resp) {
                    _this.tableData = resp.data;
                })
            },
</script>
```



```java
@WebServlet("/brand/*")
public class BrandServlet extends BaseServlet{

    private BrandService brandService = new BrandServiceImpl();

    /**
     * 查询所有
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void selectAll(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //调用service方法
        List<Brand> brands = brandService.selectAll();

        //将list集合转为json
        String jsonString = JSON.toJSONString(brands);

        //写数据
        response.setContentType("text/json;charset=utf-8");
        response.getWriter().write(jsonString);
    }
```



 

### 5.批量删除

![image-20230223134948565](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302231349690.png)





### 6.分页查询

![image-20230223150625288](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302231506384.png)





![image-20230223151452467](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302231514573.png)





![image-20230223161212281](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302231612390.png)



### 7.条件查询

![image-20230223161532095](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302231615199.png)



![image-20230223172049551](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302231720662.png)



![image-20230223212139437](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232121521.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .el-table .warning-row {
            background: oldlace;
        }

        .el-table .success-row {
            background: #f0f9eb;
        }
    </style>

</head>
<body>
<div id="app">

    <!--搜索表单-->
    <el-form :inline="true" :model="brand" class="demo-form-inline">

        <el-form-item label="当前状态">
            <el-select v-model="brand.status" placeholder="当前状态">
                <el-option label="启用" value="1"></el-option>
                <el-option label="禁用" value="0"></el-option>
            </el-select>
        </el-form-item>

        <el-form-item label="企业名称">
            <el-input v-model="brand.companyName" placeholder="企业名称"></el-input>
        </el-form-item>

        <el-form-item label="品牌名称">
            <el-input v-model="brand.brandName" placeholder="品牌名称"></el-input>
        </el-form-item>

        <el-form-item>
            <el-button type="primary" @click="onSubmit">查询</el-button>
        </el-form-item>
    </el-form>

    <!--按钮-->

    <el-row>

        <el-button type="danger" plain @click="BatchDeletion">批量删除</el-button>
        <el-button type="primary" plain @click="dialogVisible = true">新增</el-button>

    </el-row>
    <!--添加数据对话框表单-->
    <el-dialog
            title="编辑品牌"
            :visible.sync="dialogVisible"
            width="30%"
            >

        <el-form ref="form" :model="brand" label-width="80px">
            <el-form-item label="品牌名称">
                <el-input v-model="brand.brandName"></el-input>
            </el-form-item>

            <el-form-item label="企业名称">
                <el-input v-model="brand.companyName"></el-input>
            </el-form-item>

            <el-form-item label="排序">
                <el-input v-model="brand.ordered"></el-input>
            </el-form-item>

            <el-form-item label="备注">
                <el-input type="textarea" v-model="brand.description"></el-input>
            </el-form-item>

            <el-form-item label="状态">
                <el-switch v-model="brand.status"
                           active-value="1"
                           inactive-value="0"
                ></el-switch>
            </el-form-item>


            <el-form-item>
                <el-button type="primary" @click="addBrand">提交</el-button>
                <el-button @click="dialogVisible = false">取消</el-button>
            </el-form-item>
        </el-form>

    </el-dialog>





    <!--表格-->
    <template>
        <el-table
                :data="tableData"
                style="width: 100%"
                :row-class-name="tableRowClassName"
                @selection-change="handleSelectionChange"
        >


            <el-table-column
                    prop="id"
                    type="selection"
                    width="55">
            </el-table-column>
            <el-table-column
                    type="index"
                    width="50">
            </el-table-column>

            <el-table-column
                    prop="brandName"
                    label="品牌名称"
                    align="center"
            >
            </el-table-column>
            <el-table-column
                    prop="companyName"
                    label="企业名称"
                    align="center"
            >
            </el-table-column>
            <el-table-column
                    prop="ordered"
                    align="center"
                    label="排序">
            </el-table-column>
            <el-table-column
                    prop="status"
                    align="center"
                    label="当前状态">
            </el-table-column>

            <el-table-column

                    prop="id"
                    align="center"
                    label="操作">

                <template slot-scope="scope">
                    <el-button type="primary" @click="selectById(scope.$index, scope.row)">修改</el-button>
                    <el-button type="danger" @click="deleteById(scope.$index, scope.row)">删除</el-button>

                    <!--修改数据对话框表单-->
                    <el-dialog
                            title="修改品牌"
                            :visible.sync="updatePage"
                            width="30%"
                    >

                        <el-form ref="form" :model="selectByIdData" label-width="80px">
                            <el-form-item label="品牌名称">
                                <el-input v-model="selectByIdData.brandName"></el-input>
                            </el-form-item>

                            <el-form-item label="企业名称">
                                <el-input v-model="selectByIdData.companyName"></el-input>
                            </el-form-item>

                            <el-form-item label="排序">
                                <el-input v-model="selectByIdData.ordered"></el-input>
                            </el-form-item>

                            <el-form-item label="备注">
                                <el-input type="textarea" v-model="selectByIdData.description"></el-input>
                            </el-form-item>

                            <el-form-item label="状态">
                                <el-switch v-model="selectByIdData.status"
                                           :active-value="1"
                                           :inactive-value="0"
                                ></el-switch>
                            </el-form-item>


                            <el-form-item>
                                <el-button type="primary" @click="updateById">提交</el-button>
                                <el-button @click="updatePage = false">取消</el-button>
                            </el-form-item>
                        </el-form>

                    </el-dialog>

                </template>

            </el-table-column>

        </el-table>
    </template>

    <!--分页工具条-->
    <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page="currentPage"
            :page-sizes="[5, 10, 15, 20]"
            :page-size="5"
            layout="total, sizes, prev, pager, next, jumper"
            :total="totalCount">
    </el-pagination>

</div>


<script src="js/vue.js"></script>
<script src="element-ui/lib/index.js"></script>
<script src="js/axios-0.18.0.js"></script>
<link rel="stylesheet" href="element-ui/lib/theme-chalk/index.css">

<script>

    new Vue({
        el: "#app",
        //当页面加载完成后，发送异步请求获取数据
        mounted(){
            this.selectAll();
            /*var _this = this;

            axios({
                method:"get",
                url:"http://localhost:8080/brand-case/selectAllServlet"
            }).then(function (resp) {
                _this.tableData = resp.data;
            })*/
        },
        methods: {

            //查询所有方法
            // selectAll(){
            //     var _this = this;
            //
            //     axios({
            //         method:"get",
            //         url:"http://localhost:8080/brand-case/brand/selectAll"
            //     }).then(function (resp) {
            //         _this.tableData = resp.data;
            //     })
            // },

            //查询分页数据
            selectAll(){
                var _this = this;

                // axios({
                //     method:"post",
                //     url:"http://localhost:8080/brand-case/brand/selectByPageAndCondition?currentPage=" + this.currentPage +"&pageSize=" + this.pageSize,
                //     data:this.brand
                // }).then(function (resp) {
                //     //设置表格数据
                //     _this.tableData = resp.data.rows;
                //     //设置总记录数
                //     _this.totalCount = resp.data.totalCount;
                // })

                axios({
                    method:"post",
                    url:"http://localhost:8080/brand-case/brand/selectByPageAndCondition?currentPage=" + this.currentPage +"&pageSize=" + this.pageSize,
                    data:this.brand
                }).then(resp =>{
                        //设置表格数据
                        this.tableData = resp.data.rows;
                        //设置总记录数
                        this.totalCount = resp.data.totalCount;
                })
            },

            //根据id查询(回显)
            selectById(index, row){

                //console.log(row.id)
                //console.log(index)

                this.updatePage = true;

                var _this = this;


                axios({
                    method:"get",
                    url:"http://localhost:8080/brand-case/brand/selectByIdBrand?id=" + row.id
                }).then(function (resp) {
                    _this.selectByIdData = resp.data;
                    //console.log(resp.data)
                })
            },

            //修改数据
            updateById(row){

                var _this = this;

                axios({
                    method:"post",
                    url:"http://localhost:8080/brand-case/brand/updateBrand",
                    data:_this.selectByIdData
                }).then(function (resp) {
                    if (resp.data == "success"){
                        //修改成功
                        //关闭窗口
                        _this.updatePage = false;

                        //新增后刷新页面
                        _this.selectAll();

                        _this.$message({
                            message: '恭喜你，修改成功',
                            type: 'success'
                        });
                    }
                })

            },

            tableRowClassName({row, rowIndex}) {
                if (rowIndex === 1) {
                    return 'warning-row';
                } else if (rowIndex === 3) {
                    return 'success-row';
                }
                return '';
            },
            // 复选框选中后执行的方法
            handleSelectionChange(val) {
                this.multipleSelection = val;

                console.log(this.multipleSelection)
            },
            // 查询方法
            onSubmit() {
                //console.log(this.brand);
                this.selectAll();
            },
            // 添加数据
            addBrand(){
                //console.log(this.brand);
                //发送ajax异步请求，添加异步数据
                var _this = this;

                axios({
                    method: "post",
                    url: "http://localhost:8080/brand-case/brand/addBrand",
                    data: _this.brand
                }).then(function (resp) {
                    if (resp.data == "success"){
                        //添加成功

                        //关闭窗口
                        _this.dialogVisible = false;

                        //新增后刷新页面
                        _this.selectAll();

                        _this.$message({
                            message: '恭喜你，添加成功',
                            type: 'success'
                        });
                    }
                })
            },
            handleClose(done) {
                this.$confirm('确认关闭？')
                    .then(_ => {
                        done();
                    })
                    .catch(_ => {});
            },

            //单个删除
            deleteById(index,row){

                this.brand.id = row.id;

                this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
                    confirmButtonText: '确定',
                    cancelButtonText: '取消',
                    type: 'warning'
                }).then(() => {
                    var _this = this;
                    axios({
                        method:"get",
                        url: "http://localhost:8080/brand-case/brand/deleteById?id=" + _this.brand.id
                    }).then(function (resp) {
                        if (resp.data == "success"){
                            //修改成功
                            //关闭窗口
                            _this.deleteByIdPage = false;

                            //新增后刷新页面
                            _this.selectAll();

                            _this.$message({
                                message: '恭喜你，删除成功',
                                type: 'success'
                            });
                        }
                    })
                }).catch(() => {
                    this.$message({
                        type: 'info',
                        message: '已取消删除'
                    });
                });
            },
            deleteBrand(row){


            },
            //批量删除
            BatchDeletion(){

                //批量删除警告框
                this.$confirm('此操作将批量删除该数据, 是否继续?', '提示', {
                    confirmButtonText: '确定',
                    cancelButtonText: '取消',
                    type: 'warning'
                }).then(() => {
                    //用户点击确认
                    //1.创建id数组[1,2,3]
                    for (let i = 0; i < this.multipleSelection.length; i++) {
                        let selectionElement = this.multipleSelection[i];
                        this.selectedInts[i] = selectionElement.id;
                    }

                    //发送ajax请求
                    //发送ajax异步请求，添加异步数据
                    var _this = this;

                    axios({
                        method: "post",
                        url: "http://localhost:8080/brand-case/brand/BatchDeletion",
                        data: _this.selectedInts
                    }).then(function (resp) {
                        if (resp.data == "success"){
                            //删除成功

                            //关闭窗口
                            //_this.dialogVisible = false;

                            //新增后刷新页面
                            _this.selectAll();

                            _this.$message({
                                message: '恭喜你，批量删除成功',
                                type: 'success'
                            });
                        }
                    })

                }).catch(() => {
                    //用户点击取消
                    this.$message({
                        type: 'info',
                        message: '已取消批量删除'
                    });
                });



            },

            //分页
            handleSizeChange(val) {
                //console.log(`每页 ${val} 条`);
                //设置每页显示条数
                this.pageSize = val;
                this.selectAll();
            },
            handleCurrentChange(val) {
                //console.log(`当前页: ${val}`);
                this.currentPage = val;
                this.selectAll();
            },

        },
        data() {
            return {
                //总记录数
                totalCount:100,
                // 当前页码
                currentPage: 1,
                // 每页显示条数
                pageSize:5,
                // 添加数据对话框是否展示的标记
                dialogVisible: false,
                // 修改数据对话框是否展示的标记
                updatePage:false,
                // 删除数据对话框是否展示的标记
                deleteByIdPage:false,
                // 品牌模型数据
                brand: {
                    status: '',
                    brandName: '',
                    companyName: '',
                    id:"",
                    ordered:"",
                    description:""
                },
                //复选框选中id集合
                selectedInts:[],
                // 复选框选中数据集合
                multipleSelection: [],
                // 表格数据
                tableData: [{
                    id:"",
                    brandName: '',
                    companyName: '',
                    ordered: '',
                    status: ""
                }],
                // 根据id查询表格数据
                selectByIdData: {
                    id:"",
                    brandName: '',
                    companyName: '',
                    ordered: '',
                    status: ""
                },
            }
        }
    })

</script>

</body>
</html>
```



![image-20230223211423975](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232114093.png)



![image-20230223211526937](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232115062.png)



![image-20230223211615381](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232116453.png)

```java
package com.itheima.mapper;

import com.itheima.pojo.Brand;
import org.apache.ibatis.annotations.*;

import javax.servlet.annotation.WebServlet;
import java.util.List;

public interface BrandMapper {

    /**
     * 查询所有
     * @return
     */
    @Select("select * from tb_brand")
    @ResultMap("brandResultMap")
    List<Brand> selectAll();


    /**
     * 新增
     * @param brand
     */
    @Insert("insert into tb_brand values (null,#{brandName}," +
            "#{companyName},#{ordered},#{description},#{status})")
    void addBrand(Brand brand);


    /**
     * 根据id查询
     * @param id
     * @return
     */
    @Select("select * from tb_brand where id = #{id}")
    @ResultMap("brandResultMap")
    Brand selectByIdBrand(int id);

    /**
     * 修改
     */
    @Update("update tb_brand set brand_name = #{brandName},company_name = #{companyName}," +
            "ordered = #{ordered},description = #{description},status = #{status}  where id = #{id};")
    void updateBrand(Brand brand);

    /**
     *
     * 单个删除
     * @param id
     */
    @Delete("delete from tb_brand where id = #{id}")
    void deleteById(int id);

    /**
     * 批量删除
     * @param ints
     */
    void BatchDeletion(@Param("ints") int[] ints);


    /**
     * 分页查询
     * @param begin
     * @param size
     * @return
     */
    @Select("select * from tb_brand limit #{begin},#{size}")
    @ResultMap("brandResultMap")
    List<Brand> selectByPage(@Param("begin") int begin,@Param("size") int size);


    /**
     * 总记录数
     * @return
     */
    @Select("select count(*) from tb_brand")
    int selectTotalCount();



    /**
     * 分页条件查询
     * @param begin
     * @param size
     * @return
     */
    List<Brand> selectByPageAndCondition(@Param("begin") int begin,@Param("size") int size,@Param("brand") Brand brand);


    /**
     * 根据条件查询总记录数
     * @return
     */
    int selectTotalCountByCondition(Brand brand);
}

```



![image-20230223211636828](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232116898.png)

```java
package com.itheima.pojo;

public class Brand {
    // id 主键
    private Integer id;
    // 品牌名称
    private String brandName;
    // 企业名称
    private String companyName;
    // 排序字段
    private Integer ordered;
    // 描述信息
    private String description;
    // 状态：0：禁用  1：启用
    private Integer status;


    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getBrandName() {
        return brandName;
    }

    public void setBrandName(String brandName) {
        this.brandName = brandName;
    }

    public String getCompanyName() {
        return companyName;
    }

    public void setCompanyName(String companyName) {
        this.companyName = companyName;
    }

    public Integer getOrdered() {
        return ordered;
    }

    public void setOrdered(Integer ordered) {
        this.ordered = ordered;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public Integer getStatus() {
        return status;
    }
    //逻辑视图
    public String getStatusStr(){
        if (status == null){
            return "未知";
        }
        return status == 0 ? "禁用":"启用";
    }

    public void setStatus(Integer status) {
        this.status = status;
    }

    @Override
    public String toString() {
        return "Brand{" +
                "id=" + id +
                ", brandName='" + brandName + '\'' +
                ", companyName='" + companyName + '\'' +
                ", ordered=" + ordered +
                ", description='" + description + '\'' +
                ", status=" + status +
                '}';
    }
}

```



![image-20230223211717904](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232117978.png)

```java
package com.itheima.service;

import com.itheima.pojo.Brand;
import com.itheima.pojo.PageBean;

import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public interface BrandService {

    /**
     * 查询所有
     * @return
     */
    List<Brand> selectAll();

    /**
     * 新增
     * @param brand
     */
    void addBrand(Brand brand);


    /**根据id查询
     * @param id
     * @return
     */
    Brand selectByIdBrand(int id);


    /**
     * 修改
     * @param brand
     */
    void updateBrand(Brand brand);


    /**
     * 单个删除
     * @param id
     */
    void deleteById(int id);

    /**
     * 批量删除
     * @param ints
     */
    void BatchDeletion(int[] ints);


    /**
     * 分页查询
     * @param currentPage
     * @param pageSize
     * @return
     */
    PageBean<Brand> selectByPage(int currentPage,int pageSize);

    /**
     * 分页条件查询
     * @param currentPage
     * @param pageSize
     * @param brand
     * @return
     */
    PageBean<Brand> selectByPageAndCondition(int currentPage,int pageSize,Brand brand);
}

```

```java
package com.itheima.service.impl;

import com.itheima.mapper.BrandMapper;
import com.itheima.pojo.Brand;
import com.itheima.pojo.PageBean;
import com.itheima.service.BrandService;
import com.itheima.util.SqlSessionFactoryUtils;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;

import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class BrandServiceImpl implements BrandService {

    //创建对应SqlSessionFactory工厂对象
    SqlSessionFactory sqlSessionFactory = SqlSessionFactoryUtils.getSqlSessionFactory();

    @Override
    public List<Brand> selectAll() {
        //获取SqlSession
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //获取BrandMapper
        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        //调用方法
        List<Brand> brands = mapper.selectAll();

        //释放资源
        sqlSession.close();

        return brands;
    }

    @Override
    public void addBrand(Brand brand) {
        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        mapper.addBrand(brand);

        sqlSession.commit();

        sqlSession.close();
    }

    @Override
    public Brand selectByIdBrand(int id) {

        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        Brand brand = mapper.selectByIdBrand(id);

        sqlSession.close();

        return brand;
    }

    @Override
    public void updateBrand(Brand brand) {

        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        mapper.updateBrand(brand);

        sqlSession.commit();

        sqlSession.close();
    }

    @Override
    public void deleteById(int id) {

        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        mapper.deleteById(id);

        sqlSession.commit();

        sqlSession.close();
    }

    @Override
    public void BatchDeletion(int[] ints) {

        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        mapper.BatchDeletion(ints);

        sqlSession.commit();

        sqlSession.close();
    }

    @Override
    public PageBean<Brand> selectByPage(int currentPage, int pageSize) {

        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        //计算开始索引
        int begin = (currentPage - 1) * pageSize;
        //计算查询条目数
        int size = pageSize;

        //查询当前页数据
        List<Brand> rows = mapper.selectByPage(begin, size);

        //查询总记录数
        int totalCount = mapper.selectTotalCount();

        //封装对象
        PageBean<Brand> pageBean = new PageBean<>();
        pageBean.setRows(rows);
        pageBean.setTotalCount(totalCount);

        sqlSession.close();

        return pageBean;
    }

    @Override
    public PageBean<Brand> selectByPageAndCondition(int currentPage, int pageSize, Brand brand) {

        SqlSession sqlSession = sqlSessionFactory.openSession();

        BrandMapper mapper = sqlSession.getMapper(BrandMapper.class);

        //计算开始索引
        int begin = (currentPage - 1) * pageSize;
        //计算查询条目数
        int size = pageSize;

        //处理brand条件，模糊表达式
        String brandName = brand.getBrandName();
        if (brandName != null && brandName.length() > 0){
            brand.setBrandName("%"+brandName+"%");
        }

        String companyName = brand.getCompanyName();
        if (companyName != null && companyName.length() > 0){
            brand.setCompanyName("%"+companyName+"%");
        }

        //查询当前页数据
        List<Brand> rows = mapper.selectByPageAndCondition(begin,size,brand);

        //查询总记录数
        int totalCount = mapper.selectTotalCountByCondition(brand);

        //封装对象
        PageBean<Brand> pageBean = new PageBean<>();
        pageBean.setRows(rows);
        pageBean.setTotalCount(totalCount);

        sqlSession.close();

        return pageBean;
    }


}

```



![image-20230223211826791](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232118871.png)

```
package com.itheima.util;

import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;

public class SqlSessionFactoryUtils {

    private static SqlSessionFactory sqlSessionFactory;

    static {
        //静态代码块会随着类的加载而自动执行，且只执行一次
        try {
            String resource = "mybatis-config.xml";
            InputStream inputStream = Resources.getResourceAsStream(resource);
            sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }


    public static SqlSessionFactory getSqlSessionFactory(){
        return sqlSessionFactory;
    }
}
```



![image-20230223211901904](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232119992.png)

```java
package com.itheima.web.servlet;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

/**
 * @author momo~
 * @version 1.0
 * 替换httpservlet，根据请求的最后一段路径来进行方法分发
 */
public class BaseServlet extends HttpServlet {

    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //1.获取请求路径
        String requestURI = req.getRequestURI();//brand-case/brand/selectAll
        //2.获取最后一段路径
        int index = requestURI.lastIndexOf("/");
        String methodName = requestURI.substring(index + 1);

        //2.执行方法
        //2.1获取BrandServlet/UserServlet字节码对象class
        //谁调用我（this所在的方法），我（this）代表谁
        //System.out.printLn(this)://BrandServlet

        Class<? extends BaseServlet> cls = this.getClass();

        //2.2 获取方法Method对象
        try {
            Method method = cls.getMethod(methodName, HttpServletRequest.class, HttpServletResponse.class);
            //2.3执行方法
            method.invoke(this,req,resp);
        } catch (NoSuchMethodException e) {
            throw new RuntimeException(e);
        } catch (InvocationTargetException e) {
            throw new RuntimeException(e);
        } catch (IllegalAccessException e) {
            throw new RuntimeException(e);
        }
    }
}

```



```java
package com.itheima.web.servlet;

import com.alibaba.fastjson.JSON;
import com.itheima.pojo.Brand;
import com.itheima.pojo.PageBean;
import com.itheima.service.BrandService;
import com.itheima.service.impl.BrandServiceImpl;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;
import java.util.Arrays;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet("/brand/*")
public class BrandServlet extends BaseServlet{

    private BrandService brandService = new BrandServiceImpl();

    /**
     * 查询所有
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void selectAll(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //调用service方法
        List<Brand> brands = brandService.selectAll();

        //将list集合转为json
        String jsonString = JSON.toJSONString(brands);

        //写数据
        response.setContentType("text/json;charset=utf-8");
        response.getWriter().write(jsonString);
    }

    /**
     * 新增
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void addBrand(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException{
        //接收前台数据
        BufferedReader br = request.getReader();
        String params = br.readLine();//json字符串

        //json数据转为Brand对象
        Brand brand = JSON.parseObject(params, Brand.class);

        //调用service
        brandService.addBrand(brand);

        //响应成功标识
        response.getWriter().write("success");
    }


    /**
     * 根据id查询
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void selectByIdBrand(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException{

        //接收前台id
        String id = request.getParameter("id");
        //System.out.println(id);

        //字符串转数字
        int i = Integer.parseInt(id);

        //调用service
        Brand brand = brandService.selectByIdBrand(i);
        //System.out.println(brand);

        //将brand对象转为json字符串发送给前台
        String jsonString = JSON.toJSONString(brand);
        //System.out.println(jsonString);

        response.setContentType("text/json;charset=utf-8");
        response.getWriter().write(jsonString);
    }




    /**
     * 修改
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void updateBrand(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException{
        //接收前台数据
        BufferedReader br = request.getReader();
        String params = br.readLine();//json字符串
        System.out.println(params);

        //json数据转为Brand对象
        Brand brand = JSON.parseObject(params, Brand.class);

        //调用service
        brandService.updateBrand(brand);

        //响应成功标识
        response.getWriter().write("success");
    }


    /**
     * 单个删除
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void deleteById(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException{
        //接收前台id
        String id = request.getParameter("id");
        //System.out.println(id);

        //字符串转数字
        int i = Integer.parseInt(id);

        //调用service
        brandService.deleteById(i);

        //响应成功标识
        response.getWriter().write("success");
    }


    public void BatchDeletion(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException{
        //接收数据
        BufferedReader br = request.getReader();
        String params = br.readLine();

        //转为int[]
        int[] ints = JSON.parseObject(params, int[].class);

        //调用service
        brandService.BatchDeletion(ints);

        //响应成功标识
        response.getWriter().write("success");
    }


    /**
     * 分页查询
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void selectByPage(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        //接收数据 当前页码和每页显示条目数 url?currentPage&pageSize
        String _currentPage = request.getParameter("currentPage");
        String _pageSize = request.getParameter("pageSize");

        int currentPage = Integer.parseInt(_currentPage);
        int pageSize = Integer.parseInt(_pageSize);

        //调用service
        PageBean<Brand> pageBean = brandService.selectByPage(currentPage, pageSize);

        //将list集合转为json
        String jsonString = JSON.toJSONString(pageBean);

        //写数据
        response.setContentType("text/json;charset=utf-8");
        response.getWriter().write(jsonString);
    }


    /**
     * 分页条件查询
     * @param request
     * @param response
     * @throws ServletException
     * @throws IOException
     */
    public void selectByPageAndCondition(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        //接收数据 当前页码和每页显示条目数 url?currentPage&pageSize
        String _currentPage = request.getParameter("currentPage");
        String _pageSize = request.getParameter("pageSize");

        int currentPage = Integer.parseInt(_currentPage);
        int pageSize = Integer.parseInt(_pageSize);

        //获取查询条件对象
        //接收数据
        BufferedReader br = request.getReader();
        String params = br.readLine();


        Brand brand = JSON.parseObject(params, Brand.class);

        //调用service
        PageBean<Brand> pageBean = brandService.selectByPageAndCondition(currentPage, pageSize, brand);
        //将list集合转为json
        String jsonString = JSON.toJSONString(pageBean);

        //写数据
        response.setContentType("text/json;charset=utf-8");
        response.getWriter().write(jsonString);
    }

}

```



```java
package com.itheima.web.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
@WebServlet("/user/*")
public class UserServlet extends BaseServlet{

    public void selectAll(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("user selectAllUser...");
    }

    public void addUser(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException{
        System.out.println("user addUser...");
    }
}

```



![image-20230223212043036](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232120134.png)

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.itheima.mapper.BrandMapper">

    <resultMap id="brandResultMap" type="brand">
        <result property="brandName" column="brand_name" />
        <result property="companyName" column="company_name" />
    </resultMap>


    <delete id="BatchDeletion">
        delete from tb_brand where id in (
            <foreach collection="ints" item="id" separator=",">
                #{id}
            </foreach>
            );
    </delete>


    <select id="selectByPageAndCondition" resultMap="brandResultMap">
        select * from tb_brand
        <where>
            <if test="brand.brandName != null and brand.brandName != ''">
                and brand_name like #{brand.brandName}
            </if>
            <if test="brand.companyName != null and brand.companyName != ''">
                and company_name like #{brand.companyName}
            </if>
            <if test="brand.status != null">
                and status = #{brand.status}
            </if>
        </where>
        limit #{begin},#{size}
    </select>


    <select id="selectTotalCountByCondition" resultType="java.lang.Integer">
        select count(*) from tb_brand
        <where>
            <if test="brandName != null and brandName != ''">
                and brand_name like #{brandName}
            </if>
            <if test="companyName != null and companyName != ''">
                and company_name like #{companyName}
            </if>
            <if test="status != null">
                and status = #{status}
            </if>
        </where>
    </select>
</mapper>
```



```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>

    <typeAliases>
        <package name="com.itheima.pojo"/>
    </typeAliases>

    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///db2?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="root"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
       <!--扫描mapper-->
        <package name="com.itheima.mapper"/>
    </mappers>
</configuration>
```



![image-20230223212214958](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302232122032.png)

```java
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>brand-case</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>war</packaging>

    <properties>
        <maven.compiler.source>8</maven.compiler.source>
        <maven.compiler.target>8</maven.compiler.target>
    </properties>


    <dependencies>
        <!--Servlet-->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.1.0</version>
            <scope>provided</scope>
        </dependency>


        <!--MyBatis-->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
            <version>3.5.5</version>
        </dependency>
        <!--MySQL-->

        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.32</version>
        </dependency>


        <!--fastjson-->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>fastjson</artifactId>
            <version>1.2.62</version>
        </dependency>


    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat7-maven-plugin</artifactId>
                <version>2.2</version>
            </plugin>
        </plugins>
    </build>
</project>
```

