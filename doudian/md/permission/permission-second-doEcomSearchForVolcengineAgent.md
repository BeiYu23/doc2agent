# 电商搜索for 火山联网引擎

> second.doEcomSearchForVolcengineAgent — 电商搜索for 火山联网引擎

| 元信息 | 值 |
| --- | --- |
| 中文名 | 电商搜索for 火山联网引擎 |
| 文档地址 | `/docs/doudian/permission/permission-second-doEcomSearchForVolcengineAgent` |
| 接口 ID | `doudian.permission.second.doEcomSearchForVolcengineAgent` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/doEcomSearchForVolcengineAgent` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1506/7861 |
| 更新日期 | `2026-03-05` |

## 接口说明

- 文档书: 二方开放权限组（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `queries` | body | array | 否 | 请求query | `["冰箱"]` |
| `count_per_query` | body | mixed | 否 | 请求数量 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/doEcomSearchForVolcengineAgent?app_key=your_appkey_here&method=second.doEcomSearchForVolcengineAgent&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ecom_docs` | array | 电商商品信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "ecom_docs": [
      {
        "brand_info": {
          "brand_name": "\"a\""
        },
        "comment_info": {
          "comment_stat": {
            "photo_count": "123",
            "photo_video_count": "123",
            "total": "123",
            "video_count": "123"
          }
        },
        "doc_id": "1",
        "ecom_ai_gc": {
          "ecom_ai_summary": {
            "reasons": [
              {
                "content": "\"a\"",
                "title": "\"a\""
              }
            ]
          },
          "ecom_ai_tag": "[\"a\"]"
        },
        "ecom_visual_info": {
          "image_uri": "\"a\"",
          "image_url": "\"a\"",
          "short_title": "\"a\"",
          "white_cover_uri": "\"a\"",
          "white_cover_url": "\"a\""
        },
        "product_info": {
          "ai_detail_summary": [
            {
              "detail_sell_info": "\"a\"",
              "structured_sell_points": "\"a\"",
              "summary": "\"a\""
            }
          ],
          "category_info": {
            "first_category": {
              "category_id": "123",
              "category_name": "\"a\""
            },
            "fourth_category": {
              "category_id": "123",
              "category_name": "\"a\""
            },
            "kg_category": {
              "cid": "123",
              "first_cid": "123",
              "first_name": "\"a\"",
              "fourth_cid": "123",
              "fourth_name": "\"a\"",
              "level": "123",
              "level_name": "\"a\"",
              "name": "\"a\"",
              "score": "0.0",
              "second_cid": "123",
              "second_name": "\"a\"",
              "third_cid": "123",
              "third_name": "\"a\"",
              "version": "123"
            },
            "leaf_category_id": "123",
            "second_category": {
              "category_id": "123",
              "category_name": "\"a\""
            },
            "third_category": {
              "category_id": "123",
              "category_name": "\"a\""
            }
          },
          "ecom_properties": [
            {
              "property_name": "\"a\"",
              "property_values": "[\"a\"]"
            }
          ],
          "price": "1??",
          "product_id": "123",
          "product_name": "\"a\""
        },
        "shop_info": {
          "shop_id": "1",
          "shop_level": "1",
          "shop_name": "\"a\"",
          "shop_type": "1"
        }
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
