# AI挽单回调

> second.volcengineFeedbackOrderRetention — AI挽单回调接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | AI挽单回调 |
| 文档地址 | `/docs/doudian/refund/refund-second-volcengineFeedbackOrderRetention` |
| 接口 ID | `doudian.refund.second.volcengineFeedbackOrderRetention` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/volcengineFeedbackOrderRetention` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/8136 |
| 更新日期 | `2026-03-12` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_amount` | body | mixed | 否 | 订单挽回的金额，单位为分，如19000。如果status=success，则order_amount和order_retention_cost必填。 | `19000` |
| `failed_reason` | body | string | 否 | 挽回失败原因，如：外呼未接通、客户买错了等 | `外呼未接通` |
| `shop_order_id` | body | string | 是 | 必填, String, 订单号 | `123456789012345` |
| `status` | body | string | 否 | 挽回状态，success/fail。如果is_outbound=1，则status和call_status必填。 | `success` |
| `is_outbound` | body | string | 是 | 必填，是否进行外呼，0: 否；1: 是 | `1` |
| `order_retention_cost` | body | mixed | 否 | 挽单的成本，单位为分，口径需要和服务商保持一致，比如：外呼成本。如果status=success，则order_amount和order_retention_cost必填。 | `1000` |
| `call_status` | body | string | 否 | 接通状态，answered/unanswered。如果is_outbound=1，则status和call_status必填 | `answered` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/volcengineFeedbackOrderRetention?app_key=your_appkey_here&method=second.volcengineFeedbackOrderRetention&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数不对，请检查（sub_code: isv.parameter-invalid:40001） | 缺少必要的参数 |
| `20000` | 系统错误 / 业务处理失败（sub_code: isp.service-error:50000） | 请反馈平台开发 |

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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "参数不对，请检查"
}
```

## 备注
