# buyin.getAllianceProductDetails

> 【二方接口】联盟商品详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.permission.buyin.getAllianceProductDetails` |
| 中文名 | 【二方接口】联盟商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/getAllianceProductDetails` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1506/6583 |
| 更新日期 | `2024-05-30` |

## 接口说明

- 文档书: 二方开放权限组（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `author_type` | body | mixed | 是 | 0: 机构，1：达人 | `0` |
| `author_id` | body | string | 是 | author_type = 0 表示机构ID，author_type = 1 表示 达人百应ID | `0` |
| `product_ids` | body | array | 是 | 商品id列表 | `[12345]` |
| `with_share_status` | body | boolean | 否 | 获取商品分销状态 | `false` |
| `with_brand_info` | body | boolean | 否 | 获取品牌信息 | `false` |
| `biz_app_key` | body | string | 否 | app_key | `xxxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/getAllianceProductDetails?app_key=your_appkey_here&method=buyin.getAllianceProductDetails&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 商品总数 | `10` |
| `products` | array | 商品信息 | `` |

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
        "activity_id": "1",
        "available_coupons": [
          {
            "apply_end_time": "xxxxx",
            "apply_start_time": "xxxxx",
            "coupon_type": "1",
            "discount_desc": "满20减1",
            "type_desc": "平台券",
            "use_end_time": "xxxxx",
            "use_start_time": "xxxxx",
            "valid_period": "1",
            "validity_type": "1"
          }
        ],
        "brand": {
          "brand_id": "12222",
          "brand_name_cn": "测试",
          "brand_name_en": "test"
        },
        "category_id": "xxxxxxx",
        "category_name": "xxxxx",
        "comment_num": "1",
        "comment_score": "5",
        "commission_type": "1",
        "cos_fee": "10",
        "cos_ratio": "1",
        "coupon_price": "10",
        "cover": "xxxxxx",
        "daily_statistics": [
          {
            "date": "xxxxxx",
            "kol_num": "1",
            "order_num": "1",
            "order_num_v2": "xxxxx",
            "view_num": "1"
          }
        ],
        "detail_brief": {
          "component_info": [
            {
              "image": {
                "height": "100",
                "pic_url": "xxxx",
                "width": "100"
              }
            }
          ],
          "success": "false"
        },
        "detail_url": "xxxxxxx",
        "first_cid": "1",
        "has_sxt": "false",
        "imgs": "xxxxxxx",
        "in_stock": "false",
        "ins_activity_param": "xxxxx",
        "is_assured": "false",
        "is_channel_product": "false",
        "kol_cos_fee": "100",
        "kol_cos_ratio": "1",
        "kol_num": "1",
        "limit_min_sale": "false",
        "logistics_info": "xxxxx",
        "mix_activity_id": "xxxx",
        "order_num": "1",
        "order_num_v2": "xxxxx",
        "post_free": "false",
        "presell_type": "1",
        "price": "商品价格",
        "product_id": "12233",
        "promotable": "false",
        "reason": "xxxxx",
        "sales": "1000",
        "sales_v2": "xxxxx",
        "second_cid": "2",
        "sharable": "false",
        "shop_id": "4455674",
        "shop_name": "测试店铺",
        "shop_total_score": {
          "logistics_score": {
            "level": "1",
            "score": "score",
            "text": "text"
          },
          "product_score": {
            "level": "1",
            "score": "score",
            "text": "text"
          },
          "service_score": {
            "level": "1",
            "score": "score",
            "text": "text"
          },
          "shop_score": {
            "level": "1",
            "score": "score",
            "text": "text"
          }
        },
        "status": "1",
        "tags": {
          "has_shop_brand_tag": "false",
          "success": "false"
        },
        "third_cid": "3",
        "title": "测试商品",
        "view_num": "1"
      }
    ],
    "total": "10"
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
