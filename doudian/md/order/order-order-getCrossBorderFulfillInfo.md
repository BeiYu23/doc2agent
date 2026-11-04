# order.getCrossBorderFulfillInfo

> 获取跨境承运单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.getCrossBorderFulfillInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getCrossBorderFulfillInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1837 |
| 更新日期 | `2021-06-09` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 主订单号(不带A) | `4795451507070928840` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getCrossBorderFulfillInfo?app_key=your_appkey_here&method=order.getCrossBorderFulfillInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_order_id` | string | 主订单号 | `4790307922954771917` |
| `company` | string | 物流公司名称 | `顺丰` |
| `company_code` | string | 物流公司Code | `shunfeng` |
| `sku_order_ids` | array | 商品单id列表 | `["4790307922954771917"]` |
| `logistics_code` | string | 物流单号 | `SF12345` |
| `way_bill_url` | string | 电子面单链接 | `https://sf6-ttcdn-tos.pstatp.com/obj/temai/xxx` |
| `mark` | string | 大头笔 | `1` |
| `product_num` | number | 商品件数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "company": "顺丰",
    "company_code": "shunfeng",
    "logistics_code": "SF12345",
    "mark": "1",
    "product_num": "1",
    "shop_order_id": "4790307922954771917",
    "sku_order_ids": "[\"4790307922954771917\"]",
    "way_bill_url": "https://sf6-ttcdn-tos.pstatp.com/obj/temai/xxx"
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
