# go-ethereum-comment
reading go-ethereum code, analyze and comment it.

主要阅读的go-ethereum的版本为：`1.10.7`

## 基本概念
### Total Difficult
当前的总难度，由从genesis块开始累加到当前块的难度总和。

每一个块的Header里面只是记录了挖到该块的时候，当时的Difficulty值是多少。
在insertChain里面动态的累加到Block的临时变量Td里面。
该Td值也会缓存到数据库里面，在重启客户端的时候有用到，不能只保存的内存中。

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


## 基本流程

* downloader下载得到的block通过blockchain的InsertChain添加到区块链中。

* blockchain在eth和downloader里面通过config共享同一个对象。

### blockchain update

BlockChain的SetHeadBeyondRoot直接设定当前链。reorg最长链分枝的时候，也是调用SetHeadBeyondRoot函数。

### downloader
### 启动geth

## 主要流程

### 本地同步流程
#### 如何存盘
#### 如何处理分叉

