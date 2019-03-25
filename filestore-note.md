
mvn clean package -DskipTests -T 6

## FileStore文件存储实例分析
分为Server和CLient两部分

FileStoreStateMachine Server
For example ratis-examples/src/main/bin/server.sh filestore server --id n0 --storage /tmp/data --peers n0:172.26.32.224:6000,n1:172.26.32.225:6001,n2:172.26.32.226:6002

FileStoreStateMachine Client
For example ratis-examples/src/main/bin/client.sh filestore loadgen --size 1048576 --numFiles 1000 --peers n0:172.26.32.224:6000,n1:172.26.32.225:6001,n2:172.26.32.226:6002


**peer**表示raft协议的参与者（leader/follower/candidate etc.)
## FileStore代码
server.sh, client.sh脚本都是运行org.apache.ratis.examples.common.Runner类。

## 流程
client:
通过RaftClient.Builder构建出RaftClient
然后在FileStore的Client-LoadGen里面operation方法开始发起请求：
通过fileStoreClient.writeAsync方法异步发送：

RaftClientImpl里面通过信号量Semaphore来进行流控

slidingWindows滑动窗口干啥子用？
 in order to support async calls to the RAFT service or individual servers.
