# MySQL常用语句

标签（空格分隔）： MySQL 常用语句 语法 随便写的标签

---

## 建表
```msyql
DROP TABLE IF EXISTS `wf_base_info`;
CREATE TABLE wf_base_info(
`i_id` INT NOT NULL AUTO_INCREMENT COMMENT '自增id',
`article_title` VARCHAR(255) NOT NULL COMMENT '文章标题',
`abstract` VARCHAR(255) DEFAULT NULL COMMENT '摘要',
`author` VARCHAR(255) DEFAULT NULL COMMENT '作者',
`author_company` VARCHAR(255) DEFAULT NULL COMMENT '作者单位',
`journal_name` VARCHAR(255) DEFAULT NULL COMMENT '刊名',
`journal` VARCHAR(255) DEFAULT NULL COMMENT 'Journal杂志',
`year_volume_period` VARCHAR(255) DEFAULT NULL COMMENT '年，卷(期)',
`classify_code` VARCHAR(255) DEFAULT NULL COMMENT '分类号',
`publish_time` datetime DEFAULT NULL COMMENT '在线出版时间',
PRIMARY KEY(`i_id`)
)ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

## insert 语句
```mysql
INSERT INTO `data_grap_ready` VALUES ('1', null, '内蒙古人民出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('2', null, '兵器工业出版社有限责任公司', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('3', null, '化学工业出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('4', null, '经济科学出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('5', null, '哈尔滨工业大学出版社有限公司', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('6', null, '国防大学出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('7', null, '兰州大学出版社有限责任公司', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('8', null, '南海出版公司', '0', '1');
INSERT INTO `data_grap_ready` VALUES ('9', null, '中国青年出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('10', null, '人民交通出版社股份有限公司', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('11', null, '学习出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('12', null, '气象出版社', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('13', null, '广东羊城晚报出版社有限公司', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('14', null, '二十一世纪出版社有限公司', '0', '0');
INSERT INTO `data_grap_ready` VALUES ('15', null, '中国宇航出版有限责任公司', '0', '0');
```

## msyql 把一个表的数据复制到另一个表
### 1、表结构相同，且在同一个数据库中（如：表 table1 table2）
```mysql
insert into table1 select * from table2 (完全复制)

insert into table1 select distinct * from table2(不复制重复纪录）

insert into table1 select top 5 * from table2 (前五条纪录)
```
### 2、不在同一个数据库中（如：db1.table1 db2.table2）
```mysql
insert into db1..table1 select * from db2..table2 (完全复制)

insert into db1.table1 select distinct * from db2.table2(不复制重复纪录）

insert into tdb1.able1 select top 5 * from db2.table2 (前五条纪录)
```
### 3、只复制指定的字段
```mysql
insert into 目标表(字段1，字段2，...) select 字段1，字段2，... from 来源表
```
