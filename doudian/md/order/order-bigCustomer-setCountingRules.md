# bigCustomer.setCountingRules

> 设置统计销量规则

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.bigCustomer.setCountingRules` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/bigCustomer/setCountingRules` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7649 |
| 更新日期 | `2025-07-31` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `counting_rules` | body | array | 否 | 规则列表（size <= 20） | `` |
| `  └ end_time` | body | mixed | 否 | 计数结束时间（秒级别时间戳） | `1752940800` |
| `  └ sku_id` | body | string | 否 | 平台SkuID | `3453363154713090` |
| `  └ start_time` | body | mixed | 否 | 计数开始时间（秒级别时间戳） | `1752076800` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/bigCustomer/setCountingRules?app_key=your_appkey_here&method=bigCustomer.setCountingRules&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
