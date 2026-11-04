# marketing.queryFinalPrice

> 查询到手价

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.marketing.marketing.queryFinalPrice` |
| 中文名 | 查询到手价 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/queryFinalPrice` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7773 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `final_price_type` | body | string | 否 | 到手价类型。lowest_final_price 最低到手价；general_final_price 普惠到手价 | `lowest_final_price` |
| `promotion_scope_type` | body | string | 否 | 优惠作用范围(商品/sku) | `sku` |
| `promotion_subject_info` | body | object | 否 | 优惠对象信息 | `` |
| `  └ promotion_subject_item_info_list` | body | array | 否 | 优惠对象单项信息列表 | `` |
| `    └ promotion_subject_id` | body | string | 否 | 优惠对象ID。商品ID_0_0_SKUID | `3763985059208626177_0_0_3516339652312834` |
| `    └ discount_rule_list` | body | array | 否 | 优惠规则列表(门槛、门槛值、优惠类型、优惠值) | `` |
| `      └ discount_threshold` | body | object | 否 | 优惠门槛 | `` |
| `        └ threshold_type` | body | mixed | 否 | 优惠门槛类型。固定传 2,2 代表满元。 | `2` |
| `        └ threshold_value` | body | mixed | 否 | 门槛值。固定传0 | `0` |
| `      └ discount_info` | body | object | 否 | 优惠信息 | `` |
| `        └ activity_price_discount` | body | object | 否 | 价格类优惠 | `` |
| `          └ discount_type` | body | mixed | 否 | 优惠方式。1: 打折; 2: 一口价; 3: 直降 | `2` |
| `          └ discount_value` | body | mixed | 否 | 优惠值 | `700` |
| `  └ start_time` | body | mixed | 否 | 优惠开始时间 | `1753332162` |
| `  └ end_time` | body | mixed | 否 | 优惠结束时间 | `1759248000` |
| `source_end` | body | mixed | 否 | 来源端。固定传 10。代表开放平台 | `10` |
| `common_ctx_info` | body | object | 否 | 上下文信息 | `` |
| `  └ source_type` | body | mixed | 否 | 来源类型 | `1` |
| `  └ operator_type` | body | mixed | 否 | 1 | `1` |
| `  └ authority_id` | body | mixed | 否 | 1 | `1` |
| `  └ isv_info` | body | object | 否 | 第三方应用信息 | `` |
| `    └ app_key` | body | mixed | 否 | isv应用id | `1` |
| `    └ app_name` | body | string | 否 | ISV应用名称 | `1` |
| `  └ shop_info` | body | object | 否 | 店铺信息 | `` |
| `    └ authority_id` | body | mixed | 否 | 店铺ID | `1` |
| `activity_code` | body | string | 否 | 玩法编码。LimitTimeTimeBuy: 限时抢购; LimitQuantityTimeBuy: 限量抢购; OrdinaryTimeBuy: 普通降价促销。 | `LimitTimeTimeBuy` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/queryFinalPrice?app_key=your_appkey_here&method=marketing.queryFinalPrice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `query_final_price_res` | object | 到手价结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:510050002） | 联系开放平台技术排查 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:510000001） | 调整参数 |

## 响应示例

成功：

```json
{
  "data": {
    "query_final_price_res": {
      "activity_code": "LimitTimeTimeBuy",
      "final_price_info": {
        "promotion_subject_final_price_info_list": [
          {
            "promotion_scope_type": "sku",
            "promotion_subject_id": "1_0_0_1",
            "sku_final_price_info": {
              "channel_id": "0",
              "channel_type": "0",
              "ext_info": {},
              "final_price_sku_type": "1",
              "price_risk_level": "redline",
              "pricing_promotion_group_list": [
                {
                  "pricing_promotion_group_type": "SINGLE_PRODUCT_PROMOTION",
                  "pricing_promotion_instance_list": [
                    {
                      "begin_time": "2025/08/05 00:00:00",
                      "discount_value": "500",
                      "end_time": "2025/08/05 00:00:00",
                      "merchant_activity_id": "ACT202409001",
                      "promotion_desc": "多单立减券：直减3",
                      "promotion_id": "PROMO20240901001",
                      "promotion_name": "9月单品直降"
                    }
                  ]
                }
              ],
              "product_id": "3633954572898306915",
              "shop_risk_discount": "80",
              "sku_final_price": "100",
              "sku_id": "3412091095817474",
              "sku_origin_price": "100",
              "sku_redline_price": "80",
              "sku_spec": "1"
            }
          }
        ]
      },
      "promotion_scope_type": "sku"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:510050002",
  "sub_msg": "系统错误"
}
```

## 备注
