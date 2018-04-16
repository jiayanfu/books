#redis的内存机制

#redis的vm机制
## key在内存中，value位于swap中，无论vm-max-memory设置为多大
## 一个page只能被一个对象使用；一个对象可以使用多个page

#redis的数据类型
## key
### DEL
### DUMP 
### EXISTS 
### EXPIRE
### EXPIREAT
### PEXPIRE
### PEXPIREAT
### PERSIST key
### TTL key
### PTTL key
### RENAME key newkey
### RENAMENX key newky ：newkey 不存在时，才进行重命名

## string
### SET 会覆盖重名的，如果不想覆盖，使用setnx 
#### SET 值类型可以为整形
### GET
### GETSET
### GETRANGE
### MGET key1 key2
### MSET key1 value1 [key2 value2]
### SETEX key seconds value
### SETNX key value
### MSETNX key value [key value]
### STRLEN key
### INCR key 
### INCRBY key value
### INCRBYFLOAD key value
### DECR key
### DECRBY key value


## hash
### HSET :
### HGET : 
### HGETALL	:获取所有的fileds以及filed值
### HMSET	key field1 value1 field2 value2 :设置多个field值
### HMGET	key field1 [field2]： 获取多个filed值
### HLEN key:	获取filed长度
### HKEYS key： 获取所有的filed
### HSETNX key filed1 value1:当field1不存在时，设置filed1
### HVALS key :获取所有的filed值

## list
### LPUSH key value1 [value2]
### LPUSHX key value
### RPUSH
### RPUSHX 
### LPOP
### RPOP
### LRANGE key start stop
### LTRIM key start top
### LLEN
### LINDEX key index 
### BLPOP key1 [key2] timeout
### BRPOP key1 [key2] timeout
### BRPOPLPUSH src_key dest_key timeout
### RPOPLPUSH src_key dest_key 
### LINSERT key BEFORE|AFTER pivot value
### LREM key count value (count只是用来表明搜索方向，大于0从头开始，小于0从尾开始，等于0 删除所有)
### LSET key index value 


## set
	无序集合，和list的区别是。元素不可以重复，而且无序
### SADD key [mem1] [mem2]
### SCARD key
### SDIFF key1 [key2]
### SINTER key1 [key2]
### SUNION key1 [key2]
### SINTERSTORE destinnation [key1] [key2]
### SUNIONSTORE destinnation [key1] [key2]
### SISMEMBER key value
### SMEMEBERS key
### SPOP 返回一个随机元素
### SMOVE src dest mem
### SRANDOM key [count] 返回集合中一个或者多个
### SREM key [mem1] [mem2]
### SSCAN key cursor [MATCH pattern] [COUNT count]

## zset
	有序集合
### ZADD
### ZCARD 
### ZCOUNT key min max
### ZINCRBY key increment member
### ZINTERSTORE dest numkeys key1[key2]
### ZUNIONSTORE dest numkeys key1[key2]
### ZLEXCOUNT key min max  字典区间
### ZRANGE key start stop [withscores是否要显示分数]
### ZRANGEBYLEX
### ZRANGEBYSCORE
### ZRANK key mem 返回排名
### ZVERRANK
### ZREVRANGE 
### ZREM
### ZREMRANGEBYLEX
### ZREMRANGEBYRANK
### ZREMRANGEBYSCORE
### ZVERRANGE
### ZVERRANGEBYSCORE
### ZSCORE key mem
### ZSCAN key cursor [MATCH pattern] [COUNT count]


#publish subscribe
## PUBLISH channel message
## PUBSUB <subcommand> [arguments]
## SUBSCRIBE channels [channels...]
## PSUBSCRIBE <pattern> [<pattern>]
## PUNSUBSCRIBE <pattern> [<pattern>]
## UNSUBSCRIBE channels [channels..]


# redis transaction
## start : MULTI
## QUEUED
## exec: EXEC 
## redis 单个命令是原子操作，redis transcation 不是原子操作；即便中间有失败，仍然会执行后面的语句，并且不会回退；transction	 更像是打包的脚本
## 在transaction执行过程中，其他客户端提交的命令不会插入到事务的执行命令序列中
## DISCARD 
## MULTI
## EXEC
## UNWATCH
## WATCH

# redis script

# redis connect
## AUTH 
## ECHO
## PING
## QUIT
## SELECT 

# redis server
## BGREWRITEAOF
## BGSAVE
## CLINET KILL [ip:port] [ID client-id]
## CLIENT LIST
## CLIENT SETNAME connection-name
## CLIENT GETNAME
## CLIENT PAUSE timeout
## CLUSTER slots
## COMMAND
## COMMAND COUNT
## COMMAND GETKEYS 
## TIME
## COMMAND INFO 
## FLUSHALL
## FLUSHDB
## DEBUG OBJECT KEY
## DEBUG SEGFAULT
## INFO
## LASTSAVE
## MONITOR
## ROLE
## SAVE
## SHUTDOWN [SAVE][NOSAVE]
## SLAVEOF host port
## SLOWLOG 
## SYNC 同步主从服务器



