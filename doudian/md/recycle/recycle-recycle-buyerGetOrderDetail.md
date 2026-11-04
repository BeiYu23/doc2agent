# recycle.buyerGetOrderDetail

> 获得订单详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.recycle.recycle.buyerGetOrderDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/buyerGetOrderDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/915 |
| 更新日期 | `2023-04-11` |

## 接口说明

- 文档书: 回收寄卖API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `clue_order_id` | body | string | 是 | 线索单ID | `3456787654` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/buyerGetOrderDetail?app_key=your_appkey_here&method=recycle.buyerGetOrderDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `detail` | object | 详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "detail": {
      "app_id": "\"12345\"",
      "brand_name": "MCM",
      "category_name": "腕表",
      "close_time": "\"12311232131\"",
      "clue_id": "\"1232131\"",
      "clue_order_id": "\"123213213\"",
      "clue_order_status": "4",
      "consignment_commission": "200",
      "consignment_fee": "200",
      "consignment_period": "7200",
      "consignment_price": "200",
      "create_time": "\"12311232131\"",
      "encrypt_shop_address": "……",
      "encrypt_shop_name": "……",
      "encrypt_shop_phone": "……",
      "encrypt_user_address": "……",
      "encrypt_user_name": "……",
      "encrypt_user_phone": "……",
      "knockdown_time": "1617355413",
      "knockdown_type": "6",
      "logistics_code": "SF123123423",
      "model_name": "全部型号",
      "notes": "“”",
      "picture": "……",
      "price_confirm_time": "1617355413",
      "price_create_time": "1617355413",
      "product_name": "\"sda\"",
      "product_pic": "xx",
      "proof": "没有",
      "purchase_way": "1",
      "recycle_commission": "200",
      "recycle_price": "200",
      "reverse_logistics_code": "SF12321312312312",
      "sent_time": "1617355413",
      "sent_way": "1",
      "series_name": "备选系列",
      "shop_consignment_time": "1617355413",
      "sku": "xx",
      "source_key": "72834792",
      "termination_reason": "拒绝估价",
      "termination_side": "系统",
      "termination_time": "1617355413",
      "theme_type": "来源",
      "trade_type": "6",
      "update_time": "\"12311232131\"",
      "vintage": "9成新"
    }
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
