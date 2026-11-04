# instantShopping.product.getSkuStockNum

> 查询sku库存信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-stock.instantShopping.product.getSkuStockNum` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1594/7826 |
| 更新日期 | `2025-10-29` |

## 接口说明

- 文档书: 库存管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `skus` | body | array | 是 | 需要查询的SKU列表 | `` |
| `  └ sku_id` | body | number | 是 | skuID | `3541184826617602` |
| `  └ product_id` | body | number | 是 | 商品ID | `3771614125814317781` |
| `  └ sku_type` | body | number | 是 | sku类型, 0-普通库存，1-区域库存，10-普通+阶梯 | `0` |
| `shop_channel_type_scene` | body | number | 否 | 0-专享+共享， 1-共享，2-专享，默认为0 | `0` |
| `show_loss` | body | boolean | 否 | 盘亏展示， true时会返回负值的库存 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/newCreateOrder?app_key=your_appkey_here&method=logistics.newCreateOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sku_stock_detail` | string | 返回结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "ebill_infos": [
      {
        "company": "zhongtong",
        "extra_resp": "1",
        "hint_msg": "您传入的收件地址与订单不一致，已采用平台订单地址完成取号",
        "order_channel": "c",
        "order_id": "202011809",
        "pack_id": "1",
        "package_center_code": "1",
        "package_center_name": "1",
        "shipping_code": "34343",
        "short_address_code": "1",
        "short_address_name": "1",
        "sort_code": "400-W00 000",
        "sub_waybill_codes": "13,434,556",
        "track_no": "202011809"
      }
    ],
    "err_infos": [
      {
        "err_code": "10701",
        "err_msg": "电子面单库存不足",
        "order_channel": "2",
        "order_id": "1",
        "pack_id": "1"
      }
    ]
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
