# second.product.batchGetProduct2C

> 【二方接口】批量获取商品信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.product.batchGetProduct2C` |
| 中文名 | 【二方接口】批量获取商品信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/batchGetProduct2C` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6950 |
| 更新日期 | `2024-10-18` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `option` | body | object | 否 | 参数 | `` |
| `  └ need_sku` | body | boolean | 否 | 是否需要sku | `true` |
| `  └ need_sell_num` | body | boolean | 否 | 是否需要销量 | `true` |
| `  └ need_tag` | body | boolean | 否 | 是否需要tag | `true` |
| `  └ need_product_pic` | body | boolean | 否 | 是否需要列表图 | `true` |
| `param` | body | array | 是 | 参数 | `` |
| `  └ product_id` | body | mixed | 是 | 商品ID 必填 | `1` |
| `  └ sku_ids` | body | array | 否 | 商品 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.batchGetProduct2C&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `products` | array | 成功查询出的product | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "products": [
      {
        "brand_id": "1",
        "category_id": "1",
        "check_status": "1",
        "description": "1",
        "main_img": {
          "Height": "1",
          "picType": "1",
          "pic_id": "1",
          "trackInfo": "1",
          "url": "1",
          "width": "11"
        },
        "mobile": "1",
        "name": "1",
        "new_category": {
          "first_c_name": "1",
          "first_cid": "1",
          "fourth_c_name": "1",
          "fourth_cid": "1",
          "second_c_name": "1",
          "second_cid": "1",
          "third_c_name": "1",
          "third_cid": "1"
        },
        "original_price": "1",
        "product_id": "1",
        "sale_price": "1",
        "sell_num": "1",
        "shop_id": "1",
        "skus": [
          {
            "channel_main_sku_id": "1",
            "code": "1",
            "id": "1",
            "out_sku_id": "1",
            "outer_sku_id": "1",
            "presell_delay": "1",
            "presell_type": "1",
            "price": "1",
            "product_id": "1",
            "sale_property_values": [
              {
                "pair_id": "1",
                "pic": {
                  "height": "1",
                  "url": "1",
                  "width": "1"
                },
                "property": {
                  "property_id": "1",
                  "property_name": "1"
                },
                "seq": "1"
              }
            ],
            "sku_biz": "1",
            "spec_id": "1",
            "supplier_id": "1",
            "type": "1"
          }
        ],
        "spec_id": "1",
        "status": "1",
        "store_id": "1",
        "tag_list": "1"
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
