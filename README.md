项目介绍
========
### 什么是接口文档管理工具?
一个用PHP编写的在线API文档管理系统；其致力于快速解决团队内部接口文档的编写、维护、存档，以及减少团队协作开发的沟通成本。
### 特点
* 轻量级
* 架构简单轻巧利于二次开发
* 部署维护方便

项目部署
========
* 在MySQL中新建api数据库，并执行 db.sql文件。如果你是在命令行操作则可以像下面这样：
```sql
source /db.sql;
```
* 在./MinPHP/core/config.php配置文件中修改数据库连接信息
```php
//数据库连接配置
'db'=>array(
  'host' => 'localhost',   //数据库地址
    'dbname' => 'api',   //数据库名
    'user' => 'root',    //帐号
    'passwd' => 'root',    //密码
    'linktype' => 'pdo',    //数据库连接类型 支持mysqli与pdo两种类型
),
```
* 把项目部署到Apache或Nginx中即可

使用说明
========
1. 当前版本(v1.1)版本只做了简单权限控制，一是有权限；二是无权限。
2. **游客** 只能查看接口分类和接口信息 __无增删改查权限__
3. 默认的管理员有两个分别为admin(密码:654321)与root(密码:123456)。
4. 如果想要修改密码可先登录进去再通过页面修改；当然你也可以直接修改数据库```user```表的字段来实现，其中密码的计算可以按照下面的方式获取到。
```sql
SELECT MD5('your passwd.');
```

提示
====
这套项目最初是由其他开发者编写，至今仍未联系上该开发者，暂时不开放该开发者的信息。