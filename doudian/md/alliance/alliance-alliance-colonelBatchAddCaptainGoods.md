# alliance.colonelBatchAddCaptainGoods

> 批量加商品到指定活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.alliance.colonelBatchAddCaptainGoods` |
| 中文名 | 批量加商品到指定活动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/colonelBatchAddCaptainGoods` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/8228 |
| 更新日期 | `2026-06-09` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `items` | body | array | 是 | 批量报名记录, 每个元素是单商品报名记录，商品不能重复，重复的只取第一个 | `` |
| `  └ product_id` | body | string | 是 | 商品id | `1235123412` |
| `  └ origin_activity_id` | body | string | 是 | - 如果是团长投放商品    - 如果原始团是招商活动，传原始团长活动id    - 如果原始团是托管商品，传0 - 如果是商家投放商品，传-1 | `123412` |
| `  └ activity_ids` | body | string | 是 | 报名的团长活动列表，逗号分割（限制最多3个） | `623462,1235125` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getUserOrderList?app_key=your_appkey_here&method=order.getUserOrderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `BaseResponse` | object | 报名结果 | `` |
| `fail_item` | array | 添加失败的记录（key：商品，value：<活动：失败原因>） | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "0",
    "shop_order_list": [
      {
        "create_time": "1617355413",
        "order_id": "4781320682406083640",
        "order_status": "3",
        "pay_amount": "500",
        "sku_order_list": [
          {
            "sku_info": {
              "product_id": "3473196049974326153",
              "product_name": "衣服",
              "sku_id": "3254535"
            }
          }
        ]
      }
    ],
    "size": "20",
    "total": "1000"
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
