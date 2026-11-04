# 合约机分期贴息

> order.withhold — 合约机分期贴息，如果消费者违约，运营商通过这个接口发起代扣。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 合约机分期贴息 |
| 文档地址 | `/docs/doudian/virtual/virtual-order-withhold` |
| 接口 ID | `doudian.virtual.order.withhold` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/withhold` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/6551 |
| 更新日期 | `2024-07-05` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 是 | 本次请求的唯一id，无业务含义 | `12378991879` |
| `order_id` | body | string | 是 | 消费者违约的合约机订单id | `69908980071231` |
| `amount` | body | mixed | 是 | 代扣金额，单位：分 | `18000` |
| `reason` | body | string | 是 | 清晰说明本次发起代扣的原因 | `用户未满24个月，中途离网` |
| `withhold_shop_id` | body | string | 是 | 代扣收款店铺Id | `77977` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/withhold?app_key=your_appkey_here&method=order.withhold&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:30012） | 检查参数传递是否合法 |
| `20000` | 系统错误 / 系统内部异常（sub_code: isp.service-error:20004） | 重试 |
| `20000` | 系统错误 / 合约机订单Id非法（sub_code: isp.service-error:30013） | 检查订单id是否合法 |
| `50002` | 业务处理失败 / 不是合约机订单（sub_code: isv.business-failed:30005） | 检查订单id是否合法 |
| `50002` | 业务处理失败 / 订单代扣进行中或已成功（sub_code: isv.business-failed:30015） | 订单代扣进行中或已成功 |
| `60000` | 触发限流，请稍后重试 / 同一笔订单，40min内最多只能发起一次代扣（sub_code: isp.traffic-limited:30014） | 同一笔订单，40min内最多只能发起一次代扣 |
| `50002` | 业务处理失败 / 系统内部错误（sub_code: isv.business-failed:30016） | 系统内部错误，需要重试 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:30012",
  "sub_msg": "缺少必要参数"
}
```

## 备注
