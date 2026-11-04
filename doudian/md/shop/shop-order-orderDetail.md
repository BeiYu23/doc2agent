# order.orderDetail

> 订单详情查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.order.orderDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/orderDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2087 |
| 更新日期 | `2022-08-08` |

## 接口说明

- 文档书: 店铺API（版本 V30.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 店铺订单号 | `4782860977949521619` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/orderDetail?app_key=your_appkey_here&method=order.orderDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_order_detail` | object | 订单信息 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单不是该店铺下的订单，无权查询（sub_code: isv.business-failed:20015） | 请检查订单号是否正确 |
| `40004` | 非法的参数 / 查询订单不存在（sub_code: isv.parameter-invalid:20014） | 请检查订单号是否正确 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20004） | 20000：如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `40004` | 非法的参数 / 订单不存在（sub_code: isv.parameter-invalid:20001） | 检查订单号是否正确 |
| `40002` | 缺少必选参数 / 请输入查询订单号（sub_code: isv.missing-parameter:20000） | 检查订单号是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "shop_order_detail": {
      "app_id": "43545454556",
      "appointment_ship_time": "1617355413",
      "author_cost_amount": "100",
      "b_type": "1",
      "b_type_desc": "抖音",
      "biz": "1",
      "biz_desc": "鲁班",
      "bmp_seller_type": "xiandian",
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
      "earliest_receipt_time": "1656049451",
      "early_arrival": "0",
      "encrypt_post_receiver": "张三",
      "encrypt_post_tel": "12345678911",
      "exp_ship_time": "1617355413",
      "finish_time": "1617355413",
      "latest_receipt_time": "1656049619",
      "logistics_info": [
        {
          "added_services": [
            {
              "help_doc": "抖音大学介绍地址",
              "key": "VC-WBHOMEDELIVERY",
              "text": "音尊达",
              "url": "http"
            }
          ],
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
      "promotion_detail": {
        "kol_discount_detail": {
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_amount": "100",
              "coupon_id": "4781320682406",
              "coupon_meta_id": "43543523532",
              "coupon_name": "优惠券",
              "coupon_type": "1",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "full_discount_amount": "100",
          "full_discount_info": [
            {
              "campaign_amount": "200",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "150",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "redpack_amount": "100",
          "redpack_info": [
            {
              "redpack_amount": "100",
              "redpack_trans_id": "675657456546547",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "total_amount": "200"
        },
        "platform_discount_detail": {
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_amount": "100",
              "coupon_id": "4781320682406",
              "coupon_meta_id": "43543523532",
              "coupon_name": "优惠券",
              "coupon_type": "1",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "full_discount_amount": "100",
          "full_discount_info": [
            {
              "campaign_amount": "200",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "150",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "redpack_amount": "100",
          "redpack_info": [
            {
              "redpack_amount": "100",
              "redpack_trans_id": "675657456546547",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "total_amount": "200"
        },
        "shop_discount_detail": {
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_amount": "100",
              "coupon_id": "4781320682406",
              "coupon_meta_id": "43543523532",
              "coupon_name": "优惠券",
              "coupon_type": "1",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "full_discount_amount": "100",
          "full_discount_info": [
            {
              "campaign_amount": "200",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "150",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "total_amount": "200"
        }
      },
      "promotion_pay_amount": "10",
      "promotion_platform_amount": "100",
      "promotion_redpack_amount": "100",
      "promotion_redpack_platform_amount": "100",
      "promotion_redpack_talent_amount": "100",
      "promotion_shop_amount": "100",
      "promotion_talent_amount": "100",
      "seller_remark_stars": "1",
      "seller_words": "注意XX",
      "serial_number_list": "[\\\"546443524543534\\\",\\\"646443524543534\\\"]",
      "ship_time": "1617355413",
      "shop_cost_amount": "100",
      "shop_id": "77977",
      "shop_name": "刘好好严选",
      "shop_order_tag_ui": [
        {
          "help_doc": "帮助文档",
          "key": "标签key",
          "text": "推荐音尊达"
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
          "author_id": "341234",
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
              "picture_url": "https://tosv.boe.byted.org/obj/temai/ffef8099084aeb514b028ec8357d9b4awww640-640",
              "product_id": "3520562294461467753",
              "product_name": "测试非卖品创建商品",
              "sku_id": "1719024557525047"
            }
          ],
          "c_biz": "1",
          "c_biz_desc": "小店自卖",
          "campaign_info": [
            {
              "campaign_amount": "200",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "7",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "cancel_reason": "不想要",
          "card_voucher": {
            "valid_days": "15",
            "valid_end": "1646063999",
            "valid_start": "1641312000"
          },
          "channel_payment_no": "PAY234532534534",
          "cid": "43545454556",
          "code": "ahgldjj",
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
              "out_warehouse_id": "2343243245",
              "warehouse_id": "32434243432",
              "warehouse_type": "0"
            }
          ],
          "inventory_type": "2",
          "inventory_type_desc": "普通库存",
          "is_activity": "false",
          "is_comment": "1",
          "item_num": "2",
          "logistics_receipt_time": "1617355413",
          "main_status": "103",
          "main_status_desc": "部分支付",
          "master_sku_order_id": "1",
          "modify_amount": "-10",
          "modify_post_amount": "-1",
          "need_serial_number": "true",
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
          "post_amount": "10",
          "post_insurance_amount": "10",
          "pre_sale_type": "1",
          "product_id": "3473196049974326153",
          "product_id_str": "3473196049974326153",
          "product_name": "XX鞋子",
          "product_pic": "https:xxxx",
          "promise_info": "{\\\"identifier\\\":\\\"R#2022-07-13\\\",\\\"receipt\\\":\\\"{\\\\\\\"FulfillDecisionId\\\\\\\":\\\\\\\"7117833576879604004\\\\\\\",\\\\\\\"LatestPushTime\\\\\\\":1657533600,\\\\\\\"PromiseTag\\\\\\\":\\\\\\\"ENUM:NEXT2_DAY\\\\\\\",\\\\\\\"ExpReceiptTime\\\\\\\":1657727999,\\\\\\\"RealWarehouseCode\\\\\\\":\\\\\\\"101\\\\\\\"}\\\"}",
          "promotion_amount": "1000",
          "promotion_detail": {
            "kol_discount_detail": {
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_amount": "100",
                  "coupon_id": "4781320682406",
                  "coupon_meta_id": "43543523532",
                  "coupon_name": "优惠券",
                  "coupon_type": "1",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "full_discount_amount": "100",
              "full_discount_info": [
                {
                  "campaign_amount": "200",
                  "campaign_id": "4781320682406083640",
                  "campaign_name": "XXX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "150",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "redpack_amount": "100",
              "redpack_info": [
                {
                  "redpack_amount": "100",
                  "redpack_trans_id": "675657456546547",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "total_amount": "200"
            },
            "platform_discount_detail": {
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_amount": "100",
                  "coupon_id": "4781320682406",
                  "coupon_meta_id": "43543523532",
                  "coupon_name": "优惠券",
                  "coupon_type": "1",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "full_discount_amount": "100",
              "full_discount_info": [
                {
                  "campaign_amount": "200",
                  "campaign_id": "4781320682406083640",
                  "campaign_name": "XXX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "150",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "redpack_amount": "100",
              "redpack_info": [
                {
                  "redpack_amount": "100",
                  "redpack_trans_id": "675657456546547",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "total_amount": "200"
            },
            "shop_discount_detail": {
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_amount": "100",
                  "coupon_id": "4781320682406",
                  "coupon_meta_id": "43543523532",
                  "coupon_name": "优惠券",
                  "coupon_type": "1",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "full_discount_amount": "100",
              "full_discount_info": [
                {
                  "campaign_amount": "200",
                  "campaign_id": "4781320682406083640",
                  "campaign_name": "XXX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "150",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "total_amount": "200"
            }
          },
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
          "relation_order": {
            "relation_order_id": "1234567",
            "write_off_no": "xxxx"
          },
          "room_id": "435454545",
          "room_id_str": "1473196049974326153",
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
              "extra": "{\\\"key\\\":\\\"value\\\"}",
              "help_doc": "https://school.jinritemai.com/doudian/web/article/101835?from=shop_article",
              "hover_text": "该商品需要送到质检中心，质检完成后发给用户",
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
              "detail": "门牌号",
              "province": {
                "id": "110000",
                "name": "北京市"
              },
              "street": {
                "id": "110108",
                "name": "xx街道"
              },
              "town": {
                "id": "110108",
                "name": "海淀区"
              }
            },
            "store_id": "1",
            "store_name": "门店1",
            "store_tel": "13333333333"
          },
          "sub_b_type": "1",
          "sub_b_type_desc": "app",
          "sum_amount": "200",
          "supplier_id": "fsgfgsdg",
          "theme_type": "1",
          "theme_type_desc": "直播间",
          "third_cid": "20174",
          "trade_type": "1",
          "trade_type_desc": "拼团",
          "update_time": "1617355413",
          "video_id": "43545454556",
          "warehouse_ids": "[\\\"49574835439\\\",\\\"954764056\\\"]",
          "writeoff_info": [
            {
              "verify_order_id": "1234567",
              "writeoff_expire_time": "1617355413",
              "writeoff_no": "xxxx",
              "writeoff_no_mask": "Te****1168",
              "writeoff_start_time": "1617355413",
              "writeoff_status": "3",
              "writeoff_status_desc": "已使用",
              "writeoff_total_count": "2",
              "writtenoff_count": "1"
            }
          ]
        }
      ],
      "sub_b_type": "1",
      "sub_b_type_desc": "小程序",
      "target_arrival_time": "0",
      "total_promotion_amount": "100",
      "trade_type": "1",
      "trade_type_desc": "拼团",
      "update_time": "1617355413",
      "user_coordinate": {
        "user_coordinate_latitude": "12.0",
        "user_coordinate_longitude": "12.0"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:20015",
  "sub_msg": "订单不是该店铺下的订单，无权查询"
}
```

## 备注
