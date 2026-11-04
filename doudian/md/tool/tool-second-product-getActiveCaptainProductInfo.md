# 【二方接口】查询生效的团长商品信息

> second.product.getActiveCaptainProductInfo — 【二方接口】查询生效的团长商品信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【二方接口】查询生效的团长商品信息 |
| 文档地址 | `/docs/doudian/tool/tool-second-product-getActiveCaptainProductInfo` |
| 接口 ID | `doudian.tool.second.product.getActiveCaptainProductInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/getActiveCaptainProductInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7606 |
| 更新日期 | `2025-07-17` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trusteeship_product_reqs` | body | array | 否 | 查询是否托管中的商品活动信息 | `` |
| `  └ product_id` | body | mixed | 否 | 1 | `1` |
| `  └ captain_id` | body | mixed | 否 | 为空则不限团长 | `1` |
| `trusteeship_search_type` | body | mixed | 否 | trusteeship_product_reqs托管查询类型，默认为一批商品id | `1` |
| `need_promote_time` | body | boolean | 否 | 1 | `1` |
| `need_promote_url` | body | boolean | 否 | 1 | `1` |
| `activity_product_reqs` | body | array | 否 | 查询是否活动中的商品活动信息 | `` |
| `  └ product_id` | body | mixed | 否 | 1 | `1` |
| `  └ activity_id` | body | mixed | 否 | 为空则不限制活动 | `1` |
| `  └ captain_id` | body | mixed | 否 | 为空则不限团长 | `1` |
| `activity_search_type` | body | mixed | 否 | activity_product_reqs活动查询类型，默认为一批商品id | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.getActiveCaptainProductInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_product_infos` | array | 商品活动查询结果 | `` |
| `trusteeship_product_infos` | array | 商品托管查询结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_product_infos": [
      {
        "activity_id": "1",
        "activity_name": "1",
        "captain_avatar": "1",
        "captain_id": "1",
        "captain_name": "1",
        "commission_rate": "1",
        "origin_activity_id": "1",
        "origin_instituion_name": "1",
        "origin_institution_id": "1",
        "product_id": "1",
        "product_img": "1",
        "product_name": "1",
        "promote_end_time": "1",
        "promote_start_time": "1",
        "promote_url": "1",
        "promotion_id": "1",
        "search_result": "1",
        "service_rate": "1",
        "shop_id": "1",
        "shop_name": "1"
      }
    ],
    "trusteeship_product_infos": [
      {
        "captain_avatar": "1",
        "captain_buyin_id": "1",
        "captain_id": "1",
        "captain_name": "1",
        "commission_rate": "1",
        "product_id": "1",
        "product_img": "1",
        "product_name": "1",
        "promote_url": "1",
        "promotion_id": "1",
        "search_result": "1",
        "service_rate": "1",
        "shop_id": "1",
        "shop_name": "1",
        "trusteeship_end_time": "1",
        "trusteeship_start_time": "1"
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
