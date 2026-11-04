# 【二方接口】直播间商品列表

> buyin.getDistributionLiveProductList — 【二方接口】直播间商品列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【二方接口】直播间商品列表 |
| 文档地址 | `/docs/doudian/permission/permission-buyin-getDistributionLiveProductList` |
| 接口 ID | `doudian.permission.buyin.getDistributionLiveProductList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/getDistributionLiveProductList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1506/6582 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 二方开放权限组（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `author_buyin_id` | body | string | 是 | 百应ID | `1345532224355` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/getDistributionLiveProductList?app_key=your_appkey_here&method=buyin.getDistributionLiveProductList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `create_time` | mixed | 直播间创建时间 | `xxxxxxxx` |
| `online_num` | mixed | 在线人数 | `100` |
| `is_rest_assured` | boolean | 是否安心购 | `false` |
| `has_kol_coupon` | boolean | 是否有主播券 | `false` |
| `is_flash_live_room` | boolean | 是否闪购直播间 | `false` |
| `product_count` | mixed | 商品总数 | `10` |
| `products` | array | 普通商品列表 | `` |
| `flash_products_count` | mixed | 闪购商品总数 | `1` |
| `flash_products` | array | 闪购商品列表 | `` |
| `room_id` | mixed | 直播间ID | `1` |
| `author_nickname` | string | 达人昵称 | `测试昵称` |
| `author_buyin_id` | mixed | 达人百应ID | `4453563322` |
| `lottery_products` | array | 福袋商品列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 256:服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 256:服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 4130:达人未开播（sub_code: isv.business-failed:4130） | 4130:达人未开播 |

## 响应示例

成功：

```json
{
  "data": {
    "author_buyin_id": "4453563322",
    "author_nickname": "测试昵称",
    "create_time": "xxxxxxxx",
    "flash_products": [
      {
        "ads_promotion_ratio": {
          "old_fans_ratio": "1",
          "share_ratio": "1"
        },
        "available_coupons": [
          {
            "apply_end_time": "xxxxxx",
            "apply_start_time": "xxxxxx",
            "coupon_type": "0",
            "discount_desc": "满20减1",
            "type_desc": "平台券",
            "use_end_time": "1",
            "use_start_time": "1",
            "valid_period": "2",
            "validity_type": "1"
          }
        ],
        "category_id": "行业类目",
        "cover": "xxxxxx",
        "first_cid": "1",
        "first_cname": "一级类目",
        "given_products": [
          {
            "cover": "xxxxxx",
            "given_skus": [
              {
                "cover": "xxxxx",
                "product_id": "112233",
                "sku_id": "223311"
              }
            ],
            "product_id": "12233",
            "product_name": "测试商品"
          }
        ],
        "is_explaining": "false",
        "list_num": "1",
        "live_room_price": "10",
        "price": "10",
        "product_id": "1111111",
        "second_cid": "2",
        "second_cname": "二级类目",
        "third_cid": "3",
        "third_cname": "三级类目",
        "title": "测试商品"
      }
    ],
    "flash_products_count": "1",
    "has_kol_coupon": "false",
    "is_flash_live_room": "false",
    "is_rest_assured": "false",
    "lottery_products": [
      {
        "lottery_activity_id": "1",
        "lottery_product_end_time": "xxxxxxx",
        "lottery_product_start_time": "xxxxxxx",
        "product_info": {
          "ads_promotion_ratio": {
            "old_fans_ratio": "1",
            "share_ratio": "1"
          },
          "available_coupons": [
            {
              "apply_end_time": "xxxxx",
              "apply_start_time": "xxxxx",
              "coupon_type": "0",
              "discount_desc": "满20减1",
              "type_desc": "平台券",
              "use_end_time": "xxxxx",
              "use_start_time": "xxxxxx",
              "valid_period": "1000",
              "validity_type": "1"
            }
          ],
          "category_id": "1",
          "cover": "xxxxxx",
          "first_cid": "1",
          "first_cname": "一级类目名称",
          "given_products": [
            {
              "cover": "xxxxxx",
              "given_skus": [
                {
                  "cover": "xxxxxx",
                  "product_id": "1122333",
                  "sku_id": "456743"
                }
              ],
              "product_id": "112233",
              "product_name": "测试商品"
            }
          ],
          "is_explaining": "false",
          "list_num": "1",
          "live_room_price": "10",
          "price": "10",
          "product_id": "1231231",
          "second_cid": "2",
          "second_cname": "二级类目名称",
          "third_cid": "3",
          "third_cname": "三级类目名称",
          "title": "测试商品"
        }
      }
    ],
    "online_num": "100",
    "product_count": "10",
    "products": [
      {
        "ads_promotion_ratio": {
          "old_fans_ratio": "1",
          "share_ratio": "1"
        },
        "available_coupons": [
          {
            "apply_end_time": "1xxxxxx",
            "apply_start_time": "1xxxxxx",
            "coupon_type": "0",
            "discount_desc": "满20减1",
            "type_desc": "平台券",
            "use_end_time": "1",
            "use_start_time": "1",
            "valid_period": "2",
            "validity_type": "1"
          }
        ],
        "category_id": "4",
        "cover": "xxxxxxx",
        "first_cid": "1",
        "first_cname": "一级类目",
        "given_products": [
          {
            "cover": "xxxxxxx",
            "given_skus": [
              {
                "cover": "xxxxxxx",
                "product_id": "1122345",
                "sku_id": "112233"
              }
            ],
            "product_id": "223145",
            "product_name": "测试商品"
          }
        ],
        "is_explaining": "false",
        "list_num": "1",
        "live_room_price": "10",
        "price": "100",
        "product_id": "112233",
        "second_cid": "2",
        "second_cname": "二级类目",
        "third_cid": "3",
        "third_cname": "三级类目",
        "title": "测试商品"
      }
    ],
    "room_id": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:256",
  "sub_msg": "256:服务打瞌睡了，请稍后再试"
}
```

## 备注
