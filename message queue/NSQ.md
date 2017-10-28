NSQ
# nsqlookupd
## 唯一性，在一个Nsq服务中只有一个nsqlookupd服务。当然也可以在集群中部署多个nsqlookupd，但它们之间是没有关联的
## 去中心化，即使nsqlookupd崩溃，也会不影响正在运行的nsqd服务.
## 充当nsqd和naqadmin信息交互的中间件
## 提供一个http查询服务，给客户端定时更新nsqd的地址目录 
## 4160 4161

# nsqd
# nsqadmin


example
https://segmentfault.com/a/1190000009194607#articleHeader16