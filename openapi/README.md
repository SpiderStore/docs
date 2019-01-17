# SpiderStore OpenAPI
API域名：https://openapi.spider.store

## Authentication
每个接口的header需要携带鉴权字段secret

## Platform

区块链平台

|Platform|区块链|
| --- | --- | 
|Ethereum|以太坊|
|EOS|柚子|
|Tron|波场|


## DApp

#### DApp-分类列表
-------
**HTTP Request**
GET /dapps/categories

**Response**

JSON
```json
{
  "data": ["全部", "游戏", "交易市场", "竞猜", "社交", "其它"]
}
```

#### DApp-列表

-------

获取所有DApp列表

**HTTP Request**

GET /dapps

**Query Parameters**

|Parameter|Default|Description|
| --- | --- | --- |
| current | 1 | 起始页 |
| page_size | 10 | 每页条目数 |
| name | null | 根据名称筛选dapp |
| category | 全部 | 根据分类筛选dapp |
| platform | Ethereum | 根据平台筛选dapp|

**Response**

JSON
```json
{
  //必有，是否存在下一页
  "has_next": true,
  //必有，当前页号。默认：1
  "current": 1,
  //必有，当前页条目数。默认：10
  "page_size": 10,
  //必有，总条目数
  "total": 100,
  //必有，数据区域
  "data": [{
    //必有，dapp_id
    "id": "5b95db7a855f0800121267c3",
    //必有，dapp名称
    "name": "PRA CandyBox",
    //必有，dapp所属分类集合
    "categories": [],
    //必有，dapp标签集合
    "tags": [],
    //必有，dapp评分. Double，1-5.
    "score": 0,
    //可空，dapp发布时间.timestamp
     "release_time": 1530609478,
    //可空，dapp描述
    "description": "基于以太坊、EOS、雷电网络与IPFS技术的大数据精准广告区块链应用",
    //可空，dapp详细描述
    "detail_description": "基于以太坊、EOS、雷电网络与IPFS技术的大数据精准广告区块链应用，主要应用于去中心化媒体与应用的广告投放结算，用户投票，防点击欺诈等业务场景，从广告角度切入，服务于整个以太坊、EOS生态。团队为腾讯系背景，在区块链、大数据与数字广告方面有资深经验和资源",
    //可空，dapp开发者说
    "developer_idea": null,
    //必有，dapp上链平台。Ethereum、EOS
    "platforms": [
                "EOS"
            ],
    //可空，主图
    "main_image": "https://static.spider.store/dapp/37e06d23-a67f-43f3-8d5b-a3878b627ee4.png",
    //可空,logo
    "logo": "https://static.spider.store/dapp/37e06d23-a67f-43f3-8d5b-a3878b627ee4.png",
    //必有，辅图
    "images": [],
    //必有，合约集合
    "contracts": [
      {
        //必有，合约信息查看地址
        "url": "https://eospark.com/MainNet/account/prochaintech",
        //必有，合约地址
        "address": "prochaintech",
        //必有，合约类型。Ethereum、EOS
        "type": "EOS"
      }
    ],
    //必有，以太坊数据
    "eos": {
      //必有，当前余额
      "balance": 42992.6028,
      //必有，24小时交易额
      "value_of_24hours": 3353.9015,
      //必有，7天交易额
      "value_of_7days": 34585.1405,
      //必有，30天交易额（计算环比）
      "value_of_30days": 203901.369,
      //必有，上一轮24小时交易额（计算环比）
      "value_of_last_24hours": 2582.8843,
      //必有，上一轮7天交易额（计算环比）
      "value_of_last_7days": 51848.9156,
      //必有，上一轮30天交易额（计算环比）
      "value_of_last_30days": 419666.3903,
      //必有，24小时交易数
      "tx_of_24hours": 11796,
      //必有，7天交易数
      "tx_of_7days": 89865,
      //必有，30天交易数
      "tx_of_30days": 468831,
      //必有，上一轮24小时交易数（计算环比）
      "tx_of_last_24hours": 8024,
      //必有，上一轮7天交易数（计算环比）
      "tx_of_last_7days": 101130,
      //必有，上一轮30天交易数（计算环比）
      "tx_of_last_30days": 1023662,
      //必有，24小时日活
      "ua_of_24hours": 2123,
      //必有，昨日日活
      "ua_of_yesterday": 1158,
      //必有，上一轮24小时日活
      "ua_of_last_24hours": 1155,
      //必有，今日日活
      "ua_of_today": 15,
      //必有，前天日活
      "ua_of_before_yesterday": 1463,
      //必有，30天日活
      "ua_of_30days": 39599,
      //必有，上一轮30天日活
      "ua_of_last_30days": 72527
    },
    //必有，组织/公司/团队信息
    "organization": {
      //可空，组织/公司/团队名称
      "name": null,
      //可空，组织/公司/团队联系方式
      "contact": null
    },
    //必有，dapp详情地址
    "url": "https://www.spider.store/dapps/5b46236f07cf996624126138",
    //必有，dapp官网地址
    "website": "https://play.0xuniverse.com/",
  }]
}
```

#### DApp-详情

-------

**HTTP Request**

GET /dapps/{id}

**Response**


JSON
```json
{
  "data": {
    //必有，dapp_id
    "id": "5b95db7a855f0800121267c3",
    //必有，dapp名称
    "name": "PRA CandyBox",
    //必有，dapp所属分类集合
    "categories": [],
    //必有，dapp标签集合
    "tags": [],
    //必有，dapp评分. Double，1-5.
    "score": 0,
    //可空，dapp发布时间.timestamp
     "release_time": 1530609478,
    //可空，dapp描述
    "description": "基于以太坊、EOS、雷电网络与IPFS技术的大数据精准广告区块链应用",
    //可空，dapp详细描述
    "detail_description": "基于以太坊、EOS、雷电网络与IPFS技术的大数据精准广告区块链应用，主要应用于去中心化媒体与应用的广告投放结算，用户投票，防点击欺诈等业务场景，从广告角度切入，服务于整个以太坊、EOS生态。团队为腾讯系背景，在区块链、大数据与数字广告方面有资深经验和资源",
    //可空，dapp开发者说
    "developer_idea": null,
    //必有，dapp上链平台。Ethereum、EOS
    "platforms": [
                "EOS"
            ],
    //可空，主图
    "main_image": "https://static.spider.store/dapp/37e06d23-a67f-43f3-8d5b-a3878b627ee4.png",
    //可空,logo
    "logo": "https://static.spider.store/dapp/37e06d23-a67f-43f3-8d5b-a3878b627ee4.png",
    //必有，辅图
    "images": [],
    //必有，合约集合
    "contracts": [
      {
        //必有，合约信息查看地址
        "url": "https://eospark.com/MainNet/account/prochaintech",
        //必有，合约地址
        "address": "prochaintech",
        //必有，合约类型。Ethereum、EOS
        "type": "EOS"
      }
    ],
    //必有，以太坊数据
    "eos": {
      //必有，当前余额
      "balance": 42992.6028,
      //必有，24小时交易额
      "value_of_24hours": 3353.9015,
      //必有，7天交易额
      "value_of_7days": 34585.1405,
      //必有，30天交易额（计算环比）
      "value_of_30days": 203901.369,
      //必有，上一轮24小时交易额（计算环比）
      "value_of_last_24hours": 2582.8843,
      //必有，上一轮7天交易额（计算环比）
      "value_of_last_7days": 51848.9156,
      //必有，上一轮30天交易额（计算环比）
      "value_of_last_30days": 419666.3903,
      //必有，24小时交易数
      "tx_of_24hours": 11796,
      //必有，7天交易数
      "tx_of_7days": 89865,
      //必有，30天交易数
      "tx_of_30days": 468831,
      //必有，上一轮24小时交易数（计算环比）
      "tx_of_last_24hours": 8024,
      //必有，上一轮7天交易数（计算环比）
      "tx_of_last_7days": 101130,
      //必有，上一轮30天交易数（计算环比）
      "tx_of_last_30days": 1023662,
      //必有，24小时日活
      "ua_of_24hours": 2123,
      //必有，昨日日活
      "ua_of_yesterday": 1158,
      //必有，上一轮24小时日活
      "ua_of_last_24hours": 1155,
      //必有，今日日活
      "ua_of_today": 15,
      //必有，前天日活
      "ua_of_before_yesterday": 1463,
      //必有，30天日活
      "ua_of_30days": 39599,
      //必有，上一轮30天日活
      "ua_of_last_30days": 72527
    },
    //必有，组织/公司/团队信息
    "organization": {
      //可空，组织/公司/团队名称
      "name": null,
      //可空，组织/公司/团队联系方式
      "contact": null
    },
    //必有，dapp详情地址
    "url": "https://www.spider.store/dapps/5b46236f07cf996624126138"
    //必有，dapp官网地址
    "website": "https://play.0xuniverse.com/",
  }
}
```


#### DApp-日粒度交易数据

-------

获取DApp按日聚合的交易数据

**HTTP Request**

GET /dapps/{id}/{platform}/daily_transactions

**Query Parameters**

|Parameter|Default|Description|
| --- | --- | --- |
| start_time | 1514736000 | 起始时间戳，默认30天前（包含） |
| end_time | 1515254400 | //可选，结束时间戳，默认今天（不包含）|

**Response**

JSON
```json
{
    //必有，默认：[]
    "data": [
        {
            //必有，用户活跃数 
            "ua": 1417,
            //必有，交易数
            "tx": 9580,
            //必有，单位：ETH
            "value": 3253.4872,
            //必有，日期时间戳且不重复 请自行格式化
            "date": 1532793600
        }
    ]
}
```
