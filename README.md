# 中国省市地区信息
数据来源于国家统计局，网址：http://www.stats.gov.cn/ ，总共846462条数据，记录了全中国的省、市、县、镇、村委会的所有地区数据。



###表结构

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

