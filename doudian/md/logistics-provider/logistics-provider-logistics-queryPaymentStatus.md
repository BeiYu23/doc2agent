# logistics.queryPaymentStatus

> 支付结果查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.queryPaymentStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/queryPaymentStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2500 |
| 更新日期 | `2022-09-14` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orderId` | body | string | 是 | 订单号 | `4732078173688851864` |
| `bizType` | body | string | 否 | ReversePickUp -- 上门取件（默认值，不传为上门取件业务） CabinetPickUp -- 快递柜 | `ReversePickUp` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/queryPaymentStatus?app_key=your_appkey_here&method=logistics.queryPaymentStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `paymentStatus` | string | 1--已支付 0--核重未支付 2--未核重 | `1` |
| `paymentFee` | number | 用户支付金额 | `11` |
| `insuranceClaimFee` | number | 应理赔金额=激励金 + 保险理赔金额 | `11` |
| `encourageFee` | number | 激励金 | `11` |
| `platformAllowance` | number | 平台补贴金额 | `11` |
| `insureClaimFee` | number | 保险理赔金额 | `11` |
| `operationTime` | string | 操作时间 | `2021-01-19 10:00:00` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 换个参数 |

## 响应示例

成功：

```json
{
  "data": {
    "encourageFee": "11",
    "insuranceClaimFee": "11",
    "insureClaimFee": "11",
    "operationTime": "2021-01-19 10:00:00",
    "paymentFee": "11",
    "paymentStatus": "1",
    "platformAllowance": "11"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "参数错误"
}
```

## 备注
