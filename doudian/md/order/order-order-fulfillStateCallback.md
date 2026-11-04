# order.fulfillStateCallback

> 大客户履约节点回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.fulfillStateCallback` |
| 中文名 | 大客户履约节点回传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/fulfillStateCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7646 |
| 更新日期 | `2025-07-30` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 店铺单号 | `111` |
| `sku_order_id_list` | body | array | 是 | sku单idList | `["111","222"]` |
| `state` | body | mixed | 是 | 状态:1 = 备货 | `1` |
| `state_time` | body | mixed | 是 | 时间戳 | `1752201052` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/fulfillStateCallback?app_key=your_appkey_here&method=order.fulfillStateCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
