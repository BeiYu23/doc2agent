# 逆向支付信息查询

> power.queryPaymentStatus — 逆向支付信息查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 逆向支付信息查询 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-queryPaymentStatus` |
| 接口 ID | `doudian.logistics.power.queryPaymentStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/queryPaymentStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1774 |
| 更新日期 | `2022-12-26` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 订单号 | `LBF123` |
| `biz_type` | body | string | 否 | 业务类型 | `ReversePickUp` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/queryPaymentStatus?app_key=your_appkey_here&method=power.queryPaymentStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `payment_status` | string | 1--已支付 0--核重未支付 2--未核重 | `1` |
| `payment_fee` | number | 用户支付金额（分） | `1` |
| `insurance_claim_fee` | number | 应理赔金额（分）= 激励金额 + 保险理赔金额 | `1` |
| `encourage_fee` | number | 激励金额（分） | `1` |
| `platform_allowance` | number | 平台补贴金额(分) | `1` |
| `insure_claim_fee` | number | 保险理赔金额(分) | `1` |
| `operation_time` | string | 状态对应的操作时间 | `2022-09-06 10:00:00` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000:不存在对应的取件信息（sub_code: isv.business-failed:10000） | 输入的订单不存在，不可重试 |

## 响应示例

成功：

```json
{
  "data": {
    "encourage_fee": "1",
    "insurance_claim_fee": "1",
    "insure_claim_fee": "1",
    "operation_time": "2022-09-06 10:00:00",
    "payment_fee": "1",
    "payment_status": "1",
    "platform_allowance": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "10000:不存在对应的取件信息"
}
```

## 备注
