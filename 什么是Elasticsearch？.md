什么是Elasticsearch？

答：想查数据就免不了搜素，搜索就离不开搜索引擎，百度、谷歌都是一个非常庞大复杂的搜索引擎，他们几乎索引了互联网上开发的所有网页和数据。然而对于我们自己的业务数据来说，肯定就没有必要用这么复杂的技术了，如果我们想实现自己的搜索引擎，方便存储和检索，Elasticsearch就是不二选择，他是一个全文搜索引擎，可以快速的存储、搜索和分析海量数据。

为什么要用Elasticsearch？

Elasticsearch 是一个开源的搜索引擎，建立在一个全文搜索引擎库Apache Lucene基础之上。

那么Lucene又是什么？Lucene可能是目前存在的，不论开源还是私有的，拥有最先进，高性能和全功能搜索引擎功能的库，但也只是一个库。要用上Lucence，我们需要编写java并引用Luncene包才可以，而且我们需要对信息检索有一定程度的理解才能明白Lucene是怎么工作的，反正用起来没那么简单。

那么为了解决这个问题，Elasticsearch就诞生了，Elasticsearch也是使用Java编写的，它的内部使用Lucene做索引与搜索，但是它的目标是全文检索变的简单，相当于Luncene的一层封装，它提供了一套简单一致的RESTful API来帮助我们实现存储和检索。

所以Elasticsearch仅仅就是一个简易版的Lucene封装么？那就大错特错了，Elasticsearch不仅仅是Lucene,并且也不仅仅只是一个全文搜索引擎。它可以被下面这样准确的形容：

`一个分布式的实时文档存储，每个字段可以被索引与搜索`

`一个分布式实时分析搜索引擎`

`能胜任上百个服务节点的扩展，并支持PB级的结构化或者非结构化数据`

总之，是一个相当牛逼的搜索引擎，维基百科，Stack Overflow、GitHub都纷纷采用他来做索引。



 Elasticsearch的安装

我们可以到 Elasticsearch 的官方网站下载 Elasticsearch：<https://www.elastic.co/downloads/elasticsearch>，同时官网也附有安装说明。

首先把安装包下载下来并解压，然后运行 bin/elasticsearch（Mac 或 Linux）或者 bin\elasticsearch.bat (Windows) 即可启动 Elasticsearch 了。

Elasticsearch 默认会在 9200 端口上运行，我们打开浏览器访问 <http://localhost:9200/> 就可以看到类似内容：  



{
  "name" : "atntrTf",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "e64hkjGtTp6_G2h1Xxdv5g",
  "version" : {
    "number": "6.2.4",
    "build_hash": "ccec39f",
    "build_date": "2018-04-12T20:37:28.497551Z",
    "build_snapshot": false,
    "lucene_version": "7.2.1",
    "minimum_wire_compatibility_version": "5.6.0",
    "minimum_index_compatibility_version": "5.0.0"
  },
  "tagline" : "You Know, for Search"
}



如果看到这个内容，就说明 Elasticsearch 安装并启动成功了，这里显示我的 Elasticsearch 版本是 6.2.4 版本，版本很重要，以后安装一些插件都要做到版本对应才可以。