## 简介
SpiderStore接入了主流公链及知名应用链的完整数据，并以此为核心驱动力，将各公链上的DAPP数据以排行榜形式完整呈现，产品公开透明、排行无人工干预、从根本杜绝恶意刷榜。

## DApp维度
DApp是Decentralized Application的缩写，译为：去中心化的应用。

DApp至少对应n(≥1)个合约地址。

### 活跃用户
```
DApp的去重用户数
```

##### Ethereum以太坊
ua = unique(fromAddress(tx))

##### EOS柚子
ua = unique(actorOfTransferEOS(action) or actorOfTransferToken(action) or actorOfAccount(action) )

##### Tron波场
ua = unique(ownerAddress(contract))

contract: TransferAssetContract、TransferContract、TriggerSmartContract

---
### 新增用户
```
DApp首次使用用户
```

##### Ethereum以太坊
nu = first(fromAddress(tx))

##### EOS柚子
nu = first(actorOfTransferEOS(action) or actorOfAccount(action)) 

##### Tron波场
nu = first(ownerAddress(contract))

contract: TransferAssetContract、TransferContract、TriggerSmartContract

---

### 交易数
```
DApp'交易次数/合约调用次数'
```

##### Ethereum以太坊
tx = count(tx)

##### EOS柚子
tx = count(eosTransfer(action) + actorOfAccount(action)+ tokenTransfer(action)) 

##### Tron波场
tx = count(contract)

contract: TransferAssetContract、TransferContract、TriggerSmartContract

---
### 交易额
```
DApp交易公链Token(如：eth、eos、tron)
```

##### Ethereum以太坊
volume = add(eth)

##### EOS柚子
volume = add(eos)

##### Tron波场
volume = add(trx)

---
### 余额
```
DApp对应地址余额总和
```

##### Ethereum以太坊
balance = add(eth)

##### EOS柚子
balance = add(eos)

##### Tron波场
balance = add(trx)

---


## 公链维度
公链即公有链。

公有链是指全世界任何人都可读取、发送交易且交易能获得有效确认的、也可以参与其中共识过程的区块链。

### 活跃用户
```
公链的去重用户数
```

##### Ethereum以太坊
au = unique(fromAddress(tx))

##### EOS柚子
au = unique(actorOfTransferEOS(action) + actorOfAccount(action)) 

##### Tron波场
au = unique(ownerAddress(contract))

---

### 新增用户
```
公链首次使用用户
```

##### Ethereum以太坊
nu = first(fromAddress(tx))

##### EOS柚子
nu = first(actorOfTransferEOS(action) or actorOfAccount(action)) 

##### Tron波场
nu = first(ownerAddress(contract))

contract: TransferAssetContract、TransferContract、TriggerSmartContract

---

### 交易数
```
公链'Transaction'数
```

##### Ethereum以太坊
tx = count(tx)

##### EOS柚子
tx = count(eosTransfer(action) + actorOfAccount(action)) 

##### Tron波场
tx = count(contract)

contract: TransferAssetContract、TransferContract、TriggerSmartContract

---
### 交易额
```
交易公链Token(如：eth、eos、tron)
```

##### Ethereum以太坊
volume = add(eth)

##### EOS柚子
volume = add(eos)

##### Tron波场
volume = add(trx)



### DApp分析-活跃用户
```
公链下已知DApp活跃用户
注意: 当前整体未去重。如:U-A用户同时使用D-A和D-B两个应用，算做2个活跃用户
```

##### Ethereum以太坊
au = unique(fromAddress(tx))

##### EOS柚子
au = unique(actorOfTransferEOS(action) + actorOfAccount(action)) 

##### Tron波场
au = unique(ownerAddress(contract))

---

### DApp分析-交易数
```
公链下已知DApp'交易次数/合约调用次数'
```

##### Ethereum以太坊
tx = count(tx)

##### EOS柚子
tx = count(eosTransfer(action) + actorOfAccount(action)) 

##### Tron波场
tx = count(contract)

contract: TransferAssetContract、TransferContract、TriggerSmartContract

---
### DApp分析-交易额
```
公链下已知DApp交易公链Token(如：eth、eos、tron)
```

##### Ethereum以太坊
volume = add(eth)

##### EOS柚子
volume = add(eos)

##### Tron波场
volume = add(trx)

---
### DApp分析-新增DApp
```
公链下已知新增DApp
```

##### Ethereum以太坊
volume = add(dapp)

##### EOS柚子
volume = add(dapp)

##### Tron波场
volume = add(dapp)

---

## 时间维度

#### 24h/24小时
链上数据**前24小时至当前时刻**

#### 7d/7天
链上数据**前7天至昨天**

#### 30d/30天
链上数据**前30天至昨天**

#### 昨日
链上数据**昨日全天时间**

#### 累计
链上数据**上线至当前时刻**


