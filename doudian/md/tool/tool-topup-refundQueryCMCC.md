# topup.refundQueryCMCC

> 中国移动退款订单状态查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.topup.refundQueryCMCC` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/refundQueryCMCC` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7622 |
| 更新日期 | `2025-07-22` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `requestId` | body | string | 否 | 抖音电商订单号 | `1` |
| `merchantId` | body | string | 否 | 商户ID | `1` |
| `type` | body | string | 否 | 接口类型 | `1` |
| `version` | body | string | 否 | 接口版本 | `1` |
| `orderNo` | body | string | 否 | 金科侧订单号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/refundQueryCMCC?app_key=your_appkey_here&method=topup.refundQueryCMCC&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status` | string | RS-成功，RF-RU-处理中，查询成功时返回 | `1` |
| `result` | string | S-成功，F-失败 | `1` |
| `orderNo` | string | 金科订单号 | `1` |
| `refundAmount` | mixed | 退款金额（单位：分），查询成功时返回 | `1` |
| `refundDate` | string | 退款日期，格式：yyyyMMdd，查询成功时返回 | `1` |
| `refundTime` | string | 退款时间，格式：yyyyMMddHHmmss，查询成功时返回 | `1` |
| `errorCode` | string | 返回码 | `1` |
| `errorMessage` | string | 错误描述 | `1` |
| `requestId` | string | 抖音电商订单号 | `1` |
| `failReason` | string | 失败原因，退款失败时返回 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "errorCode": "1",
    "errorMessage": "1",
    "failReason": "1",
    "orderNo": "1",
    "refundAmount": "1",
    "refundDate": "1",
    "refundTime": "1",
    "requestId": "1",
    "result": "1",
    "status": "1"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
