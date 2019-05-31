## ATP60协议API

版本v1.0.0



文档修订记录

| 日期       | 版本   | 说明         | 作者  |
| ---------- | ------ | ------------ | ----- |
| 2019-05-28 | v1.0.0 |  | 吴清云 |


### 获取请求令牌

> 获取请求令牌TOKEN

```json
http请求方式：POST
https://{url}/auth/accessToken

{
    "appId": "19d0bc0e3b13615271",
    "appKey": "e4629469d2cdff53a6cf733377614062"
}

```

请求报文说明：

| 字段名                  | 类型   | 是否必填 | 描述                                                         |
| ----------------------- | ------ | -------- | ------------------------------------------------------------ |
| appId             | String | 是       | 平台分配的商户号     |
| appKey                    | String | 是       | 商户密钥     |

响应报文：

```json
{
  "data": {
        "expiresIn": 7200,
        "accessToken":""
    },
  "errCode": "0",
  "msg": "操作成功"
}
```

响应报文说明：

| 字段名    | 类型   | 是否必填 | 描述           |
| --------- | ------ | -------- | -------------- |
| expiresIn      | long | 是       | 过期时间|
| accessToken      | String | 是       | 请求令牌|


### 查询用户所有的券

> 查询用户所有的券

```json
http请求方式：POST
https://{url}/ticket/v1/account/balance
{
	
	"accessToken":"accessToken",
	"address":"buQmpzjwkA8yY18vzrnk72SuTmm5bz1rTyej",
	"startPage":"",
	"pageSize":""
}
```

请求报文说明：

| 字段名                  | 类型   | 是否必填 | 描述                                                         |
| ----------------------- | ------ | -------- | ------------------------------------------------------------ |
| accessToken             | String | 是       | 请求令牌     |
| address                 | String | 是       | 账户地址     |
| startPage               | String | 是       |分页起始页|
| pageSize                | String | 是       |每页数量|

响应报文：

```json
{

  "data": {
    "ticketList":[
		{
			"contractAddress": "合约地址",
			"ticketId": "券Id",
			"ticketName": "券名称",
			"ticketIcon": "url",
			"ticketDesc": "券描述",
			"ticketIssuer": {
				"address": "发行方区块链地址",
				"icon": "",
				"name": "名称"
			},
			"ticketAcceptance": {
				"address": "承兑方区块链地址",
				"icon": "",
				"name": "名称"
			},
			"ticketFaceValue": "600",
			"ticketSpe": [{
					"key": "颜色",
					"value": "红色"
				}, {
					"key": "尺寸",
					"value": "42"
				}
			],
			"balance": "100",
			"startTime":"",
			"endTime":"",
			"trancheId":""
		}
    ],
	
	"page": {
            "count": 1,
            "curSize": 3,
            "endOfGroup": 1,
            "firstResultNumber": 0,
            "nextFlag": false,
            "queryTotal": true,
            "size": 10,
            "start": 1,
            "startOfGroup": 1,
            "total": 3
    }
  },
  
  "errCode": "0",
  "msg": "操作成功"
}
```
> 响应报文说明：

| 字段名    | 类型   | 是否必填 | 描述           |
| --------- | ------ | -------- | -------------- |
| ticketList   | List | 是        | 券列表      |
| contractAddress  | String | 是        | 合约地址      |
| ticketId  | String | 是        | 券ID      |
| ticketName  | String | 是        | 券名称      |
| ticketIcon  | String | 是        | 券icon      |
| ticketDesc  | String | 是        | 券描述      |
| contractAddress  | String | 是        | 合约地址      |
| contractAddress  | String | 是        | 合约地址      |
| ticketIssuer  | Object | 是        | 券发行方      |
| ticketIssuer.address  | String | 是        | 券发行方地址      |
| ticketIssuer.icon  | String | 是        | 券发行方icon      |
| ticketIssuer.name  | String | 是        | 券发行方名称      |
| ticketAcceptance  | Object | 是        | 券发行方名称      |
| ticketAcceptance.address  | String | 是        | 承兑方地址      |
| ticketAcceptance.icon  | String | 是        | 承兑方icon      |
| ticketAcceptance.name  | String | 是        | 承兑方名称      |
| ticketFaceValue  | String | 是        | 面值      |
| ticketSpe  | List | 是        |规格      |
| ticketSpe.key  | String | 是        | 属性key      |
| ticketSpe.value  | String | 是        | 属性值      |
| balance  | String | 是        | 余额      |
| startTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| endTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| trancheId  | String | 是        | 区块链分组id      |


### 查询所有的券

> 查询所有的券

```json
http请求方式：POST
https://{url}/ticket/v1/list
{
	
	"accessToken":"accessToken",
	"startPage":"",
	"pageSize":""
}
```

请求报文说明：

| 字段名                  | 类型   | 是否必填 | 描述                                                         |
| ----------------------- | ------ | -------- | ------------------------------------------------------------ |
| accessToken             | String | 是       | 请求令牌     |
| startPage               | String | 是       |分页起始页|
| pageSize                | String | 是       |每页数量|


响应报文：

```json
{

  "data": {
    "ticketList":[
		{
			"contractAddress": "合约地址",
			"ticketId": "券Id",
			"ticketName": "券名称",
			"ticketIcon": "url",
			"ticketDesc": "券描述",
			"ticketIssuer": {
				"address": "发行方区块链地址",
				"icon": "",
				"name": "名称"
			},
			"ticketAcceptance": {
				"address": "承兑方区块链地址",
				"icon": "",
				"name": "名称"
			},
			"ticketFaceValue": "600",
			"ticketSpe": [{
					"key": "颜色",
					"value": "红色"
				}, {
					"key": "尺寸",
					"value": "42"
				}
			],
			"startTime":"",
			"endTime":"",
			"trancheId":""
		}
    ],
	
	"page": {
            "count": 1,
            "curSize": 3,
            "endOfGroup": 1,
            "firstResultNumber": 0,
            "nextFlag": false,
            "queryTotal": true,
            "size": 10,
            "start": 1,
            "startOfGroup": 1,
            "total": 3
    }
  },
  
  "errCode": "0",
  "msg": "操作成功"
}
```
> 响应报文说明：

| 字段名    | 类型   | 是否必填 | 描述           |
| --------- | ------ | -------- | -------------- |
| ticketList   | List | 是        | 券列表      |
| contractAddress  | String | 是        | 合约地址      |
| ticketId  | String | 是        | 券ID      |
| ticketName  | String | 是        | 券名称      |
| ticketIcon  | String | 是        | 券icon      |
| ticketDesc  | String | 是        | 券描述      |
| contractAddress  | String | 是        | 合约地址      |
| contractAddress  | String | 是        | 合约地址      |
| ticketIssuer  | Object | 是        | 券发行方      |
| ticketIssuer.address  | String | 是        | 券发行方地址      |
| ticketIssuer.icon  | String | 是        | 券发行方icon      |
| ticketIssuer.name  | String | 是        | 券发行方名称      |
| ticketAcceptance  | Object | 是        | 券发行方名称      |
| ticketAcceptance.address  | String | 是        | 承兑方地址      |
| ticketAcceptance.icon  | String | 是        | 承兑方icon      |
| ticketAcceptance.name  | String | 是        | 承兑方名称      |
| ticketFaceValue  | String | 是        | 面值      |
| ticketSpe  | List | 是        |规格      |
| ticketSpe.key  | String | 是        | 属性key      |
| ticketSpe.value  | String | 是        | 属性值      |
| startTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| endTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| trancheId  | String | 是        | 区块链分组id      |