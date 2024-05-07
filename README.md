# go-ethereum-comment
reading go-ethereum code, analyze and comment it.

主要阅读的go-ethereum的版本为：`1.10.7`

## 基本概念
### [挖矿总难度(Total Difficult)](挖矿总难度.md)

### [以太坊难度计算详解](以太坊难度计算详解.md)

### [叔块和最重链](叔块和最重链.md)

### [Peer之间的Block同步流程](Peer之间的Block同步流程.md)
### [如何处理分叉(reorg)](如何处理分叉.md)

### [挖矿(miner)流程](挖矿流程.md)

### Node Object
一个客户端，包含各种服务goroutine

1. 管理account
2. 管理P2P对象
3. 提供HTTP，WebSocket，IPC，RPC的服务对象

### Ethereum Object
处理以太坊区块链相关的服务对象

1. 新来的区块处理
2. 区块链处理
3. 交易池管理
4. 挖矿管理
5. API管理：console可以访问的一系列接口；通过JavaScript脚本操作

### Database的schema

主要是各种key的常量。用来持久化大量的缓存变量。例如：TotalDifficulty
