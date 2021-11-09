# Mongo
显示所有数据库： show dbs

当前数据库: db

模糊匹配 ： $regex:

---
--备份单个表

mongodump -u  superuser -p 123456  --port 27017 --authenticationDatabase admin -d myTest -c d -o /backup/mongodb/myTest_d_bak_201507021701.bak



--备份单个库

mongodump  -u  superuser -p 123456 --port 27017  --authenticationDatabase admin -d myTest -o  /backup/mongodb/



--备份所有库

mongodump  -u  superuser -p 123456 --authenticationDatabase admin  --port 27017 -o /root/bak 



--备份所有库推荐使用添加--oplog参数的命令，这样的备份是基于某一时间点的快照，只能用于备份全部库时才可用，单库和单表不适用：

mongodump -h 127.0.0.1 --port 27017   --oplog -o  /root/bak 



--同时，恢复时也要加上--oplogReplay参数，具体命令如下(下面是恢复单库的命令)：

mongorestore  -d swrd --oplogReplay  /home/mongo/swrdbak/swrd/



--恢复单个库：

mongorestore  -u  superuser -p 123456 --port 27017  --authenticationDatabase admin -d myTest   /backup/mongodb/



--恢复所有库：

mongorestore   -u  superuser -p 123456 --port 27017  --authenticationDatabase admin  /root/bak



--恢复单表

mongorestore -u  superuser -p 123456  --authenticationDatabase admin -d myTest -c d /backup/mongodb/myTest_d_bak_201507021701.bak/myTest/d.bson
