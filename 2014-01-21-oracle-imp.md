Date: 2014-01-21 21:23
Title: Oracle的dmp文件解析
Tags: oracle
Slug: read-oracle-dmp-files
Category: Dev

工作中用到的最多的数据库就是`Oracle`了.其中的数据库导出的格式是`dmp`.如果想解析其中的内容的话,一个办法就是用`imp`命令导入到数据库中,然后查看了.不过有时候并不是想看到数据,只是想看到表结构,导出时候的`Schema`的话,就不用这么麻烦了.直接用读取文件.表结构,导出时候的一些基本信息都是明文的,数据内容是`Oracle`加密的,这个是无能为力的.

之前就用这个方法搞定一个导入时候`exp`命令`fromuser`的问题.