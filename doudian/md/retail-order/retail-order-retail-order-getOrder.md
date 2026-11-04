# retail.order.getOrder

> 【即时零售】订单详情查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-order.retail.order.getOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/retail/order/getOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1531/6727 |
| 更新日期 | `2025-11-27` |

## 接口说明

- 文档书: 订单管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 订单ID | `"6917533224570258991"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=retail.order.getOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_order_detail` | object | 订单详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20004） | 20000：如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `50002` | 业务处理失败 / 20059:查询免息信息错误，请稍后重试（sub_code: isv.business-failed:20059） | 重试 |
| `40004` | 非法的参数 / 订单不存在（sub_code: isv.parameter-invalid:20001） | 检查订单号是否正确 |
| `50002` | 业务处理失败 / 查询订单不存在（sub_code: isv.business-failed:20014） | 请检查订单号是否正确 |
| `50002` | 业务处理失败 / 110001:[FAIL,OQ10002,查询订单不存在]（sub_code: isv.business-failed:110001） | 查询订单不存在 |
| `50002` | 业务处理失败 / 20055:查询失败，请稍后重试（sub_code: isv.business-failed:20055） | 查询失败，请稍后重试 |
| `50002` | 业务处理失败 / 20015:订单不是该店铺下的订单，无权查询（sub_code: isv.business-failed:20015） | 订单不是该店铺下的订单 |
| `50002` | 业务处理失败 / 20000:请输入查询订单号（sub_code: isv.business-failed:20000） | 请输入订单号 |

## 响应示例

成功：

```json
{
  "data": {
    "shop_order_detail": {
      "accept_order_status": "1",
      "address_tag_ui": [
        {
          "help_doc": "用户选择的省、市、区/县、街道与填写的详细地址层级不一致，可能为双地址",
          "key": "双地址",
          "text": "双地址"
        }
      ],
      "aid": "11",
      "amount_info": {
        "author_cost_amount": "100",
        "make_up_post_amount": "100",
        "modify_amount": "100",
        "modify_post_amount": "100",
        "only_platform_cost_amount": "100",
        "order_amount": "100",
        "packing_amount": "100",
        "pay_amount": "100",
        "platform_cost_amount": "100",
        "post_amount": "100",
        "post_insurance_amount": "100",
        "post_origin_amount": "100",
        "post_promotion_amount": "100",
        "promotion_amount": "100",
        "promotion_pay_amount": "100",
        "promotion_platform_amount": "100",
        "promotion_redpack_amount": "100",
        "promotion_redpack_platform_amount": "100",
        "promotion_redpack_shop_amount": "100",
        "promotion_redpack_talent_amount": "100",
        "promotion_shop_amount": "100",
        "promotion_talent_amount": "100",
        "shop_cost_amount": "100",
        "tax_amount": "100",
        "total_estimated_amount_include_refund": "50",
        "total_promotion_amount": "100"
      },
      "app_id": "1128",
      "appointment_ship_time": "1721034836",
      "b_type": "2",
      "b_type_desc": "抖音",
      "biz": "2",
      "biz_desc": "小店",
      "buyer_words": "取消",
      "cancel_reason": "支付超时",
      "channel_payment_no": "mock_DPM2304261117519001500291007185",
      "create_time": "1721034836",
      "doudian_open_id": "1#1231212",
      "earliest_receipt_time": "1721034836",
      "early_arrival": "true",
      "encrypt_pay_tel": "1231234",
      "encrypt_post_receiver": "张三",
      "encrypt_post_tel": "12341234",
      "exp_ship_time": "1721041802",
      "extra_promotion_amount_detail": [
        {
          "promotion_desc": "满20减元运费",
          "promotion_type": "优惠类型",
          "share_cost": {
            "author_cost": "100",
            "platform_cost": "100",
            "shop_cost": "100"
          }
        }
      ],
      "finish_time": "1721034836",
      "free_interest": {
        "free_interest_detail": [
          {
            "platform_clearing_amount": "100",
            "shop_clearing_amount": "100",
            "trade_type": "1"
          }
        ],
        "period": "12",
        "refund_total_free_interest_partner_clearing_amount": "100",
        "refund_total_free_interest_platform_clearing_amount": "100",
        "total_free_interest_platform_clearing_amount": "100",
        "total_free_interest_shop_clearing_amount": "100",
        "trade_amount": "100"
      },
      "fulfill_status": "ACCEPTED",
      "fulfilment_mode": "0",
      "greet_words": "贺卡",
      "latest_receipt_time": "1721034836",
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
          "guarantee_amount": "100",
          "hour_up_pickup_code": "7198",
          "product_info": [
            {
              "outer_sku_id": "sdfa",
              "price": "100",
              "product_count": "2",
              "product_id": "3473196049974326153",
              "product_id_str": "3473196049974326153",
              "product_name": "苹果",
              "sku_id": "3254535",
              "sku_order_id": "4781320682406083640",
              "sku_specs": [
                {
                  "name": "颜色",
                  "value": "蓝色"
                }
              ]
            }
          ],
          "ship_time": "1617355413",
          "sp_discount_price": "100",
          "sp_price": "100",
          "sp_total_price": "100",
          "tracking_no": "3617355413"
        }
      ],
      "main_status": "3",
      "main_status_desc": "已全部发货",
      "mask_pay_tel": "1********20",
      "mask_post_addr": {
        "city": {
          "id": "310000",
          "name": "市辖区"
        },
        "detail": "生单工***",
        "province": {
          "id": "31",
          "name": "上海市"
        },
        "street": {
          "id": "310120001",
          "name": "金海街道"
        },
        "town": {
          "id": "310120",
          "name": "奉贤区"
        }
      },
      "mask_post_receiver": "生***",
      "mask_post_tel": "1********20",
      "order_expire_time": "1721034836",
      "order_id": "6917533224570258991",
      "order_level": "2",
      "order_status": "3",
      "order_status_desc": "已发货",
      "order_tag": {},
      "order_type": "0",
      "order_type_desc": "普通订单",
      "original_shop_id": "1234",
      "pay_time": "1721034836",
      "pay_type": "2",
      "post_addr": {
        "city": {
          "id": "310000",
          "name": "市辖区"
        },
        "encrypt_detail": "xxx",
        "province": {
          "id": "31",
          "name": "上海市"
        },
        "street": {
          "id": "310120001",
          "name": "金海街道"
        },
        "town": {
          "id": "310120",
          "name": "奉贤区"
        }
      },
      "promise_info": "{\"identifier\":\"S#2023-04-26\"}",
      "promotion_detail": {
        "kol_discount_detail": {
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_amount": "100",
              "coupon_id": "123456",
              "coupon_meta_id": "123456",
              "coupon_name": "券名称",
              "coupon_type": "21",
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
              "campaign_amount": "100",
              "campaign_id": "123456",
              "campaign_name": "活动名称",
              "campaign_sub_type": "0",
              "campaign_type": "100",
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
              "redpack_trans_id": "123456",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "total_amount": "100"
        },
        "platform_discount_detail": {
          "allowance_amount": "100",
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_amount": "100",
              "coupon_id": "123456",
              "coupon_meta_id": "123456",
              "coupon_name": "券名称",
              "coupon_type": "21",
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
              "campaign_amount": "100",
              "campaign_id": "123456",
              "campaign_name": "活动名称",
              "campaign_sub_type": "0",
              "campaign_type": "100",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "gold_coin_amount": "100",
          "official_deduction_amount": "100",
          "redpack_amount": "100",
          "redpack_info": [
            {
              "redpack_amount": "100",
              "redpack_trans_id": "红包汇总id",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "total_amount": "100",
          "user_balance_amount": "100"
        },
        "shop_discount_detail": {
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_activity_id": "优惠券所属商家活动ID",
              "coupon_amount": "100",
              "coupon_id": "123456",
              "coupon_meta_id": "12345678",
              "coupon_name": "券名称",
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
              "campaign_activity_id": "123456",
              "campaign_amount": "100",
              "campaign_id": "123456",
              "campaign_name": "活动名称",
              "campaign_sub_type": "0",
              "campaign_type": "7",
              "share_discount_cost": {
                "author_cost": "100",
                "extra_map": {},
                "platform_cost": "100",
                "shop_cost": "100",
                "third_platform_cost": "0"
              }
            }
          ],
          "redpack_amount": "100",
          "redpack_info": [
            {
              "redpack_amount": "100",
              "redpack_trans_id": "123456",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "total_amount": "100"
        }
      },
      "receipt_date": "2023-08-07",
      "receipt_time_map": {},
      "recommend_end_ship_time": "1721034836",
      "recommend_start_ship_time": "1721034836",
      "seller_remark_stars": "0",
      "seller_words": "取消",
      "sender_info": {
        "sender_addr": {
          "city": {
            "id": "310000",
            "name": "市辖区"
          },
          "detail": "生单工***",
          "province": {
            "id": "31",
            "name": "上海市"
          },
          "street": {
            "id": "金海街道",
            "name": "310120001"
          },
          "town": {
            "id": "奉贤区",
            "name": "310120"
          }
        },
        "sender_name": "张三",
        "sender_tel": "123456"
      },
      "serial_number_list": "[\"546443524543534\"]",
      "ship_time": "1721041802",
      "shop_id": "123456",
      "shop_name": "订单专用_测试店三",
      "shop_order_tag_ui": [
        {
          "extra": "额外信息",
          "help_doc": "帮助文档",
          "key": "标签key",
          "text": "标签文案"
        }
      ],
      "sku_order_list": [
        {
          "after_sale_info": {
            "after_sale_status": "1",
            "after_sale_type": "1",
            "refund_status": "6"
          },
          "app_id": "1128",
          "appointment_ship_time": "1721041802",
          "author_cost_amount": "100",
          "author_id": "341234",
          "author_name": "xxx",
          "b_type": "2",
          "b_type_desc": "抖音",
          "biz": "1",
          "biz_desc": "鲁班",
          "bundle_sku_info": [
            {
              "item_num": "3",
              "picture_url": "http://",
              "product_id": "3520562294461467753",
              "product_name": "子商品名称",
              "sku_id": "1719024557525047"
            }
          ],
          "c_biz": "8",
          "c_biz_desc": "小店自卖",
          "campaign_info": [
            {
              "campaign_activity_id": "123456",
              "campaign_amount": "100",
              "campaign_id": "123456",
              "campaign_name": "活动名称",
              "campaign_sub_type": "0",
              "campaign_type": "100",
              "extra_map": {},
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
          "channel_payment_no": "PAY34243247134325",
          "code": "ahgldjj",
          "confirm_receipt_time": "1721041802",
          "create_time": "1617355413",
          "custom_properties": [
            {
              "name": "正常糖"
            }
          ],
          "encrypt_post_receiver": "张三",
          "encrypt_post_tel": "xxxx",
          "exp_ship_time": "1721041802",
          "extra_info": {},
          "finish_time": "1617355413",
          "first_cid": "20005",
          "fourth_cid": "20174",
          "free_interest": {
            "free_interest_detail": [
              {
                "platform_clearing_amount": "100",
                "shop_clearing_amount": "100",
                "trade_type": "1"
              }
            ],
            "period": "12",
            "refund_total_free_interest_platform_clearing_amount": "100",
            "refund_total_free_interest_shop_clearing_amount": "100",
            "total_free_interest_platform_clearing_amount": "100",
            "total_free_interest_shop_clearing_amount": "100",
            "trade_amount": "100"
          },
          "given_product_activity_info": {
            "given_product_activity_type": "NORMAL",
            "given_product_activity_value": "200"
          },
          "given_product_type": "FREE",
          "goods_price": "100",
          "goods_type": "1",
          "is_activity": "false",
          "is_comment": "1",
          "item_num": "2",
          "logistics_receipt_time": "1721041802",
          "main_status": "3",
          "main_status_desc": "部分支付",
          "mask_post_addr": {
            "city": {
              "id": "110000",
              "name": "北京市"
            },
            "detail": "***",
            "province": {
              "id": "110000",
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
          "mask_post_receiver": "生***",
          "mask_post_tel": "1********20",
          "master_sku_order_id_list": "[\"4781320682406083640\"]",
          "modify_amount": "100",
          "modify_post_amount": "100",
          "need_serial_number": "true",
          "only_platform_cost_amount": "100",
          "order_amount": "100",
          "order_expire_time": "1617355413",
          "order_id": "4781320682406083640",
          "order_level": "3",
          "order_status": "3",
          "order_status_desc": "待支付",
          "order_type": "0",
          "order_type_desc": "普通订单",
          "origin_amount": "100",
          "out_product_id": "432655662343",
          "out_sku_id": "43564553",
          "packing_charge_amount": "100",
          "page_id": "43545454556",
          "parent_order_id": "4781320682406083640",
          "pay_amount": "100",
          "pay_time": "1617355413",
          "pay_type": "2",
          "platform_cost_amount": "100",
          "post_addr": {
            "city": {
              "id": "310000",
              "name": "市辖区"
            },
            "encrypt_detail": "xxx",
            "province": {
              "id": "31",
              "name": "上海市"
            },
            "street": {
              "id": "310120001",
              "name": "金海街道"
            },
            "town": {
              "id": "310120",
              "name": "奉贤区"
            }
          },
          "post_amount": "100",
          "post_insurance_amount": "100",
          "pre_sale_type": "1",
          "prescription_info_list": [
            {
              "consultation_detail": {
                "consultation_i_d": "1234",
                "patinet_info": {
                  "age": "22",
                  "gender": "男",
                  "id_card_num": "1**************23",
                  "is_follow_up_visit": "true",
                  "medical_history": "[1]",
                  "name": "张三"
                }
              },
              "prescription_detail": {
                "consultation_i_d": "123456",
                "create_time": "1711531958",
                "img_urls": "1231",
                "prescription_i_d": "123456",
                "status": "1"
              }
            }
          ],
          "product_channel_info": {
            "product_channel_id": "6832432432",
            "product_channel_type": "3"
          },
          "product_id": "3473196049974326153",
          "product_id_str": "3473196049974326153",
          "product_name": "XX鞋子",
          "product_pic": "https:xxxx",
          "promise_info": "{\"identifier\":\"S#2023-04-26\"}",
          "promotion_amount": "100",
          "promotion_detail": {
            "kol_discount_detail": {
              "allowance_amount": "100",
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_activity_id": "123456",
                  "coupon_amount": "100",
                  "coupon_id": "123456",
                  "coupon_meta_id": "123456",
                  "coupon_name": "券名称",
                  "coupon_type": "1",
                  "coupon_type_desc": "100",
                  "credit": "100",
                  "discount": "100",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  },
                  "threshold": "100",
                  "user_nick_name": "达人昵称"
                }
              ],
              "full_discount_amount": "100",
              "full_discount_info": [
                {
                  "campaign_activity_id": "123456",
                  "campaign_amount": "100",
                  "campaign_id": "123456",
                  "campaign_name": "活动名称",
                  "campaign_sub_type": "0",
                  "campaign_type": "7",
                  "campaign_type_desc": "活动类型文案",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "gold_coin_amount": "100",
              "official_deduction_amount": "100",
              "redpack_amount": "100",
              "redpack_info": [
                {
                  "redpack_amount": "100",
                  "redpack_trans_id": "123456",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "total_amount": "100",
              "user_balance_amount": "100"
            },
            "platform_discount_detail": {
              "allowance_amount": "100",
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_activity_id": "123456",
                  "coupon_amount": "100",
                  "coupon_id": "123456",
                  "coupon_meta_id": "123456",
                  "coupon_name": "券名称",
                  "coupon_type": "1",
                  "coupon_type_desc": "平台折扣券",
                  "discount": "100",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  },
                  "threshold": "100"
                }
              ],
              "full_discount_amount": "100",
              "full_discount_info": [
                {
                  "campaign_activity_id": "123456",
                  "campaign_amount": "100",
                  "campaign_id": "123456",
                  "campaign_name": "活动名称",
                  "campaign_sub_type": "0",
                  "campaign_type": "7",
                  "campaign_type_desc": "限时特卖",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "gold_coin_amount": "100",
              "official_deduction_amount": "100",
              "redpack_amount": "100",
              "redpack_info": [
                {
                  "redpack_amount": "100",
                  "redpack_trans_id": "123456",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "total_amount": "100",
              "user_balance_amount": "100"
            },
            "shop_discount_detail": {
              "allowance_amount": "100",
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_amount": "100",
                  "coupon_id": "4781320682406",
                  "coupon_meta_id": "123456",
                  "coupon_name": "优惠券",
                  "coupon_type": "1",
                  "coupon_type_desc": "1",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  },
                  "user_nick_name": "这是个名字"
                }
              ],
              "full_discount_amount": "100",
              "full_discount_info": [
                {
                  "campaign_activity_id": "1243456",
                  "campaign_amount": "100",
                  "campaign_id": "1243456",
                  "campaign_name": "XXX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "7",
                  "campaign_type_desc": "1",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "gold_coin_amount": "100",
              "official_deduction_amount": "100",
              "redpack_amount": "100",
              "redpack_info": [
                {
                  "redpack_amount": "100",
                  "redpack_trans_id": "123456",
                  "share_discount_cost": {
                    "author_cost": "100",
                    "platform_cost": "100",
                    "shop_cost": "100"
                  }
                }
              ],
              "total_amount": "100",
              "user_balance_amount": "100"
            }
          },
          "promotion_pay_amount": "100",
          "promotion_pay_amount_details": [
            {
              "share_cost": {
                "author_cost": "100",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "promotion_platform_amount": "100",
          "promotion_redpack_amount": "100",
          "promotion_redpack_platform_amount": "100",
          "promotion_redpack_shop_amount": "100",
          "promotion_redpack_talent_amount": "100",
          "promotion_shop_amount": "100",
          "promotion_talent_amount": "100",
          "receive_type": "1",
          "reduce_stock_type": "1",
          "reduce_stock_type_desc": "下单减库存",
          "room_id": "435454545",
          "room_id_str": "1473196049974326153",
          "second_cid": "20174",
          "serial_no_info": {
            "all_lp_shop_code": {},
            "all_lp_task_code": {},
            "available_lp": "\"顺丰\"",
            "express_info": [
              {
                "express_code": "shunfeng",
                "tasks": [
                  {
                    "scene": "ebill",
                    "shop_code": "\"\"",
                    "task_code": "\"\""
                  }
                ]
              }
            ],
            "is_can_edit": "true",
            "is_need_check_by_industry": "true",
            "is_required": "false",
            "need_check_available_lp": "false",
            "need_photo": "false",
            "serial_no_list": [
              {
                "serial_no_list": [
                  {
                    "content_type": "image",
                    "key": "SN",
                    "label": "\"\"",
                    "value": "\"\""
                  }
                ],
                "stage": "2"
              }
            ],
            "shipping_need_check_codes": "\"69\", \"SN\"",
            "sku_binds_69_codes": "\"123132131\""
          },
          "ship_time": "1617355413",
          "shop_cost_amount": "100",
          "sku_id": "3254535",
          "sku_medical_trace_info": {
            "item_count": "1",
            "need_trace_info": "false",
            "strong_check": "false",
            "trace_info": {
              "batch_and_trace_code_list": [
                {
                  "batch_code": "\"123\"",
                  "trace_code": "\"123\""
                }
              ],
              "sku_order_id": "\"123\""
            }
          },
          "sku_order_tag_ui": [
            {
              "extra": "额外信息，json格式",
              "help_doc": "帮助文档",
              "hover_text": "标签备注文案",
              "key": "标签key",
              "sort": "排序",
              "tag_type": "标签类型，如颜色",
              "text": "标签文案"
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
            "extra": "扩展字段",
            "store_address": {
              "city": {
                "id": "310000",
                "name": "市辖区"
              },
              "detail": "xxx",
              "province": {
                "id": "31",
                "name": "上海市"
              },
              "street": {
                "id": "310120001",
                "name": "金海街道"
              },
              "town": {
                "id": "310120",
                "name": "奉贤区"
              }
            },
            "store_id": "123456",
            "store_name": "门店名称",
            "store_tel": "12345678"
          },
          "sub_b_type": "3",
          "sub_b_type_desc": "app",
          "sum_amount": "200",
          "supplier_id": "fsgfgsdg",
          "tax_amount": "100",
          "third_cid": "20174",
          "trade_type": "1",
          "trade_type_desc": "拼团",
          "update_time": "1617355413",
          "video_id": "43545454556",
          "voucher_deduction_amount": "100"
        }
      ],
      "sub_b_type": "3",
      "sub_b_type_desc": "H5",
      "supermarket_order_serial_no": "135334",
      "target_arrival_time": "1721034836",
      "update_time": "1721034836",
      "user_coordinate": {
        "user_coordinate_latitude": "117.250076",
        "user_coordinate_longitude": "31.707203"
      },
      "user_tag_ui": [
        {
          "key": "user_profile_shop_customer_type",
          "text": "店铺老客"
        }
      ]
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4100003",
  "sub_msg": "参数非法"
}
```

## 备注
