# 数据库设计 [返回](./README.md)
    
<div id="USERS"></div>

- ## USERS表（用户表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |USER_ID|NUMBER(8,0)|主键|否| | | 用户ID|
    |NAME|VARCHAR2(50 BYTE)| |否| | | 用户真实姓名|
    |GIT_USERNAME|VARCHAR2(50 BYTE)| |是|空| | GitHUB用户名|
    |STATUS|VARCHAR2(50 BYTE)| |否|空| | 用户类型|
    |UPDATE_DATE|DATE| |是|空| | GitHUB用户名修改日期|
    |PASSWORD|VARCHAR2(512 BYTE)| |是|空| | 加密存储密码，为空表示密码就是学号|
    |DISABLE|VARCHAR2(20 BYTE)| |否| | |是否禁用,值为是表示禁用,其他表示正常.|
<div id="TEACHERS"></div>

- ## TEACHERS表（老师表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEACHER_ID|VARCHAR2(50 BYTE)|主键|否| | | 老师的工号|
    |TEACHER_NAME|VARCHAR2(50 BYTE)|外键|否| | | 老师的姓名|
    |TEACHER_DEPARTMENT|VARCHAR2(100 BYTE)| |否| | | 老师所属部门|
    |TEACHER_SUBJECT|VARCHAR2(40 BYTE)| |否| | | 老师所授课程|
    |TEACHER_TERM|VARCHAR2(40 BYTE)| |否| | | 老师所选学期|

<div id="STUDENTS"></div>

- ## STUDENTS表（学生表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)|主键,外键|否| | | 学生的学号|
    |STUDENT_NAME|VARCHAR2(50 BYTE)| |是| |空| 学生的姓名|
    |STUDENT_CLASS|VARCHAR2(20 BYTE)| |否| | | 学生属于的班级|
    |STUDENT_SUM|VARCHAR2(400 BYTE)|外键|是|空| | 成绩汇总|
    |STUDENT_SUBJECT|VARCHAR2(20 BYTE)| |否| | | 学生所选课程|
    |STUDENT_TERM|VARCHAR2(20 BYTE)| |否| | | 学生所选学期|
<div id="SUBJECTS"></div>

- ## SUBJECTS表（学科表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |SUBJECT_ID|NUMBER(6,0)|主键，外键|否| | | 学科编号|
    |SUBJECT_NAME|VARCHAR2(100 BYTE)| |否| | | 学科名称|
    |STUDENTM_ID|VARCHAR2(50 BYTE)|联合主键1，外键|否| | | 学生的学号，STUDENTS表外键|
 
<div id="GRADES"></div>

- ## GRADES表（学生实验成绩表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |GRADE_ID|NUMBER(6,0)|主键|否| | |实验编号|
    |SUM_SCORE|NUMBER| |是|空| 取值0-100|总的分数|
    |COMMENT|VARCHAR2(400 BYTE)| |是|空| | 老师对实验的评语|
    |GRADE_PRESENT|FLOAT| |是|空| |每个实验占总成绩的百分比|
    |DATE|DATE| |是|空| |老师批改实验的日期，为空表示未批改|
    |

<div id="TESTS"></div>

- ## TESTS表（实验项目表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEST_ID|NUMBER(6,0)|主键|否| | | 成绩编号|
    |GRADE_ID|NUMBER(6,0)|主键|否| | | 实验编号，TESTS表的外键|
    |TEST_NAME|VARCHAR2(100 BYTE)| |否| | | 实验名称|
    <div id="TESTS"></div>

- ## COURSE表（选课表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |COURSE_ID|NUMBER(6,0)|主键|否| | | 课程编号|
    |COURSE_TIME|DATE| |否| | |课程时长|
    |COURSE_NAME|VARCHAR2(100 BYTE)| |否| | |课程名称|
    |USER_ID|NUMBER(8,0)|外键|否| | | 用户ID|
    <div id="COURSE"></div>
<
