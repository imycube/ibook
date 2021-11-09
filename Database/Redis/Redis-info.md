# Redis

server：服务器运行的环境参数
127.0.0.1:6379> info server
# Server
redis_version:5.0.0  //版本

redis_git_sha1:00000000  

redis_git_dirty:0

redis_build_id:d7f585d46da7df6a

redis_mode:standalone //单机或集群

os:Darwin 18.0.0 x86_64 //操作系统版本

arch_bits:64 //64位

multiplexing_api:kqueue //多路复用模式：https://www.cnblogs.com/moonz-wu/p/4740908.html

atomicvar_api:atomic-builtin //原子处理API

gcc_version:4.2.1 //编译redis时所使用的GCC版本

process_id:56247 //进程PID

run_id:2e82362af1c456809a0ab20d46ec542e8526da3e //唯一随即标识符，用于sentinel和cluster

tcp_port:6379 //端口号

uptime_in_seconds:191356 //启动时长

uptime_in_days:2 //启动天数

hz:10 //redis内部调度频率（关闭timeout客户端，删除过期key等）

configured_hz:10

lru_clock:7302602 //lru时钟

executable:/Users/why/redis-server //执行文件

config_file:/usr/local/redis/redis.conf //配置文件

clients：客户端的相关信息

127.0.0.1:6379> info clients

# Clients
connected_clients:8 //已连接的客户端数量

client_recent_max_input_buffer:2 //当前连接客户端中最长的输出列表

client_recent_max_output_buffer:0 //当前连接的客户端当中，最大输入缓存

blocked_clients:0 //正在等待阻塞命令的客户端的数量（BLPOP、BRPOP、BRPOPLPUSH）

memory：服务器运行内存统计数据

127.0.0.1:6379> info memory

# Memory
used_memory:2219728 //redis分配的内存总量，包含了进程开销和数据内存，单位：字节

used_memory_human:2.12M //直观展示

used_memory_rss:1486848 //操作系统分配的内存总量

used_memory_rss_human:1.42M //直观展示

used_memory_peak:2320464 //redis内存峰值

used_memory_peak_human:2.21M //直观展示

used_memory_peak_perc:95.66% //used_memory除以used_memory_peak

used_memory_overhead:2203820 //Redis为了维护数据集的内部机制所需的内存开销，包括所有客户端输出缓冲区、查询缓冲区、AOF重写缓冲区和主从复制的backlog。

used_memory_startup:986976 //redis启动时消耗的内存

used_memory_dataset:15908  //数据占用内存大小 等于 used_memory-user_memory_overhead

used_memory_dataset_perc:1.29% //数据占用百分比

allocator_allocated:2186384 

allocator_active:1448960

allocator_resident:1448960

total_system_memory:8589934592 //系统总内存

total_system_memory_human:8.00G //直观展示

used_memory_lua:37888  //lua脚本存储占用的内存

used_memory_lua_human:37.00K //直观展示

used_memory_scripts:0

used_memory_scripts_human:0B

number_of_cached_scripts:0

maxmemory:0 //配置允许redis使用的最大内存，0为不限制

maxmemory_human:0B

maxmemory_policy:noeviction //配置的内存淘汰策略,当前配置为内存满后写入失败 https://blog.csdn.net/why444216978/article/details/96175129

allocator_frag_ratio:0.66

allocator_frag_bytes:18446744073708814192

allocator_rss_ratio:1.00

allocator_rss_bytes:0

rss_overhead_ratio:1.03

rss_overhead_bytes:37888

mem_fragmentation_ratio:0.68 //内存碎片率：used_memory_rss比used_memeory

mem_fragmentation_bytes:18446744073708852080

mem_not_counted_for_evict:0

mem_replication_backlog:1048576 //主从复制缓冲区大小，默认为当前配置1M

mem_clients_slaves:0

mem_clients_normal:168084

mem_aof_buffer:0 

mem_allocator:libc //redis内存分配器，编译时指定

active_defrag_running:0 //是否有磁盘碎片正在运行

lazyfree_pending_objects:0 //是否存在延时释放挂起，有bigkey时容易出现

persistence:持久化信息

127.0.0.1:6379> info persistence

# Persistence
loading:0  //表示是否正在载入持久化文件

rdb_changes_since_last_save:0 //距离最近一次成功创建RDB持久化文件之后，经过了多少秒

rdb_bgsave_in_progress:0 //表示是否正在执行bgsave创建持久化文件

rdb_last_save_time:1567393235 //最近一次成功创建RDB文件的时间戳

rdb_last_bgsave_status:ok //表示最近一次创建RDB文件是否成功

rdb_last_bgsave_time_sec:0 //记录最近一次创建RDB文件耗费的秒数

rdb_current_bgsave_time_sec:-1  //当前正在创建RDB文件已经耗费的秒数 

rdb_last_cow_size:0 //记录父进程与子进程相比执行了多少修改

aof_enabled:1 //是否开启AOF

aof_rewrite_in_progress:0 //记录是否正在创建AOF文件

aof_rewrite_scheduled:0 //记录在AOF文件创建完毕后，是否需要执行预约的AOF重写操作

aof_last_rewrite_time_sec:0 //最近一次创建AOF文件耗费的时长

aof_current_rewrite_time_sec:-1 //当前正在创建AOF文件已经耗费的秒数

aof_last_bgrewrite_status:ok //表示最近一次子进程创建AOF文件是否成功

aof_last_write_status:ok //表示最近一次主进程创建AOF文件是否成功

aof_last_cow_size:0 //记录父进程与子进程相比执行了多少修改

aof_current_size:188 //AOF文件当前大小

aof_base_size:134 //服务启动时或AOF重写最近一次执行后AOF文件大小

aof_pending_rewrite:0 //是否有AOF重写操作在等待执行

aof_buffer_length:0 //AOF缓冲区大小

aof_rewrite_buffer_length:0 //AOF重写缓冲区大小

aof_pending_bio_fsync:0 //IO队列中等待执行fsync的数量

aof_delayed_fsync:0  //被延迟的fysnc数量

stats：通用统计数据

127.0.0.1:6379> info stats

# Stats
total_connections_received:16 //服务器已接收连接的数量

total_commands_processed:625752 //服务器已执行命令数量

instantaneous_ops_per_sec:2 //服务器每秒执行命令数量OPS

total_net_input_bytes:44830691 //网络输入总字节数

total_net_output_bytes:238587948 //网络输出总字节数

instantaneous_input_kbps:0.04 //网络输入kbps

instantaneous_output_kbps:0.04 //网络输出kbps

rejected_connections:0 //因最大客户端数量限制而被拒绝的连接请求数量

sync_full:0 //主从全量同步成功次数

sync_partial_ok:0 //主从部分同步成功次数

sync_partial_err:0 //主从部分同步失败次数

expired_keys:0 //运行以来过期的key数量

expired_stale_perc:0.00 //过期的比率

expired_time_cap_reached_count:0 //因cpu利用率过高而提前结束定期删除的次数

keyspace_hits:0 //查询key命中次数

keyspace_misses:0 //查询key未命中次数

pubsub_channels:1 //当前使用中的频道的数量

pubsub_patterns:0 //当前使用中的模式的数量

latest_fork_usec:549 //最近一次fork操作阻塞redis进程的耗时，单位：微秒

migrate_cached_sockets:0 //是否已缓存了到改地址的连接

slave_expires_tracked_keys:0 //主从实例到期key数量

active_defrag_hits:0 //主动碎片整理命中次数

active_defrag_misses:0 //主动碎片整理未命中次数

active_defrag_key_hits:0 //主动碎片整理key命中次数

active_defrag_key_misses:0 //主动碎片整理key为命中次数

replication：主从复制相关信息

主节点：
127.0.0.1:7001> info replication

# Replication
role:master

connected_slaves:2

slave0:ip=127.0.0.1,port=7000,state=online,offset=21989553,lag=0

slave1:ip=127.0.0.1,port=6379,state=online,offset=21989553,lag=0

master_replid:8df382aa7877943d6f4c467e54aaeb205c52f22f //主节点自身replid

master_replid2:50b654fb2350b6d7f8bd54a5a0978f3c5fb11d0f

master_repl_offset:22178637 //主节点当前的offset

second_repl_offset:1503820

repl_backlog_active:1

repl_backlog_size:1048576

repl_backlog_first_byte_offset:20940978

repl_backlog_histlen:1048576
 
子节点：
127.0.0.1:6379> info replication

# Replication
role:slave

master_host:127.0.0.1

master_port:7001

master_link_status:up //主节点连接状态，up正常，down断开

master_last_io_seconds_ago:0 //距离最近一次与主服务器通信已经过去了多少秒

master_sync_in_progress:0 //正在同步的进程数

slave_repl_offset:22178637 //子节点当前offset

slave_priority:100 //从节点优先级

slave_read_only:1 //子节点是否只读

connected_slaves:0

master_replid:8df382aa7877943d6f4c467e54aaeb205c52f22f  //对应主节点replid

master_replid2:0000000000000000000000000000000000000000

master_repl_offset:22178637 //主节点当前offset

second_repl_offset:1503820

repl_backlog_active:1 //是否开启backlog缓冲区

repl_backlog_size:1048576 //backlog缓冲区大小

repl_backlog_first_byte_offset:21130062

repl_backlog_histlen:1048576

cpu：CPU使用情况

127.0.0.1:7001> info  cpu

# CPU

used_cpu_sys:200.833850 //redis 服务器耗费的系统 CPU

used_cpu_user:78.669595 //redis 服务器耗费的用户 CPU

used_cpu_sys_children:0.015188 //后台进程耗费的系统 CPU

used_cpu_user_children:0.002388 //后台进程耗费的用户 CPU 

cluster：集群信息

127.0.0.1:7001> info cluster

# Cluster

cluster_enabled:0

keyspace：键值对统计数量信息

27.0.0.1:7001> info keyspace

# Keyspace

db0:keys=5,expires=0,avg_ttl=0 //avg_ttl为平均存活周期
 
常用字段和方法：

查看命令执行次数和耗时

127.0.0.1:6379> info commandstats

# Commandstats
cmdstat_info:calls=11,usec=686,usec_per_call=62.36

cmdstat_get:calls=2,usec=8,usec_per_call=4.00

cmdstat_command:calls=1,usec=1428,usec_per_call=1428.00

cmdstat_set:calls=1,usec=6,usec_per_call=6.00

查看ops

localhost:redis why$ redis-cli -p 6379 info stats | grep ops

instantaneous_ops_per_sec:6

极限情况下可以达到10W，如果ops过高，可以通过monitor指定观察一下哪些指令比较频繁

客户端连接数：
localhost:redis why$ redis-cli -p 6379 info clients

# Clients
connected_clients:8

client_recent_max_input_buffer:2

client_recent_max_output_buffer:0

blocked_clients:0
如果连接数异常，可以通过client list查看链接来源

localhost:redis why$ redis-cli -p 6379 client list

id=17 addr=127.0.0.1:7001 fd=12 name= age=198256 idle=0 flags=M db=0 sub=0 
psub=0 multi=-1 qbuf=0 qbuf-free=0 obl=0 oll=0 omem=0 events=r cmd=publish
id=16 addr=127.0.0.1:53324 fd=10 name=sentinel-7ca46925-cmd age=198256 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=0 qbuf-free=32768 obl=0 oll=0 omem=0 events=r cmd=ping

id=3 addr=127.0.0.1:53093 fd=8 name=sentinel-7ca46925-cmd age=198326 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=0 qbuf-free=0 obl=0 oll=0 omem=0 events=r cmd=ping

id=4 addr=127.0.0.1:53094 fd=9 name=sentinel-7ca46925-pubsub age=198326 idle=0 flags=P db=0 sub=1 psub=0 multi=-1 qbuf=0 qbuf-free=0 obl=0 oll=0 omem=0 events=r cmd=subscribe

id=6 addr=127.0.0.1:53096 fd=11 name=sentinel-7ca46925-pubsub age=198326 idle=0 flags=P db=0 sub=1 psub=0 multi=-1 qbuf=0 qbuf-free=0 obl=0 oll=0 omem=0 events=r cmd=subscribe

id=8 addr=127.0.0.1:53098 fd=13 name=sentinel-d83a3e57-pubsub age=198326 idle=0 flags=P db=0 sub=1 psub=0 multi=-1 qbuf=0 qbuf-free=0 obl=0 oll=0 omem=0 events=r cmd=subscribe

id=15 addr=127.0.0.1:53323 fd=7 name=sentinel-d83a3e57-cmd age=198256 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=0 qbuf-free=32768 obl=0 oll=0 omem=0 events=r cmd=publish

id=30 addr=127.0.0.1:57149 fd=14 name= age=0 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=26 qbuf-free=32742 obl=0 oll=0 omem=0 events=r cmd=client
关注超出最大连接数而被拒绝的客户端链接次数：

localhost:redis why$ redis-cli -p 6379 info stats | grep reject
rejected_connections:2
如果被拒绝的次数很多，需要调整maxclients参数

内存占用
localhost:redis why$ redis-cli -p 6379 info memory | grep used| grep human
used_memory_human:2.12M

used_memory_rss_human:1.62M

used_memory_peak_human:2.23M

used_memory_lua_human:37.00K

used_memory_scripts_human:0B
如果内存占用过大，机器无法承受，并且无法在业务上减少，可以考虑集群化

复制积压缓冲区，部分同步失败次数
localhost:redis why$ redis-cli -p 6379 info stats | grep ync

sync_full:0

sync_partial_ok:0

sync_partial_err:0

如果sync_partial_err次数多，可以考虑扩大主节点repl-backlog-size参数，默认为1M