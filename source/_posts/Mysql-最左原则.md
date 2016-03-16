---
title: Mysql 索引最左原则
date: 2016-03-15 11:08:37
tags: mysql
categories: mysql
---

### 能用到索引或者索引部分

 * 联合索引全字段匹配；如: where a=1 and b=2
 * 联合索引左边字段匹配；如: where a=1（索引是a，b）
 * 联合索引左边字段范围查询, 范围查询截断了索引的使用，
 	* 如: where a < 100 and b=1（索引是a，b），只用到索引的a部分，b部分不起作用；
	* 如: where a = 100 and b>1（索引是a，b），用到了整个索引
 * 索引的模糊查询，可以用到索引的部分；如 where a like 'abc%'
 * IN 一般情况下是算作精确查询里。
 * 联合索引的使用场景还有 where + order by。
  
