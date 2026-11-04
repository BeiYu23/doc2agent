# 上报预发货订单

> order.reportPreDeliveryOrder — 上报预发货订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 上报预发货订单 |
| 文档地址 | `/docs/doudian/logistics/logistics-order-reportPreDeliveryOrder` |
| 接口 ID | `doudian.logistics.order.reportPreDeliveryOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/reportPreDeliveryOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/8213 |
| 更新日期 | `2026-04-22` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 否 | 订单ID | `112233` |
| `extra` | body | string | 否 | 扩展信息 | `{}` |
| `daily_audit_times` | body | mixed | 否 | 商家每日审单次数 | `3` |
| `ware_mode` | body | string | 否 | 仓模式, 枚举值：self 自有仓 cloud 云仓 hybrid 混合仓 | `cloud` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/reportPreDeliveryOrder?app_key=your_appkey_here&method=order.reportPreDeliveryOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否上报成功 | `false` |
| `reason` | string | 原因说明 | `订单中包含预售商品` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "reason": "订单中包含预售商品",
    "success": "false"
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
