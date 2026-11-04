# 支付成功状态推进

> supplyCenter.order.pay — 支付成功状态推进

| 元信息 | 值 |
| --- | --- |
| 中文名 | 支付成功状态推进 |
| 文档地址 | `/docs/doudian/selection/selection-supplyCenter-order-pay` |
| 接口 ID | `doudian.selection.supplyCenter.order.pay` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/order/pay` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5323 |
| 更新日期 | `2023-11-10` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pur_order_id` | body | string | 是 | 精选货源订单号 | `12345` |
| `pay_amount` | body | number | 是 | 支付金额数据 | `12` |
| `post_amount` | body | number | 是 | 邮费 | `13` |
| `sku_order_pay_infos` | body | array | 是 | 子订单支付信息 | `` |
| `  └ pur_sku_order_id` | body | string | 是 | 子订单号 | `1234` |
| `  └ pay_amount` | body | number | 是 | 子订单支付信息 | `11` |
| `pay_time` | body | number | 是 | 秒级时间戳 | `1698146585` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.order.pay&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
