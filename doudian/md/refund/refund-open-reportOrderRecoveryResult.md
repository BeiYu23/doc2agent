# 上报挽单执行结果

> open.reportOrderRecoveryResult — 上报挽单执行结果

| 元信息 | 值 |
| --- | --- |
| 中文名 | 上报挽单执行结果 |
| 文档地址 | `/docs/doudian/refund/refund-open-reportOrderRecoveryResult` |
| 接口 ID | `doudian.refund.open.reportOrderRecoveryResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/reportOrderRecoveryResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/8095 |
| 更新日期 | `2026-02-13` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `is_reach_consumer` | body | boolean | 是 | 是否触达消费者 | `true` |
| `reach_failed_reason` | body | string | 否 | 未触达原因 | `外呼未接通` |
| `recover_result` | body | string | 否 | 挽单结果，枚举如下：success 挽单成功; no_reach_consumer 未能触达消费者；consumer_refuse 已触达但消费者拒绝；merchant_following 商家跟进中；merchant_abandon_recover 商家放弃挽单 挽单失败原因 | `success` |
| `recover_failed_reason` | body | string | 否 | 挽单失败原因 | `消费者认为补偿金额较少，拒绝挽单` |
| `outbound_id` | body | array | 否 | 外呼ID | `["123"]` |
| `recover_trace_id` | body | string | 是 | 挽单ID | `123456` |
| `message_id` | body | array | 否 | 短信ID | `["123"]` |
| `conversation_id` | body | array | 否 | 会话ID | `["123"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/reportOrderRecoveryResult?app_key=your_appkey_here&method=open.reportOrderRecoveryResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / recoverTraceID不合法（sub_code: isv.parameter-invalid:10010） | 请使用/open/getOrderRecoveryRecommendation接口返回的recoverTraceID |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:10010",
  "sub_msg": "recoverTraceID不合法"
}
```

## 备注
