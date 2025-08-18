## 安装
下载压缩包解压缩，并执行bin目录下的elasticsearch.bat<br>
[下载](https://www.elastic.co/cn/downloads/past-releases)

**CAT API** 

```
/_cat/allocation  #查看单节点的shard分配整体情况
/_cat/shards #查看各shard的详细情况
/_cat/shards/{index} #查看指定分片的详细情况
/_cat/master #查看master节点信息
/ cat/nodes #查看所有节点信息
/_cat/indices #查看集群中所有index的详细信息
/_cat/indices/{index} #查看集群中指定index的详细信息
/_cat/count #查看当前集群的doc数量
/ cat/count/{index} #查看指定索引的doc数量
/_cat/recovery #查看集群内每个shard的recovery过程.调整replica
/_cat/recovery/{index}#査看指定索引shard的recovery过程
/_cat/health #查看集群当前状态:红、黄、绿
/_cat/pending tasks #查看当前集群的pending task
/_cat/aliases/{alias} #查看指定索引的alias信息
/_cat/thread poo1 #集群各节点内部不同类型的threadpoo1的统计信息，
/_cat/plugins #查看集群各个节点上的plugin信息
/ cat/fielddata #查看当前集群各个节点的fielddata内存使用情况
```

运行本地ES后，执行[示例](http://localhost:9200/_cat/health?v)

## 客户端Kibana
下载压缩包解压缩，并执行bin目录下的kibana.bat<br>
[下载](https://www.elastic.co/cn/downloads/past-releases)

## 索引

**创建**
```

PUT /user

GET /user

PUT /student index
{
	"settings":{
		"number of shards": 1,
		"number of replicas": 1
	},
	"mappings":{
		"properties"{
			"name":{
				"type" :"text"
			},
			"age":{
				type":"integer
			},
			"enrolled date":{
				"type": "date"
			}
		}
	}
}


GET /student index
```

**查询**
```
GET /employee/_doc/1

GET /employee/_mget{
	"ids": ["1","2","3"]
}

```

更多示例参考官网教程， [官网](https://www.elastic.co/guide/en/elasticsearch/reference/7.17/index.html)
## 文档

**创建**
```

PUT /employee/_doc/1
{
	"name":"张三”,
	"sex": 1,
	"age": 25,
	"address":"广州天河公园",
	"remark":"java developer"
}

POST /employee/_doc
{
	"name":"李四”,
	"sex": 1,
	"age": 25,
	"address":"广州天河公园",
	"remark":"java developer"
}


```
