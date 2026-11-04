# 查询营销玩法圈品信息

> marketing.queryActivityProduct — 查询营销玩法圈品信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询营销玩法圈品信息 |
| 文档地址 | `/docs/doudian/marketing/marketing-marketing-queryActivityProduct` |
| 接口 ID | `doudian.marketing.marketing.queryActivityProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/queryActivityProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7778 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `query_option` | body | object | 否 | 活动查询选项 | `` |
| `  └ need_activity_detail` | body | boolean | 否 | 是否查询活动明细 | `true` |
| `  └ need_product_info` | body | boolean | 否 | 是否需要商品信息。 | `true` |
| `  └ need_page_query_product` | body | boolean | 否 | 是否需要按商品进行分页查询 | `true` |
| `  └ product_page` | body | mixed | 否 | 当前是第几页，从1开始 | `1` |
| `  └ product_page_size` | body | mixed | 否 | 每页返回多少商品 | `10` |
| `  └ need_promotion_limit` | body | boolean | 否 | 是否需要活动限用信息 | `true` |
| `common_ctx_info` | body | object | 否 | 1 | `` |
| `  └ operator_type` | body | mixed | 否 | 1 | `1` |
| `  └ authority_id` | body | mixed | 否 | 1 | `1` |
| `  └ shop_info` | body | object | 否 | 1 | `` |
| `    └ authority_id` | body | mixed | 否 | 1 | `1` |
| `  └ isv_info` | body | object | 否 | 第三方应用信息 | `` |
| `    └ app_key` | body | mixed | 否 | isv应用id | `1` |
| `    └ app_name` | body | string | 否 | ISV应用名称 | `1` |
| `  └ source_type` | body | mixed | 否 | 1 | `1` |
| `activity_id` | body | mixed | 否 | 活动ID | `7546141092304273698` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/queryActivityProduct?app_key=your_appkey_here&method=marketing.queryActivityProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity` | object | 玩法数据 | `` |
| `total_product_num` | mixed | 活动圈的商品总数量 | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -100001:按商品分页必须打开查询子活动详情开关（sub_code: isv.business-failed:-100001） | 修改入参 |

## 响应示例

成功：

```json
{
  "data": {
    "activity": {
      "activity_common_config": {
        "renew_config": {
          "renew_status": "1",
          "renew_switch": "true"
        },
        "rule_scope": {
          "rule_scope_type": "3"
        },
        "source_page": "52",
        "source_type": "10"
      },
      "activity_extra_info": {
        "time_buy_extra": {
          "order_expire_time": "1800",
          "product_total_count": "12",
          "renew_switch_on": "true",
          "set_promotion_limit": "true"
        }
      },
      "activity_info": {
        "activity_code": "LimitTimeTimeBuy",
        "activity_id": "7543564853458698506",
        "activity_name": "限时抢购 20250806 15:45",
        "create_time": "1749744000",
        "creator_id": "77977",
        "creator_type": "1",
        "status": "1",
        "update_time": "1749744000"
      },
      "activity_operation": {
        "has_failed_operation": "false",
        "has_risk_block": "false"
      },
      "activity_products": [
        {
          "activity_rule": {
            "campaign_resource": {
              "campaign_limit": {
                "promotion_limit": {
                  "left_limit_num": "1",
                  "limit_num": "2",
                  "limit_type": "14"
                }
              }
            }
          },
          "activity_sku_list": [
            {
              "activity_rule": {
                "campaign_resource": {
                  "user_limit": {
                    "trade_limit": {
                      "trade_limit_type": "1",
                      "user_limit": "2"
                    }
                  }
                },
                "discount_rule": [
                  {
                    "discount_info": {
                      "activity_price_discount": {
                        "discount_type": "1",
                        "discount_value": "20"
                      }
                    }
                  }
                ]
              },
              "sku_info": {
                "activity_fixed_price": "800",
                "cover": "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/tYUaupaL_m_349ba525902bbcf2174847edd3347b4e_sx_116617_www1010-1010",
                "origin_price": "800",
                "sku_id": "1774276049399816",
                "specification": "浅灰色/XXXS"
              }
            }
          ],
          "product_info": {
            "channel_id": "0",
            "channel_type": "0",
            "cover": "1",
            "is_kol_exclusive": "false",
            "max_price": "1200",
            "min_price": "1200",
            "name": "多sku半身裙01-20 21:47",
            "product_id": "3633954572898306915"
          }
        }
      ],
      "activity_rule": {
        "campaign_resource": {
          "campaign_limit": {
            "promotion_limit": {
              "limit_type": "14"
            }
          },
          "user_limit": {
            "trade_limit": {
              "trade_limit_type": "1"
            }
          }
        },
        "discount_rule": [
          {
            "discount_info": {
              "activity_price_discount": {
                "discount_type": "2"
              }
            }
          }
        ],
        "scene_rule": {
          "need_live": "false"
        }
      },
      "activity_time": {
        "end_time": "1749744000",
        "start_time": "1749744000",
        "warm_up_time": "1749744000"
      }
    },
    "total_product_num": "2"
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
  "sub_code": "isv.business-failed:-100001",
  "sub_msg": "-100001:按商品分页必须打开查询子活动详情开关"
}
```

## 备注
