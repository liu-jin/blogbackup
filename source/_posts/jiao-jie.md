title: 交接文档
date: 2015-06-09 10:24:15
tags:
---
# ODPS应用管理文档
## 1. 应用
* abif：商家数据
* tbpec：效果中心
* tpda：商品指南针

## 2. 后台权限
在在云端里添加成员后只在该应用的dev环境里添加了该成员，生产pro还没有读表的权限，需要在后台通过命令方式添加角色。
### 2.1 abif权限管理角色划分
角色是通过policy方式创建的，abif拥有角色如下：

* owner：只有一个，现在是依韵
* admin：依韵、腾景、南迦
* prd_default：默认生产角色，有限list，desc权限，不能select
* team：团队成员添加该角色，可以读写表
* read：外部成员添加，只能读表

### 2.2 package资源共享
有些外部pro的表是通过package的方式供abif访问的，需要拥有admin角色的人员在后台命令安装package，并授权给相关角色，才能访问package封装的资源（表、函数等）


*关于权限的详细文档[参考链接](http://odps.alibaba-inc.com/doc/prddoc/odps_security/index.html)*

<!--more-->

## 3. 空间清理
由于业务的增长，odps项目存储空间的使用有时会超过监控预警值，出现报警的情况，解决办法参考：http://odps.alibaba-inc.com/?p=626

## 4. 常用链接

云账号查询：

* http://d2.alibaba-inc.com/aliyunquery.html

应用账单、健康分：

* http://meta.alibaba-inc.com/manage/project/paybillnew/project_day.html?projName=abif&ds=2015-06-01

* http://meta.alibaba-inc.com/manage/project/paybill/project_day.html?projName=abif&ds=2015-06-01

qouta组资源占用情况：

* http://meta.alibaba-inc.com/project/health/quota.html
