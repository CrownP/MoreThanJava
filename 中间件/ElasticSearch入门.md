概述：

Elasticsearch 是一个开源的搜索引擎，建立在一个全文搜索引擎库 Apache Lucene 基础之上。 Lucene 可以说是当下最先进、高性能、全功能的搜索引擎库—无论是开源还是私有，但仅仅只是一个库，需要使用 Java 将 Lucene 集成到应用程序中，且实现非常复杂，因此迎来了ES。

ES 使用 Java 编写，内部使用 Lucene 做索引与搜索，通过隐藏 Lucene 的复杂性，使全文检索变得简单，取而代之的是提供一套 RestfulAPI。

Elasticsearch 不仅仅只是一个全文搜索引擎，可以被下面这样准确的形容：

- 一个分布式的实时文档存储，*每个字段* 可以被索引与搜索
- 一个分布式实时分析搜索引擎
- 能胜任上百个服务节点的扩展，并支持 PB 级别的结构化或者非结构化数据

安装：
1.安装es：需要jdk环境，然后官网下载es，解压，`./bin/elasticsearch 启动, -d 参数后台启动（不能使用root用户，需要创建一个用户）。通过访问 curl 'http://localhost:9200/?pretty'  测试es是否成功启动。

2.安装Kibana，下载地址 https://www.elastic.co/cn/downloads/kibana

```
wget https://artifacts.elastic.co/downloads/kibana/kibana-6.0.0-linux-x86_64.tar.gz
sha1sum kibana-6.0.0-linux-x86_64.tar.gz 
tar -xzf kibana-6.0.0-linux-x86_64.tar.gz
cd kibana/
```

启动。

报内存问题，修改配置文件 jvm.options

-Xms128m
-Xmx128m
#8-13:-XX:+UseConcMarkSweepGC

