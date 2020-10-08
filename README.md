### 项目介绍

周报系统是基于Spring+SpringMVC+MyBatis三大框架实现，实现了管理员模块和学生模块的操作，主要功能可以上传周报、修改周报等，还能够提供一些建议操作。还能够将数据导出成excel格式。

环境：IDEA	MySQL	Tomcat 8.5

### 数据库表的创建

* **user表**

```mysql
CREATE TABLE `user` (
  `id` int(11) NOT NULL,
  `username` varchar(20) DEFAULT NULL,
  `password` varchar(20) DEFAULT NULL,
  `sex` varchar(4) DEFAULT NULL,
  `major` varchar(20) DEFAULT NULL,
  `team` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

```

* **weekinfo表**

```mysql
CREATE TABLE `weekinfo` (
  `id` int(11) NOT NULL DEFAULT '0',
  `week` int(11) NOT NULL DEFAULT '0',
  `time` varchar(30) DEFAULT NULL,
  `content` varchar(4000) DEFAULT NULL,
  `tcontent` varchar(4000) DEFAULT NULL,
  `limits` varchar(40) DEFAULT NULL,
  PRIMARY KEY (`id`,`week`),
  CONSTRAINT `id_fk` FOREIGN KEY (`id`) REFERENCES `user` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

```

* **message表**

```mysql
CREATE TABLE `message` (
  `id` int(4) NOT NULL AUTO_INCREMENT,
  `week` int(2) NOT NULL,
  `content` varchar(1000) DEFAULT NULL,
  `reply` varchar(1000) DEFAULT NULL,
  `time` varchar(50) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=118 DEFAULT CHARSET=utf8;
```

