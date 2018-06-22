# 中国省市地区信息
数据来源于国家统计局，网址：http://www.stats.gov.cn/ ，总共846462条数据，记录了全中国的省、市、县、镇、村委会的所有地区数据。

由于表数据量比较大，采用zip压缩的方式commit，zip包下载即可用



### 表结构

| 字段     | 备注                       |
| ------ | ------------------------ |
| id     | 主键                       |
| p_code | 地区的上一级编码                 |
| code   | 城市编码                     |
| name   | 城市名称                     |
| level  | 级别:1-省，2-市，3-县，4-镇，5-村委会 |



### sql语句

```mysql
CREATE TABLE `china_regions` (
  `id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  `p_code` varchar(50) NOT NULL DEFAULT '' COMMENT '上一级编码',
  `code` varchar(50) NOT NULL DEFAULT '' COMMENT '编码',
  `name` varchar(100) NOT NULL DEFAULT '' COMMENT '名称',
  `level` tinyint(4) NOT NULL COMMENT '级别:1-省，2-市，3-县，4-镇，5-村委会',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```



### 片段

```
id	p_code	code	name	level
1	0	11	北京市	1
2	0	12	天津市	1
3	0	13	河北省	1
4	0	14	山西省	1
5	0	15	内蒙古自治区	1
6	0	21	辽宁省	1
7	0	22	吉林省	1
8	0	23	黑龙江省	1
9	0	31	上海市	1
...
292	52	520100000000	贵阳市	2
293	52	520200000000	六盘水市	2
294	52	520300000000	遵义市	2
295	52	520400000000	安顺市	2
296	52	520500000000	毕节市	2
...
```

