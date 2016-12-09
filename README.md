# hyperledger 笔记

## 目录

#### 1.hyperledger whitepaper 白皮书

#### 2.hyperledger zh 

#### 3.PBFT	共识算法
	http://bitkan.com/news/topic/21120
	http://www.jianshu.com/p/fb5edf031afd
#### 4.go 		
	https://zengweigang.gitbooks.io/core-go/content/eBook/06.3.html

#### 5.fabric 


## 1.hyperledger whitepaper 白皮书

### 1.1 背景
	身份识别,隐私,审核提供一个安全的模型,缩短运算周期.
	链上代码 chaincode 执行智能合约
	身份识别,可审核性
### 1.2 关键服务

**(点对点协议P2P)** 
	google RPC

**(分布式账本)**
	rocksDB

**(共识管理)**		
	PBFT

## 2.hyperledger zh 

### 2.1 fabirc
	每个参与者通过向网络membership服务证明自己的身份来访问系统。

### 2.2 消息	
	消息在节点之间通过Messageproto 结构封装来传递的，可以分为 4 种类型：发现（Discovery）, 交易（Transaction）, 同步(Synchronization)和共识(Consensus)。
`CORE_PEER_DISCOVERY_ROOTNODE`
**域的定义:**

- `PeerID` 是在启动时或配置文件中定义的 peer 的任意名字
- `PeerEndpoint` 描述了端点和它是验证还是非验证 peer
- `pkiID` 是 peer 的加密ID
- `address` 以`ip:port`这样的格式表示的 peer 的主机名或IP和端口
- `blockNumber` 是 peer 的区块链的当前的高度

如果收到的`DISC_HELLO` 消息的块的高度比当前 peer 的块的高度高，那么它马上初始化同步协议来追上当前的网络。

`DISC_HELLO`之后，peer 会周期性的发送`DISC_GET_PEERS`来发现任意想要加入网络的 peer。收到`DISC_GET_PEERS`后，peer 会发送`payload`
包含`PeerEndpoint`的数组的`DISC_PEERS`作为响应。这是不会使用其它的发现消息类型。	



## 4.go


