# 使用wxPython+Mysql实现了一个专利管理系统
+ 这也是[武汉纺织大学](https://www.wtu.edu.cn/)软件11806班的python结课作业.

+ 本系统的参考博客：[http://www.fangshiyu.top/article/article-list/](http://www.fangshiyu.top/article/article-list/)
### 运行环境
操作系统：只适用于windows 10，Mac OS版在调试。后期推出！

数据库：SQL sever 2014，注意连接MySql数据库需要对源代码进行调试!
## 运行该系统有两种方式：
### 第一种方式：直接运行程序
#### Usage
第一步:

    pip install  requirements.txt

第二步:

     创建数据库patent，数据库需要两张表，一个是user_info，另一个是patent_info.
     数据库代码：
```sql
CREATE TABLE patent_info
       (Patentid VARCHAR(5) NOT NULL,
        PatentName VARCHAR(40) NOT NULL,
        PatentFunctional VARCHAR(40),
	BaseClass VARCHAR(40) NOT NULL,
	RegionalCategory VARCHAR(40) NOT NULL,
	FunctionCategory VARCHAR(40) NOT NULL,
	ApplicantName VARCHAR(40),
	ApplicantID CHAR(18) NOT NULL,
	ModifyTime VARCHAR(40),
	SubmitTime VARCHAR(40),
	AuditTime VARCHAR(40),
	patentstate VARCHAR(40) NOT NULL,
	); 

CREATE TABLE user_info
       (UserCategory VARCHAR(6) NOT NULL, 
	Password VARCHAR(20) NOT NULL,
	TrueName VARCHAR(40) NOT NULL,
	IDCard CHAR(18) NOT NULL,
	Gender VARCHAR(5),
        Birthday VARCHAR(20),
	Phone VARCHAR(15),
	QQ VARCHAR(15),
	Email VARCHAR(20),
	UserStatus VARCHAR(8) NOT NULL,
	); 

INSERT INTO patent_info VALUES ('1', '发明软件数据整合方法', '无', '实用性', '中国内地', '发明专利', '李春', '420683199907244218', '2018-06-30', '2018-06-30', '2018-06-30', '审核通过');
INSERT INTO patent_info VALUES ('2', '发明软件聚合方法', '无', '实用性', '中国内地', '发明专利', '李沙', '420683199907244213', '2018-06-30', '2018-06-30', '2018-06-30', '审核通过');
INSERT INTO patent_info VALUES ('3', '种Exce1软件数据整合方法', '无', '实用性', '中国内地', '发明专利', '李沙', '420683199907244213', '2018-06-30', '2018-06-30', '2018-06-30', '审核未通过');
INSERT INTO patent_info VALUES ('4', '种Exce1聚合方法', '无', '实用性', '中国内地', '发明专利', '李沙', '420683199907244213', '2018-06-30', '2018-06-30', '2018-06-30', '待审核');
INSERT INTO patent_info VALUES ('5', '一种贼牛逼的专利', '无', '实用性', '中国内地', '发明专利', '李涵', '420683199907244211', '2018-06-30', '2018-06-30', '2018-06-30', '审核未通过');
INSERT INTO patent_info VALUES ('6', '牛逼的专利', '无', '实用性', '中国内地', '发明专利', '李涵', '420683199907244211', '2018-06-30', '2018-06-30', '2018-06-30', '审核通过');
INSERT INTO patent_info VALUES ('7', '好牛逼的专利', '无', '实用性', '中国内地', '发明专利', '李涵', '420683199907244211', '2018-06-30', '2018-06-30', '2018-06-30', '待审核');


INSERT INTO user_info VALUES('用户','123456','李沙','420683199907244213','男','2020-07-24','15271020426','2858756816','1020323847@qq.com','待审核')
INSERT INTO user_info VALUES('用户','123456','李涵','420683199907244211','男','2020-07-24','15271020426','2858756816','1020323847@qq.com','审核通过')
INSERT INTO user_info VALUES('管理员','123456','李春','420683199907244218','男','2020-04-24','15271020426','2858756816','1020323847@qq.com','审核通过')

select * from patent_info
select * from user_info
```

第三步：

    运行main_page.py

### 第二种方式：执行exe可执行文件
多个py文件打包exe可执行文件详情请见博客[http://www.fangshiyu.top/article/article-detail/36/](http://www.fangshiyu.top/article/article-detail/36/)内容

第一步：

	找到main_page.zip文件直接解压缩

第二步：

	在解压缩的文件夹里找到main_page.exe双击即可执行

第三步：

	进入交互界面在设置里配置参数，连接数据库。数据库代码上附，这里不在赘述。
