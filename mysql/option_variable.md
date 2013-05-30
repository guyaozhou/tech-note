## 简介

MySQL 究竟有多少个选项？有多少个变量？很难说得清，反正很多，而且还在不断增加中。给个大概的概念：

* [MySQL 选项表](http://dev.mysql.com/doc/refman/5.7/en/mysqld-option-tables.html)
* 输入命令: `SHOW VARIABLES;`
* 输入命令: `SHOW STATUS;` 

### 几个有用的选项

#### `innodb_file_per_table`

每个 innodb 都保存到不同的文件中，在版本5.6.6后已经是缺省设置了，不过在这之前，还需要自己设置。

修改配置文件：

    [mysqld]
    innodb_file_per_table

修改表现有表的设置：

    SET GLOBAL innodb_file_per_table=1;     -- 设置成 1/0
    ALTER TABLE table_name ENGINE=InnoDB;

参考：

* [Enabling and Disabling File-Per-Table Mode](http://dev.mysql.com/doc/refman/5.7/en/tablespace-enabling.html)

