## HBase实验

#### 一、实验目的

​	会使用HBase Shell 连接分布式数据库HBase进行建表及增删改查操作

#### 二、实验要求

1. Linux、MacOSX或其他类似Unix的操作系统

2. HBase

#### 三、预备知识

​	HBase (Hadoop Database)是一个高可靠性、高性能、面向列、可伸缩、 实时读写的分布式数据库。HBase不同于一般的关系数据库，它是一个适合于非结构化数据存储的数据库。另一个不同的是HBase基于列的而不是基于行的模式。HBase利用Hadoop HDFS作为其文件存储系统,利用Hadoop MapReduce来处理 HBase中的海量数据,利用Zookeeper作为其分布式协同服务。

HBase有三种安装模式：本地模式、伪分布模式和全分布模式。本地模式是HBase的默认模式，该模式是直接在本地文件系统中存放数据而不是基于HDFS，也不需要使用Zookeeper。注意，在本地文件系统上运行HBase一般不能确保数据的持久性，要想确保数据都被保存下来，需要在HDFS上运行HBase。但是在本地文件系统上运行HBase可以快速开始学习和熟悉HBase系统的运作，因而该模式通常用于HBase程序的测试。HBase的伪分布模式是在一台机器上模拟HBase的全分布环境，需要使用HDFS来保存数据，同时还需要运行Zookeeper。HBase的全分布模式通常应用于生产环境中，需要使用多台机器。本实验在本地模式下进行。

> 

#### 四、实验内容

  1. 分别启动ZooKeeper、Hadoop集群和HBase集群
     在所有节点都运行`zkServer.sh start`以启动ZooKeeper
     在master节点运行`start-all.sh`以启动Hadoop集群
     在master节点运行`start-hbase.sh`以启动HBase集群

  2. 使用Hbase Shell连接HBase。

  3. 创建表student,且有2个列族，分别为`stuinfo`,`course`,显示表结构。

  4.  修改表结构，`course`列族返回最大版本数为3，显示表结构。 

  5. 向表中添加数据，要求包括以下列，并至少包含两个样例：

     >stuinfo列族：name、age、sex、dept

     > course列族：english、math、physics

  6. 添加完数据后，用`scan`命令查询`student`表中的所有信息。  

  7.  更新数据，将`course`列族中的`math`列值都加5 

  8. 使用get查询`course`列族的信息。

  9. 删除student表。