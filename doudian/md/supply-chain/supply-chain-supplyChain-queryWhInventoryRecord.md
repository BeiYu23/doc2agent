# supplyChain.queryWhInventoryRecord

> 查询品仓库存流水

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.queryWhInventoryRecord` |
| 中文名 | 查询品仓库存流水 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/queryWhInventoryRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/7439 |
| 更新日期 | `2025-10-17` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_num` | body | mixed | 是 | 页码 | `1` |
| `page_size` | body | mixed | 是 | 单页大小 | `100` |
| `data_date_start` | body | string | 是 | 库存流水时间起始 | `2025-06-18 00:00:00` |
| `data_date_end` | body | string | 是 | 库存流水时间终止 | `2025-06-20 00:00:00` |
| `logistic_status_time_start` | body | string | 否 | 物流状态更新时间起始 | `2025-06-18 00:00:00` |
| `logistic_status_time_end` | body | string | 否 | 物流状态更新时间终止 | `2025-06-20 00:00:00` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/queryWhInventoryRecord?app_key=your_appkey_here&method=supplyChain.queryWhInventoryRecord&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `record_list` | array | 库存流水列表 | `` |
| `total` | mixed | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统内部异常（sub_code: isp.service-error:10000） | 咨询内部技术人员 |
| `20000` | 系统错误 / isp.service-error:10001（sub_code: isp.service-error:30000） | 咨询连接平台技术人员 |

## 响应示例

成功：

```json
{
  "data": {
    "record_list": [
      {
        "cargoCode": "货品code",
        "courierName": "SF",
        "deliveryTime": "2025-06-18 00:00:00",
        "erpOrderNo": "123456789",
        "erpRefNo": "123456",
        "fromLocationCode": "W0066",
        "fromLocationName": "自营仓编码",
        "fromLocationType": "2",
        "hqId": "4019383",
        "hqName": "岩禾（上海）贸易有限公司",
        "invType": "1",
        "isFinish": "1/0",
        "isGov": "1/0",
        "isSubsidy": "1/0",
        "logisticStatus": "SEND_OFF",
        "logisticStatusTime": "2025-06-18 00:00:00",
        "mpnCode": "mpnCode",
        "mpnName": "iphone16新款",
        "outerBizID": "123456",
        "packageVolumn": "10.34",
        "packageWeight": "0.482",
        "pickupTime": "2025-06-18 00:00:00",
        "qty": "10",
        "serialNumbers": "S1248972",
        "toLocationCity": "苏州市",
        "toLocationCode": "江苏省",
        "toLocationName": "收货仓库名称",
        "toLocationProvince": "江苏省",
        "toLocationType": "2",
        "totalQty": "10",
        "transactionId": "123456",
        "transactionTime": "2025-06-18 00:00:00",
        "transactionType": "1001",
        "transactionTypeName": "2C销售出库",
        "whCity": "江苏省苏州市",
        "whCode": "自营仓编码",
        "whName": "自营仓名称",
        "whType": "2C"
      }
    ],
    "total": "100"
  },
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10000",
  "sub_msg": "系统内部异常"
}
```

## 备注
