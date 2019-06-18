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
   "meta": {
        "code": 0,
        "message": "操作成功"
    }
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
https://{url}/voucher/v1/account/balance
{
	
	"accessToken":"accessToken",
	"address":"buQmpzjwkA8yY18vzrnk72SuTmm5bz1rTyej",
	"start":"",
	"pageSize":""
}
```

请求报文说明：

| 字段名                  | 类型   | 是否必填 | 描述                                                         |
| ----------------------- | ------ | -------- | ------------------------------------------------------------ |
| accessToken             | String | 是       | 请求令牌     |
| address                 | String | 是       | 账户地址     |
| start               | String | 是       |分页起始页|
| pageSize                | String | 是       |每页数量|

响应报文：

```json
{
    "meta": {
        "code": 0,
        "message": "操作成功"
    },
    "data": {
        "page": {
            "pageSize": 10,
            "pageStart": 1,
            "pageTotal": 2
        },
        "voucherList": [{
            "contractAddress": "buQjKBwHxxpXUQ5vguogcQM6JuWpD8eQjqxB",
            "voucherId": "1ae0fd9c54ba44dd8dc38b0441b6332a",
            "voucherName": "大陷水饺韭菜1kg",
            "voucherIcon": 	"https://timgsa.baidu.com/timgf9c10cc530cool.cnFcommunity01a1.jpg",
            "faceValue": "18",
            "description": "韭菜水饺:我就是韭菜",
            "trancheId": "0",
			"balance": "100",
            "voucherProperties": [{
                "key": "价格",
                "value": "18"
            }, {
                "key": "颜色",
                "value": "黄色"
            }],
            "voucherIssuer": {
                "address": "buQjhTsw3csavGJt3su5YfsWqQteqp81ZQT8",
                "icon": "",
                "name": "三全食品有效公司"
            },
            "voucherAcceptance": [{
                "address": "buQjhTsw3csavGJt3su5YfsWqQteqp81ZQT8",
                "icon": "http://xxxxxx.png",
                "name": "三全集中处理中心"
            }]
        }]
    }
}
```
> 响应报文说明：

| 字段名    | 类型   | 是否必填 | 描述           |
| --------- | ------ | -------- | -------------- |
| voucherList | List | 是        | 券列表      |
| contractAddress  | String | 是        | 合约地址      |
| voucherId | String | 是        | 券ID      |
| voucherName | String | 是        | 券名称      |
| voucherIcon | String | 是        | 券icon      |
| description | String | 是        | 券描述      |
| voucherIssuer | Object | 是        | 券发行方      |
| voucherIssuer.address | String | 是        | 券发行方地址      |
| voucherIssuer.icon | String | 是        | 券发行方icon      |
| voucherIssuer.name | String | 是        | 券发行方名称      |
| voucherAcceptance | Object | 是        | 券发行方名称      |
| voucherAcceptance.address | String | 是        | 承兑方地址      |
| voucherAcceptance.icon | String | 是        | 承兑方icon      |
| voucherAcceptance.name | String | 是        | 承兑方名称      |
| faceValue | String | 是        | 面值      |
| voucherProperties | List | 是        |规格      |
| voucherProperties.key | String | 是        | 属性key      |
| voucherProperties.value | String | 是        | 属性值      |
| balance  | String | 是        | 余额      |
| startTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| endTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| trancheId  | String | 是        | 区块链分组id      |


### 查询所有的券

> 查询所有的券

```json
http请求方式：POST
https://{url}/voucher/v1/list
{
	
	"accessToken":"accessToken",
	"start":"",
	"pageSize":""
}
```

请求报文说明：

| 字段名      | 类型   | 是否必填 | 描述       |
| ----------- | ------ | -------- | ---------- |
| accessToken | String | 是       | 请求令牌   |
| start       | String | 是       | 分页起始页 |
| pageSize    | String | 是       | 每页数量   |


响应报文：

```json
{
    "meta": {
        "code": 0,
        "message": "操作成功"
    },
    "data": {
        "page": {
            "pageSize": 10,
            "pageStart": 1,
            "pageTotal": 2
        },
        "voucherList": [{
            "contractAddress": "buQjKBwHxxpXUQ5vguogcQM6JuWpD8eQjqxB",
            "voucherId": "1ae0fd9c54ba44dd8dc38b0441b6332a",
            "voucherName": "大陷水饺韭菜1kg",
            "voucherIcon": "https://timgsa.baidu.com/timg?f9c10cc530cool.cnFcommunity01a1.jpg",
            "faceValue": "18",
            "description": "韭菜水饺:我就是韭菜",
            "trancheId": "0",
            "voucherProperties": [{
                "key": "价格",
                "value": "18"
            }, {
                "key": "颜色",
                "value": "黄色"
            }],
            "voucherIssuer": {
                "address": "buQjhTsw3csavGJt3su5YfsWqQteqp81ZQT8",
                "icon": "",
                "name": "三全食品有效公司"
            },
            "voucherAcceptance": [{
                "address": "buQjhTsw3csavGJt3su5YfsWqQteqp81ZQT8",
                "icon": "http://xxxxxx.png",
                "name": "三全集中处理中心"
            }]
        }]
    }
}
```
> 响应报文说明：

| 字段名    | 类型   | 是否必填 | 描述           |
| --------- | ------ | -------- | -------------- |
| voucherList | List | 是        | 券列表      |
| contractAddress  | String | 是        | 合约地址      |
| voucherId | String | 是        | 券ID      |
| voucherName | String | 是        | 券名称      |
| voucherIcon | String | 是        | 券icon      |
| description | String | 是        | 券描述      |
| faceValue | String | 是        | 面值  |
| voucherIssuer | Object | 是        | 券发行方      |
| voucherIssuer.address | String | 是        | 券发行方地址      |
| voucherIssuer.icon | String | 是        | 券发行方icon      |
| voucherIssuer.name | String | 是        | 券发行方名称      |
| voucherAcceptance | Object | 是        | 券发行方名称      |
| voucherAcceptance.address | String | 是        | 承兑方地址      |
| voucherAcceptance.icon | String | 是        | 承兑方icon      |
| voucherAcceptance.name | String | 是        | 承兑方名称      |
| voucherProperties | List | 是        |规格      |
| voucherProperties.key | String | 是        | 属性key      |
| voucherProperties.value | String | 是        | 属性值      |
| startTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| endTime  | String | 是        | 有效期-开始时间 无有效期为-1      |
| trancheId  | String | 是        | 区块链分组id      |
