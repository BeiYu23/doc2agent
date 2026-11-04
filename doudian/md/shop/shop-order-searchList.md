# order.searchList

> 订单列表查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.order.searchList` |
| 中文名 | 订单列表查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/searchList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2086 |
| 更新日期 | `2022-08-08` |

## 接口说明

- 文档书: 店铺API（版本 V23.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product` | body | string | 否 | 商品，number型代表商品ID，其它代表商品名称 | `3473196049974326153` |
| `b_type` | body | number | 否 | 【下单端】 0、站外   1、火山   2、抖音   3、头条   4、西瓜   5、微信   6、值点app  7、头条lite   8、懂车帝  9、皮皮虾   11、抖音极速版   12、TikTok   13、musically   14、穿山甲   15、火山极速版   16、服务市场   26、番茄小说   27、UG教育营销电商平台   28、Jumanji   29、电商SDK | `2` |
| `after_sale_status_desc` | body | string | 否 | 售后状态：all-全部，in_aftersale-售后中，refund-退款中，refund_success-退款成功，refund_fail-退款失败，exchange_success-换货成功 aftersale_close-售后关闭 | `refund_success` |
| `tracking_no` | body | string | 否 | 物流单号 | `435435` |
| `presell_type` | body | number | 否 | 预售类型：1 全款预售 | `1` |
| `order_type` | body | number | 否 | 【订单类型】 0、普通订单 2、虚拟商品订单 4、电子券（poi核销） 5、三方核销 | `1` |
| `create_time_start` | body | number | 否 | 下单时间：开始，秒级时间戳 | `1617355413` |
| `create_time_end` | body | number | 否 | 下单时间：截止，秒级时间戳 | `1617355413` |
| `abnormal_order` | body | number | 否 | 异常订单，1-异常取消，2-风控审核中 | `1` |
| `trade_type` | body | number | 否 | 【交易类型】 0、普通 1、拼团 2、定金预售 3、订金找贷 4、拍卖 5、0元单 6、回收 7、寄卖 10、样品 | `1` |
| `combine_status` | body | array | 否 | 状态组合查询，直接输入状态码（只支持一个元素） | `` |
| `  └ order_status` | body | string | 否 | 订单状态，","分隔多个状态 | `1` |
| `  └ main_status` | body | string | 否 | 主流程状态，","分隔多个状态 | `103` |
| `update_time_start` | body | number | 否 | 更新时间：开始 | `1617355413` |
| `update_time_end` | body | number | 否 | 更新时间：截止 | `1617355413` |
| `size` | body | number | 是 | 单页大小，限制100以内 | `20` |
| `page` | body | number | 是 | 页码，0页开始 | `0` |
| `order_by` | body | string | 否 | 排序条件(create_time 订单创建时间；update_time 订单更新时间；默认create_time；) | `create_time` |
| `order_asc` | body | boolean | 否 | 排序类型，小到大或大到小，默认大到小 | `false` |
| `store_id_list` | body | array | 否 | 门店id列表 | `[1,2]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/searchList?app_key=your_appkey_here&method=order.searchList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `page` | number | 页数，从0开始 | `0` |
| `total` | number | 总订单数 | `1000` |
| `size` | number | 单页大小 | `20` |
| `shop_order_list` | array | 订单信息 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 订单查询只支持查询最近90天内的数据（sub_code: isv.parameter-invalid:20022） | 需要把下单开始时间设置为最近90天内的时间（如果没有传下单开始时间会默认设置当前时间90天前的时间为下单开始时间） |
| `40004` | 非法的参数 / 订单查询最多支持查询5万（sub_code: isv.parameter-invalid:20013） | 翻页查询最多支持查询到5万，需要缩短查询时间范围，降低查询的订单量 |
| `40004` | 非法的参数 / 订单查询状态条件超过限制，只支持1个元素（sub_code: isv.parameter-invalid:20012） | 状态查询条件是list，但现在只支持传入一个元素，重新组装参数查询 |
| `40004` | 非法的参数 / 订单查询开始时间不能为空（sub_code: isv.parameter-invalid:20011） | 时间为必传项，下单开始时间和更新开始时间必传一个 |
| `40004` | 非法的参数 / 单次查询订单数超过限制（sub_code: isv.parameter-invalid:20008） | 单页最大支持100，size设置需要 <= 100 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20005） | 如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20004） | 如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `40004` | 非法的参数 / 查询订单列表页数不能小于0（sub_code: isv.parameter-invalid:10035） | 查询页数从0开始，需要输入大于等于0的数 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "0",
    "shop_order_list": [
      {
        "app_id": "43545454556",
        "appointment_ship_time": "1617355413",
        "author_cost_amount": "100",
        "b_type": "1",
        "b_type_desc": "抖音",
        "biz": "1",
        "biz_desc": "鲁班",
        "bmp_seller_type": "xiaodian",
        "bmp_vertical_market": "supermarket_pop",
        "buyer_words": "要xxx",
        "cancel_reason": "不想要",
        "channel_payment_no": "PAY234532534534",
        "create_time": "1617355413",
        "d_car_shop_biz_data": {
          "coupon_right": [
            {
              "quota": "1",
              "right_name": "现金抵扣",
              "right_type": "1"
            }
          ],
          "poi_addr": "中关村XXX",
          "poi_adname": "金城江区",
          "poi_city_name": "河池市",
          "poi_id": "22535659043973690",
          "poi_name": "XXXX门店",
          "poi_pname": "广西壮族自治区",
          "poi_tel": "12345678901"
        },
        "doudian_open_id": "#YOUR_SECRET_KEY",
        "earliest_receipt_time": "1656049420",
        "early_arrival": "",
        "encrypt_post_receiver": "张三",
        "encrypt_post_tel": "12345678911",
        "exp_ship_time": "1617355413",
        "finish_time": "1617355413",
        "latest_receipt_time": "1656049451",
        "logistics_info": [
          {
            "company": "shunfeng",
            "company_name": "顺丰",
            "delivery_id": "shunfeng_3617355413",
            "product_info": [
              {
                "outer_sku_id": "sdfa",
                "price": "1000",
                "product_count": "2",
                "product_id": "3473196049974326153",
                "product_id_str": "3473196049974326153",
                "product_name": "苹果",
                "sku_id": "3254535",
                "sku_order_id": "4781320682406083640",
                "sku_specs": [
                  {
                    "name": "颜色",
                    "value": "蓝"
                  }
                ]
              }
            ],
            "ship_time": "1617355413",
            "tracking_no": "3617355413"
          }
        ],
        "main_status": "103",
        "main_status_desc": "部分支付",
        "modify_amount": "-10",
        "modify_post_amount": "-1",
        "only_platform_cost_amount": "100",
        "open_id": "23431434",
        "order_amount": "600",
        "order_expire_time": "1800",
        "order_id": "4781320682406083640",
        "order_level": "2",
        "order_phase_list": [
          {
            "campaign_id": "3214324342342",
            "channel_payment_no": "PAY34243247134325",
            "current_phase": "1",
            "current_phase_status_desc": "已开始但未支付",
            "pay_success": "true",
            "phase_close_time": "1617355413",
            "phase_open_time": "1617355413",
            "phase_order_amount": "100",
            "phase_order_id": "4781320682406083640",
            "phase_pay_amount": "100",
            "phase_pay_time": "1617355413",
            "phase_pay_type": "1",
            "phase_payable_price": "100",
            "phase_post_amount": "100",
            "phase_promotion_amount": "100",
            "phase_sum_amount": "100",
            "sku_order_id": "4781320682406083640",
            "sku_price": "100",
            "total_phase": "2"
          }
        ],
        "order_status": "3",
        "order_status_desc": "待支付",
        "order_type": "0",
        "order_type_desc": "普通订单",
        "pay_amount": "500",
        "pay_time": "1617355413",
        "pay_type": "1",
        "platform_cost_amount": "100",
        "post_addr": {
          "city": {
            "id": "110000",
            "name": "市辖区"
          },
          "encrypt_detail": "丹棱街1号",
          "province": {
            "id": "110000",
            "name": "北京市"
          },
          "street": {
            "id": "110000",
            "name": "中关村街道"
          },
          "town": {
            "id": "110000",
            "name": "海淀区"
          }
        },
        "post_amount": "10",
        "post_insurance_amount": "10",
        "post_origin_amount": "100",
        "post_promotion_amount": "100",
        "promise_info": "{\\\"receipt\\\":\\\"{\\\\\\\"FulfillDecisionId\\\\\\\":\\\\\\\"7117833576879604004\\\\\\\",\\\\\\\"LatestPushTime\\\\\\\":1657533600,\\\\\\\"PromiseTag\\\\\\\":\\\\\\\"ENUM:NEXT2_DAY\\\\\\\",\\\\\\\"ExpReceiptTime\\\\\\\":1657727999,\\\\\\\"RealWarehouseCode\\\\\\\":\\\\\\\"101\\\\\\\"}\\\"}",
        "promotion_amount": "1000",
        "promotion_pay_amount": "10",
        "promotion_platform_amount": "100",
        "promotion_redpack_amount": "100",
        "promotion_redpack_platform_amount": "100",
        "promotion_redpack_talent_amount": "100",
        "promotion_shop_amount": "100",
        "promotion_talent_amount": "100",
        "seller_remark_stars": "1",
        "seller_words": "注意XX",
        "serial_number_list": "[\"546443524543534\",\"646443524543534\"]",
        "ship_time": "1617355413",
        "shop_cost_amount": "100",
        "shop_id": "77977",
        "shop_name": "刘好好严选",
        "shop_order_tag_ui": [
          {
            "help_doc": "http://",
            "key": "sug_home_deliver",
            "text": "建议音尊达"
          }
        ],
        "sku_order_list": [
          {
            "account_list": {
              "account_info": [
                {
                  "account_name": "测试",
                  "account_type": "1",
                  "encrypt_account_id": "15678909876"
                }
              ]
            },
            "ad_env_type": "live",
            "after_sale_info": {
              "after_sale_status": "6",
              "after_sale_type": "1",
              "refund_status": "1"
            },
            "app_id": "43545454556",
            "appointment_ship_time": "1617355413",
            "author_cost_amount": "100",
            "author_id": "324234453",
            "author_name": "XXXX",
            "b_type": "1",
            "b_type_desc": "抖音",
            "biz": "1",
            "biz_desc": "鲁班",
            "bmp_seller_type": "xiaodian",
            "bmp_vertical_market": "supermarket_pop",
            "bundle_sku_info": [
              {
                "code": "M8-1234-101",
                "item_num": "1",
                "picture_url": "https://lf3-cm.ecombdstatic.com/obj/temai/df9426c9e41521588fe0ffbf424b6b72c559ad47www800-800",
                "product_id": "3520562294461467753",
                "product_name": "测试非卖品创建商品",
                "sku_id": "1719024557525047"
              }
            ],
            "c_biz": "1",
            "c_biz_desc": "精选联盟",
            "cancel_reason": "不想要",
            "card_voucher": {
              "valid_days": "15",
              "valid_end": "1646063999",
              "valid_start": "1646063000"
            },
            "channel_payment_no": "PAY234532534534",
            "cid": "43545454556",
            "code": "djfafj",
            "confirm_receipt_time": "1617355413",
            "content_id": "43545454556",
            "contract_info": {
              "encrypt_mobile_no": ""
            },
            "create_time": "1617355413",
            "encrypt_post_receiver": "张三",
            "encrypt_post_tel": "12345678911",
            "exp_ship_time": "1617355413",
            "finish_time": "1617355413",
            "first_cid": "20005",
            "fourth_cid": "20174",
            "given_product_type": "FREE",
            "goods_type": "1",
            "has_tax": "true",
            "inventory_list": [
              {
                "count": "2",
                "inventory_type": "1",
                "inventory_type_desc": "普通库存",
                "out_warehouse_id": "3254234234234",
                "warehouse_id": "3141234234324",
                "warehouse_type": "0"
              }
            ],
            "inventory_type": "2",
            "inventory_type_desc": "普通库存",
            "is_comment": "1",
            "item_num": "2",
            "logistics_receipt_time": "1617355413",
            "main_status": "103",
            "main_status_desc": "部分支付",
            "master_sku_order_id": "1",
            "modify_amount": "-10",
            "modify_post_amount": "-1",
            "need_serial_number": "false",
            "only_platform_cost_amount": "100",
            "order_amount": "600",
            "order_expire_time": "1800",
            "order_id": "4781320682406083640",
            "order_level": "3",
            "order_status": "3",
            "order_status_desc": "待支付",
            "order_type": "0",
            "order_type_desc": "普通订单",
            "origin_amount": "100",
            "origin_id": "43545454556",
            "out_product_id": "432655662343",
            "out_sku_id": "43564553",
            "out_warehouse_ids": "[\"49574835439\",\"954764056\"]",
            "page_id": "43545454556",
            "parent_order_id": "4781320682406083640",
            "pay_amount": "500",
            "pay_time": "1617355413",
            "pay_type": "1",
            "platform_cost_amount": "100",
            "post_addr": {
              "city": {
                "id": "110000",
                "name": "市辖区"
              },
              "encrypt_detail": "丹棱街1号",
              "province": {
                "id": "110000",
                "name": "北京市"
              },
              "street": {
                "id": "110000",
                "name": "中关村街道"
              },
              "town": {
                "id": "110000",
                "name": "海淀区"
              }
            },
            "post_amount": "1",
            "post_insurance_amount": "10",
            "pre_sale_type": "1",
            "product_id": "3473196049974326153",
            "product_id_str": "3473196049974326153",
            "product_name": "衣服",
            "product_pic": "https:xxxxx",
            "promise_info": "{\\\"identifier\\\":\\\"R#2022-07-13\\\",\\\"receipt\\\":\\\"{\\\\\\\"FulfillDecisionId\\\\\\\":\\\\\\\"7117833576879604004\\\\\\\",\\\\\\\"LatestPushTime\\\\\\\":1657533600,\\\\\\\"PromiseTag\\\\\\\":\\\\\\\"ENUM:NEXT2_DAY\\\\\\\",\\\\\\\"ExpReceiptTime\\\\\\\":1657727999,\\\\\\\"RealWarehouseCode\\\\\\\":\\\\\\\"101\\\\\\\"}\\\"}",
            "promotion_amount": "1000",
            "promotion_pay_amount": "10",
            "promotion_platform_amount": "100",
            "promotion_redpack_amount": "100",
            "promotion_redpack_platform_amount": "100",
            "promotion_redpack_talent_amount": "100",
            "promotion_shop_amount": "100",
            "promotion_talent_amount": "100",
            "receive_type": "1",
            "reduce_stock_type": "1",
            "reduce_stock_type_desc": "下单减库存",
            "room_id": "43545454556",
            "room_id_str": "147319604997432615",
            "second_cid": "20174",
            "send_pay": "1",
            "send_pay_desc": "鲁班广告",
            "ship_time": "1617355413",
            "shop_cost_amount": "100",
            "sku_customization_info": [
              {
                "detail": {
                  "extra": "{\"key\":\"value\"}",
                  "pic": [
                    {
                      "id": "1",
                      "url": "https://www.xxx.xxx"
                    }
                  ],
                  "text": [
                    {
                      "content": "1234567",
                      "id": "1",
                      "key": "order_id"
                    }
                  ]
                }
              }
            ],
            "sku_id": "3254535",
            "sku_order_tag_ui": [
              {
                "extra": "{\"key\":\"value\"}",
                "help_doc": "https://school.jinritemai.com/doudian/web/article/101835?from=shop_article",
                "hover_text": "该商品需要送到质检中心，质检完成后发给用户该商品需要送到质检中心，质检完成后发给用户",
                "key": "pre_sale_label",
                "sort": "1",
                "tag_type": "orange",
                "text": "全款预售"
              }
            ],
            "source_platform": "XXX",
            "spec": [
              {
                "name": "颜色",
                "value": "蓝"
              }
            ],
            "store_info": {
              "store_address": {
                "city": {
                  "id": "110100",
                  "name": "市辖区"
                },
                "detail": "地址门牌号",
                "province": {
                  "id": "110000",
                  "name": "北京市"
                },
                "street": {
                  "id": "110111",
                  "name": "xxx街道"
                },
                "town": {
                  "id": "110108",
                  "name": "海淀区"
                }
              },
              "store_id": "111",
              "store_name": "门店1",
              "store_tel": "13333333333"
            },
            "sub_b_type": "1",
            "sub_b_type_desc": "小程序",
            "sum_amount": "200",
            "supplier_id": "fsgfgsdg",
            "theme_type": "1",
            "theme_type_desc": "直播间",
            "third_cid": "20174",
            "trade_type": "1",
            "trade_type_desc": "拼团",
            "update_time": "1617355413",
            "video_id": "43545454556",
            "warehouse_ids": "[\"49574835439\",\"954764056\"]"
          }
        ],
        "sub_b_type": "1",
        "sub_b_type_desc": "小程序",
        "target_arrival_time": "",
        "total_promotion_amount": "100",
        "trade_type": "1",
        "trade_type_desc": "拼团",
        "update_time": "1617355413",
        "user_coordinate": {
          "user_coordinate_latitude": "15.0",
          "user_coordinate_longitude": "203.2"
        },
        "user_id_info": {
          "encrypt_id_card_name": "#YOUR_SECRET_KEY",
          "encrypt_id_card_no": "#YOUR_SECRET_KEY"
        },
        "user_tag_ui": [
          {
            "key": "user_profile_buy_frequency",
            "text": "服务优先"
          }
        ]
      }
    ],
    "size": "20",
    "total": "1000"
  },
  "err_no": 0,
  "message": "success",
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:20022",
  "sub_msg": "订单查询只支持查询最近90天内的数据"
}
```

## 备注
