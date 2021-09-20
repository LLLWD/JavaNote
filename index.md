## 数据库

###### 碎碎念，暂时不知道些什么，先留着<br>B站观看的此视频 [MySQL基础+高级](https://www.bilibili.com/video/BV12b411K7Zu?from=search&seid=7632868581936074314&spm_id_from=333.337.0.0)，博客中的数据库都来自于上视频评论区的资料，请大家自行下载。<br>书籍：《数据库系统概论》（高等教育出版社）《MySQL必知必会》（人民邮电出版社）

### 数据库
数据：描述事物的符号记录<br>
数据库(DataBase)：是长期存储在计算机内、有组织的、可共享的大量数据的集合。数据库中的数据按一定的数据模型组织、描述和存储，具有较小的冗余度、较高的数据独立性和易扩展性，并可为各种用户共享<br>
数据库管理系统(DataBase Management System DBMS)：MySQL<br>
数据库系统(DataBase System):是由DB DBMS DBA(数据库管理人员) 应用程序 组成的存储、管理、处理和维护数据的系统<br>

### SQL（结构化查询语言 Structured Query Language）
SQL是关系数据库的标准语言<br>
![这是图片](/assets/img/philly-magic-garden.jpg "Magic Gardens")
#### 关键字
关键字要大写，数据库名，表名，字段名要小写
#### 字符关键字
拼接```CONCAT```<br>
小写```UPPER```大写```LOWER```<br>
取别名```AS```<br>
```
SELECT CONCAT(UPPER(last_name),LOWER(first_name)) AS 姓大写名小写
FROM employees;
```
截取字符串```SUBSTRING```(也可以简写为SUBSTR)<br>
```INSTR```
```
# SUBSTRING(字段名,n,m) 截取[n,m]处字符
# 获取每位员工的姓的首字母
SELECT SUBSTRING(first_name,1,1)
FROM employees;

# SUBSTRING(字段名,n) 截取字段n之后的所有字符，包括n
# 获取每位员工的姓,并删除首字母
SELECT SUBSTRING(first_name,2)
FROM employees;
```
去字段前后空格TRIM<br>
左填充,右填充LPAD,RPAD<br>
转义ESCAPE<br>

#### 数学关键字
四舍五入```ROUND```<br>
向上取整```CEIL```<br>
向下取整```FLOOR```<br>
截断```TRUNCATE```<br>
取余```MOD``` (和Java的%作用相同;被除数为正,结果为正;被除数为负,结果为负. 实际上 %=a-(a/b * b) a,b都为int (a/b会向下取整得到整数) <br>

#### 日期函数
```NOW()``` 当前系统的日期和时间<br>
```CURDATE()``` 当前日期<br>
```CURTIME()``` 当前时间<br>
```YEAR() MONTH() DAY() HOUR() MINUTE() SECOND() MONTHNAME()``` <br>
```STR_TO_DATE()``` 将日期格式转换成指定格式的时间<br>
```DATE_FORMAT()``` 日期转换成字符<br>

#### 其他函数
```VERSION()``` 当前DBMS版本<br>
```DATABASE()``` 当前所在数据库<br>
```USER()``` 当前用户<br>
