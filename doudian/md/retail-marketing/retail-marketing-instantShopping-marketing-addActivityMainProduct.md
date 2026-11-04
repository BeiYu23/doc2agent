# 主品报名活动

> instantShopping.marketing.addActivityMainProduct — 主品报名活动

| 元信息 | 值 |
| --- | --- |
| 中文名 | 主品报名活动 |
| 文档地址 | `/docs/doudian/retail-marketing/retail-marketing-instantShopping-marketing-addActivityMainProduct` |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.addActivityMainProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/7252 |
| 更新日期 | `2025-02-10` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 是 | 活动id | `1111` |
| `create_details` | body | array | 是 | 新增明细，不允许同时操作多个门店的明细 | `` |
| `  └ main_product_id` | body | string | 是 | 主商品id | `1111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/searchList?app_key=your_appkey_here&method=order.searchList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_detail_list` | array | 成功明细 | `` |
| `fail_detail_list` | array | 失败明细 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-40000） | 检查请求参数 |
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统异常，请联系技术人员排查（sub_code: isp.service-error:-11450） | 系统异常，请联系技术人员排查 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "1",
    "shop_order_list": [
      {
        "accept_order_status": "0",
        "actual_receive_amount_info": {
          "actual_receive_amount": "9900",
          "actual_receive_amount_details": [
            {
              "amount": "1000",
              "type": "1"
            }
          ]
        },
        "address_tag_ui": [
          {
            "hover_text": "用户选择的省、市、区/县、街道与填写的详细地址层级不一致，可能为双地址",
            "key": "double_address",
            "text": "双地址"
          }
        ],
        "app_id": "43545454556",
        "appointment_ship_time": "1617355413",
        "author_cost_amount": "100",
        "aweme_id": "Youyou",
        "b_type": "1",
        "b_type_desc": "抖音",
        "biz": "1",
        "biz_desc": "鲁班",
        "bmp_seller_type": "xiaodian",
        "bmp_source": "flower",
        "bmp_vertical_market": "giftcard",
        "buyer_words": "要xxx",
        "cancel_reason": "不想要",
        "channel_payment_no": "PAY234532534534",
        "consolidate_info": {
          "consolidate_type": "1"
        },
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
        "earliest_receipt_time": "1660788000",
        "early_arrival": "true",
        "encrypt_pay_tel": "pcS3I1UOqlJ72TCuhVY4cmSNm8jUAoZmO52C",
        "encrypt_post_receiver": "张三",
        "encrypt_post_tel": "12345678911",
        "exp_ship_time": "1617355413",
        "extra_promotion_amount_detail": [
          {
            "promotion_desc": "满20减2元运费",
            "promotion_type": "freight_discount",
            "share_cost": {
              "author_cost": "200",
              "platform_cost": "200",
              "shop_cost": "200"
            }
          }
        ],
        "finish_time": "1617355413",
        "free_interest": {
          "free_interest_detail": [
            {
              "platform_clearing_amount": "200",
              "shop_clearing_amount": "100",
              "sku_order_id": "商品单单号",
              "trade_type": "1"
            }
          ],
          "period": "12",
          "refund_total_free_interest_platform_clearing_amount": "0",
          "refund_total_free_interest_shop_clearing_amount": "0",
          "total_free_interest_platform_clearing_amount": "200",
          "total_free_interest_shop_clearing_amount": "100",
          "trade_amount": "1000"
        },
        "fulfill_status": "ACCEPTED",
        "greet_words": "贺卡信息",
        "latest_receipt_time": "1660791600",
        "logistics_info": [
          {
            "company": "shunfeng",
            "company_name": "顺丰",
            "delivery_id": "shunfeng_3617355413",
            "guarantee_amount": "100",
            "hour_up_pickup_code": "7198",
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
            "sp_discount_price": "300",
            "sp_price": "400",
            "sp_total_price": "700",
            "tracking_no": "3617355413",
            "transit_merge_type": "merge"
          }
        ],
        "main_status": "103",
        "main_status_desc": "部分支付",
        "make_up_post_amount": "10",
        "mask_pay_tel": "18*******56",
        "mask_post_addr": {
          "city": {
            "id": "110000",
            "name": "北京市"
          },
          "detail": "***",
          "province": {
            "id": "11",
            "name": "北京市"
          },
          "street": {
            "id": "110108012",
            "name": "海淀街道"
          },
          "town": {
            "id": "110108",
            "name": "海淀"
          }
        },
        "mask_post_receiver": "王**",
        "mask_post_tel": "1********35",
        "modify_amount": "-10",
        "modify_post_amount": "-1",
        "only_platform_cost_amount": "100",
        "open_id": "23431434",
        "order_amount": "600",
        "order_expire_time": "1800",
        "order_id": "4781320682406083640",
        "order_level": "2",
        "order_operate_record_list": [
          {
            "op_code": "100008",
            "op_id": "6940199726097503849_1741604941_100008",
            "operate_time": "2025-03-10 19:09:01",
            "operator": "买家"
          }
        ],
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
        "order_tag": {},
        "order_type": "0",
        "order_type_desc": "普通订单",
        "original_shop_id": "1234",
        "packing_amount": "1",
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
        "promise_detail": {
          "promise_time_detail": {
            "promise_appointment_ship_time": "1730883081",
            "promise_exp_ship_time": "1730883081",
            "promise_latest_receipt_time": "1730883081",
            "promise_recommend_end_ship_time": "1730883081",
            "promise_recommend_start_ship_time": "1730883081"
          },
          "promise_type": "2",
          "recommend_logistics_list": [
            {
              "logistics_collection_end_time": "1730883081",
              "logistics_company_code": "shunfeng",
              "logistics_company_name": "顺丰",
              "logistics_company_product_type": "tekuai",
              "logistics_company_product_type_name": "特快",
              "logistics_latest_receipt_time": "1730883081",
              "logistics_recommend_end_ship_time": "1730883081",
              "logistics_recommend_start_ship_time": "1730883081"
            }
          ]
        },
        "promise_info": "{\\\\\\\"receipt\\\\\\\":\\\\\\\"{\\\\\\\\\\\\\\\"FulfillDecisionId\\\\\\\\\\\\\\\":\\\\\\\\\\\\\\\"7117833576879604004\\\\\\\\\\\\\\\",\\\\\\\\\\\\\\\"LatestPushTime\\\\\\\\\\\\\\\":1657533600,\\\\\\\\\\\\\\\"PromiseTag\\\\\\\\\\\\\\\":\\\\\\\\\\\\\\\"ENUM:NEXT2_DAY\\\\\\\\\\\\\\\",\\\\\\\\\\\\\\\"ExpReceiptTime\\\\\\\\\\\\\\\":1657727999,\\\\\\\\\\\\\\\"RealWarehouseCode\\\\\\\\\\\\\\\":\\\\\\\\\\\\\\\"101\\\\\\\\\\\\\\\"}\\\\\\\"}",
        "promotion_amount": "1000",
        "promotion_detail": {
          "kol_discount_detail": {
            "coupon_info": [
              {
                "extra_map": {}
              }
            ],
            "full_discount_info": [
              {
                "extra_map": {}
              }
            ],
            "redpack_info": [
              {
                "extra_map": {}
              }
            ]
          },
          "platform_discount_detail": {
            "coupon_info": [
              {
                "extra_map": {}
              }
            ],
            "full_discount_info": [
              {
                "extra_map": {}
              }
            ],
            "redpack_info": [
              {
                "extra_map": {}
              }
            ]
          },
          "shop_discount_detail": {
            "coupon_info": [
              {
                "extra_map": {}
              }
            ],
            "full_discount_info": [
              {
                "extra_map": {}
              }
            ],
            "redpack_info": [
              {
                "extra_map": {}
              }
            ]
          }
        },
        "promotion_pay_amount": "10",
        "promotion_platform_amount": "100",
        "promotion_redpack_amount": "100",
        "promotion_redpack_platform_amount": "100",
        "promotion_redpack_talent_amount": "100",
        "promotion_shop_amount": "100",
        "promotion_talent_amount": "100",
        "receipt_date": "2023-08-03",
        "receipt_time_map": {},
        "recommend_end_ship_time": "1691063475",
        "recommend_logistics_list": [
          {
            "logistics_collection_end_time": "1730883081",
            "logistics_company_code": "shunfeng",
            "logistics_company_name": "顺丰",
            "logistics_delivery_end_time": "1730883081",
            "logistics_product_type": "tekuai",
            "logistics_product_type_name": "特快",
            "logistics_recommend_end_ship_time": "1730883081",
            "logistics_recommend_start_ship_time": "1730883081"
          }
        ],
        "recommend_start_ship_time": "1691063475",
        "relation_shop_order_ids": "[\"632743925435\"]",
        "seller_remark_stars": "1",
        "seller_words": "注意XX",
        "serial_number_list": "[\\\"546443524543534\\\",\\\"646443524543534\\\"]",
        "ship_time": "1617355413",
        "shop_cost_amount": "100",
        "shop_id": "77977",
        "shop_name": "刘好好严选",
        "shop_order_tag_ui": [
          {
            "extra": "标签额外信息",
            "help_doc": "http://",
            "key": "sug_home_deliver",
            "text": "建议音尊达"
          }
        ],
        "shop_period_purchase_info": {
          "deliver_type": "5",
          "period_num": "4"
        },
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
            "bmp_source": "flower",
            "bmp_vertical_market": "giftcard",
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
              "contract_id": "62e7af251e41002c",
              "encrypt_mobile_no": "13888888888"
            },
            "create_time": "1617355413",
            "custom_properties": [
              {
                "name": "正常糖"
              }
            ],
            "encrypt_post_receiver": "张三",
            "encrypt_post_tel": "12345678911",
            "exp_ship_time": "1617355413",
            "extra_info": {},
            "finish_time": "1617355413",
            "first_cid": "20005",
            "fourth_cid": "20174",
            "free_interest": {
              "free_interest_detail": [
                {
                  "platform_clearing_amount": "200",
                  "shop_clearing_amount": "100",
                  "trade_type": "1"
                }
              ],
              "period": "12",
              "refund_total_free_interest_platform_clearing_amount": "0",
              "refund_total_free_interest_shop_clearing_amount": "0",
              "total_free_interest_platform_clearing_amount": "200",
              "total_free_interest_shop_clearing_amount": "100",
              "trade_amount": "10000"
            },
            "given_exp_ship_time": "1750435199",
            "given_exp_ship_time_desc": "主商品发货后，赠品5天内发货",
            "given_product_activity_info": {
              "given_product_activity_type": "NORMAL",
              "given_product_activity_value": "2"
            },
            "given_product_type": "FREE",
            "goods_price": "100",
            "goods_type": "1",
            "gov_subsidy_detail": {
              "product_tag": "government_subsidy_multis",
              "supplier_shop_id": "12345",
              "supplier_shop_name": "abc 公司"
            },
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
            "low_price_info": {
              "low_price_product": {
                "img": "\"https://p6-aio.ecombdimg.com/obj/ecom-shop-material/wYxIpQzK_m_5e47ebab4b3ca5681b89114c96a50666_sx_298973_www800-800\"",
                "product_id": "3435495646",
                "product_name": "超值购商品",
                "sku_id": "37489375",
                "sku_specs": [
                  {
                    "name": "颜色分类",
                    "value": "白色"
                  }
                ]
              }
            },
            "main_status": "103",
            "main_status_desc": "部分支付",
            "mask_post_addr": {
              "city": {
                "id": "110000",
                "name": "北京市"
              },
              "detail": "***",
              "province": {
                "id": "11",
                "name": "北京市"
              },
              "street": {
                "id": "110108012",
                "name": "海淀街道"
              },
              "town": {
                "id": "110108",
                "name": "海淀"
              }
            },
            "mask_post_receiver": "王**",
            "mask_post_tel": "1********35",
            "master_sku_order_id": "4781320682406083640",
            "master_sku_order_id_list": "[\"4781320682406083640\"]",
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
            "out_warehouse_ids": "[\\\"49574835439\\\",\\\"954764056\\\"]",
            "packing_charge_amount": "100",
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
            "product_channel_info": {
              "product_channel_id": "6709347328",
              "product_channel_type": "4"
            },
            "product_id": "3473196049974326153",
            "product_id_str": "3473196049974326153",
            "product_name": "衣服",
            "product_pic": "https:xxxxx",
            "promise_info": "{\\\\\\\"identifier\\\\\\\":\\\\\\\"R#2022-07-13\\\\\\\",\\\\\\\"receipt\\\\\\\":\\\\\\\"{\\\\\\\\\\\\\\\"FulfillDecisionId\\\\\\\\\\\\\\\":\\\\\\\\\\\\\\\"7117833576879604004\\\\\\\\\\\\\\\",\\\\\\\\\\\\\\\"LatestPushTime\\\\\\\\\\\\\\\":1657533600,\\\\\\\\\\\\\\\"PromiseTag\\\\\\\\\\\\\\\":\\\\\\\\\\\\\\\"ENUM:NEXT2_DAY\\\\\\\\\\\\\\\",\\\\\\\\\\\\\\\"ExpReceiptTime\\\\\\\\\\\\\\\":1657727999,\\\\\\\\\\\\\\\"RealWarehouseCode\\\\\\\\\\\\\\\":\\\\\\\\\\\\\\\"101\\\\\\\\\\\\\\\"}\\\\\\\"}",
            "promotion_amount": "1000",
            "promotion_detail": {
              "kol_discount_detail": {
                "coupon_info": [
                  {
                    "extra_map": {}
                  }
                ],
                "full_discount_info": [
                  {
                    "extra_map": {}
                  }
                ],
                "redpack_info": [
                  {
                    "extra_map": {}
                  }
                ]
              },
              "platform_discount_detail": {
                "coupon_info": [
                  {
                    "extra_map": {}
                  }
                ],
                "full_discount_info": [
                  {
                    "extra_map": {}
                  }
                ],
                "redpack_info": [
                  {
                    "extra_map": {}
                  }
                ]
              },
              "shop_discount_detail": {
                "coupon_info": [
                  {
                    "extra_map": {}
                  }
                ],
                "full_discount_info": [
                  {
                    "extra_map": {}
                  }
                ],
                "redpack_info": [
                  {
                    "extra_map": {}
                  }
                ]
              }
            },
            "promotion_pay_amount": "10",
            "promotion_pay_amount_details": [
              {
                "pay_promotion_type": "混合出资-mixed_charge；GovernmentReduce-政府补贴",
                "share_cost": {
                  "platform_cost": "300",
                  "shop_cost": "300"
                }
              }
            ],
            "promotion_platform_amount": "100",
            "promotion_redpack_amount": "100",
            "promotion_redpack_platform_amount": "100",
            "promotion_redpack_talent_amount": "100",
            "promotion_shop_amount": "100",
            "promotion_talent_amount": "100",
            "quality_check_info": {
              "check_fail_msg": "贵金属不符",
              "check_result_code": "CHECK_FAIL",
              "resend_check_time": "1664350911"
            },
            "quality_inspection_status": "0",
            "receive_type": "1",
            "reduce_stock_type": "1",
            "reduce_stock_type_desc": "下单减库存",
            "relation_sku_order_ids": "[\"6374932845093\"]",
            "room_id": "147319604997432615",
            "room_id_str": "147319604997432615",
            "second_cid": "20174",
            "send_pay": "1",
            "send_pay_desc": "鲁班广告",
            "serial_no_info": {
              "all_lp_shop_code": {},
              "all_lp_task_code": {},
              "available_lp": "[\"shunfeng\"]",
              "need_photo": "true",
              "serial_no_list": [
                {
                  "serial_no_list": [
                    {
                      "key": "SN",
                      "value": "[\"SN1234\"]"
                    }
                  ],
                  "stage": "2"
                }
              ],
              "shipping_need_check_codes": "[\"SN\",\"69\",\"IMEI\"]",
              "sku_bind_69_codes": "[\"1234\"]"
            },
            "ship_time": "1617355413",
            "shop_cost_amount": "100",
            "sku_cargo_future_stock": {
              "supply_sku_snapshots": [
                {
                  "batch_detail": [
                    {
                      "arrive_time": "5",
                      "arrive_time_type": "1",
                      "batch_id": "146533163111263693",
                      "inventory_type": "1",
                      "stock_num": "1"
                    }
                  ],
                  "inventory_type": "0"
                }
              ]
            },
            "sku_customization_info": [
              {
                "detail": {
                  "extra": "{\\\"key\\\":\\\"value\\\"}",
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
            "sku_info": {
              "commit_code": "\"12222\""
            },
            "sku_order_tag_ui": [
              {
                "extra": "{\\\"key\\\":\\\"value\\\"}",
                "help_doc": "https://school.jinritemai.com/doudian/web/article/101835?from=shop_article",
                "hover_text": "该商品需要送到质检中心，质检完成后发给用户该商品需要送到质检中心，质检完成后发给用户",
                "key": "pre_sale_label",
                "sort": "1",
                "tag_type": "orange",
                "text": "全款预售"
              }
            ],
            "sku_period_purchase_info": {
              "deliver_time": "1730114000",
              "deliver_type": "5",
              "period_num": "1"
            },
            "sku_yun_warehouse_info": [
              {
                "current_business_stage": "2",
                "pre_allocated_yun_warehouse_info": {
                  "yun_warehouse_code": "001",
                  "yun_warehouse_name": "仓名称"
                },
                "real_yun_warehouse_info": {
                  "yun_warehouse_code": "001",
                  "yun_warehouse_name": "仓名称"
                },
                "sku_count": "1",
                "sku_id": "123"
              }
            ],
            "source_platform": "XXX",
            "sp_product_id": "\"32467832\"",
            "spec": [
              {
                "name": "颜色",
                "value": "蓝"
              }
            ],
            "store_info": {
              "extra": "扩展字段",
              "store_address": {
                "city": {
                  "id": "110000",
                  "name": "北京市"
                },
                "detail": "互联网金融中心",
                "province": {
                  "id": "11",
                  "name": "北京市"
                },
                "street": {
                  "id": "110108012",
                  "name": "海淀街道"
                },
                "town": {
                  "id": "110108",
                  "name": "海淀"
                }
              },
              "store_id": "1",
              "store_name": "门店名称",
              "store_tag_map": {},
              "store_tel": "13888888888"
            },
            "sub_b_type": "1",
            "sub_b_type_desc": "小程序",
            "sum_amount": "200",
            "supplier_id": "fsgfgsdg",
            "tax_amount": "8",
            "theme_type": "1",
            "theme_type_desc": "直播间",
            "third_cid": "20174",
            "trade_type": "1",
            "trade_type_desc": "拼团",
            "update_time": "1617355413",
            "video_id": "43545454556",
            "voucher_deduction_amount": "200",
            "warehouse_ids": "[\\\"49574835439\\\",\\\"954764056\\\"]"
          }
        ],
        "sub_b_type": "1",
        "sub_b_type_desc": "小程序",
        "supermarket_order_serial_no": "27",
        "target_arrival_time": "1660788000",
        "tax_amount": "8",
        "total_promotion_amount": "100",
        "trade_type": "1",
        "trade_type_desc": "拼团",
        "update_time": "1617355413",
        "urge_deliver_Times": "1",
        "user_coordinate": {
          "user_coordinate_latitude": "31.707203",
          "user_coordinate_longitude": "117.250076"
        },
        "user_icon": "https://p26.douyinpic.com/img/aweme-avatar",
        "user_id_info": {
          "encrypt_id_card_name": "#YOUR_SECRET_KEY",
          "encrypt_id_card_no": "#YOUR_SECRET_KEY"
        },
        "user_nick_name": "这是个名字",
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
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
