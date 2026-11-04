# instantShopping.marketing.updateActivityProducts

> 更新商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.updateActivityProducts` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6383 |
| 更新日期 | `2024-05-22` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 是 | 活动id | `123` |
| `update_details` | body | array | 是 | 待编辑的优惠明细 | `` |
| `  └ main_product_id` | body | string | 否 | 主品id | `123` |
| `  └ main_sku_id` | body | string | 否 | 主skuId | `123` |
| `  └ activity_detail` | body | object | 否 | 优惠详情 | `` |
| `    └ stock_option` | body | object | 否 | 库存设置 | `` |
| `      └ use_max_limit` | body | boolean | 是 | true：实际库存小于活动库存时，使用实际库存作为活动库存 false：实际库存小于活动库存时，禁止提报 | `true` |
| `      └ activity_stock` | body | number | 是 | 提报使用的活动库存 | `123` |
| `    └ activity_price` | body | number | 否 | 活动价，单位：分 | `123` |
| `    └ limit_buy` | body | number | 否 | 每人限购 | `123` |
| `  └ sub_product_id` | body | string | 否 | 子品ID | `123` |
| `  └ sub_sku_id` | body | string | 否 | 子品SKUID | `123` |
| `  └ store_id` | body | number | 是 | 门店id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/orderDetail?app_key=your_appkey_here&method=order.orderDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_detail_list` | array | 成功更新的优惠明细 | `` |
| `fail_detail_list` | array | 失败的优惠明细 | `` |

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
    "shop_order_detail": {
      "accept_order_status": "1",
      "address_tag_ui": [
        {
          "hover_text": "用户选择的省、市、区/县、街道与填写的详细地址层级不一致，可能为双地址",
          "key": "double_address",
          "text": "双地址"
        }
      ],
      "app_id": "1128",
      "appointment_ship_time": "0",
      "author_cost_amount": "0",
      "aweme_id": "Youyou",
      "b_type": "2",
      "b_type_desc": "抖音",
      "biz": "2",
      "biz_desc": "小店",
      "buyer_words": "取消",
      "cancel_reason": "支付超时",
      "channel_payment_no": "mock_DPM2304261117519001500291007185",
      "consolidate_info": {
        "consolidate_type": "1"
      },
      "create_time": "1.682479079e+09",
      "d_car_shop_biz_data": {
        "coupon_right": [
          {
            "quota": "1",
            "right_name": "现金抵扣",
            "right_type": "1"
          }
        ],
        "poi_addr": "<nil>",
        "poi_adname": "<nil>",
        "poi_city_name": "<nil>",
        "poi_id": "<nil>",
        "poi_name": "<nil>",
        "poi_pname": "<nil>",
        "poi_tel": "<nil>"
      },
      "doudian_open_id": "1@#YOUR_SECRET_KEY",
      "earliest_receipt_time": "0",
      "early_arrival": "false",
      "encrypt_pay_tel": "134",
      "encrypt_post_receiver": "aaa",
      "encrypt_post_tel": "1231234",
      "exp_ship_time": "1.682524799e+09",
      "finish_time": "0",
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
        "trade_amount": "200"
      },
      "fulfill_status": "ACCEPTED",
      "greet_words": "贺卡",
      "latest_receipt_time": "0",
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
          "guarantee_amount": "300",
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
          "tracking_no": "3617355413"
        }
      ],
      "main_status": "3",
      "main_status_desc": "已全部发货",
      "mask_pay_tel": "XXX",
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
      "modify_amount": "0",
      "modify_post_amount": "0",
      "only_platform_cost_amount": "0",
      "open_id": "69175",
      "order_amount": "20500",
      "order_expire_time": "1800",
      "order_id": "6917533224570258991",
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
      "order_recycle_info": {
        "appoint_recycle_end_time": "1685440259",
        "appoint_recycle_start_time": "1685440259",
        "pronduct_desc": "大家电-空调",
        "quoted_price": "3",
        "recycle_actual_amount_info": {
          "actual_amount": "1",
          "send_channel": "1",
          "send_status": "1"
        },
        "recycle_mode": "1",
        "recycle_order_id": "6898432433432",
        "recycle_status": "2",
        "recycle_status_desc": "分配师傅",
        "shop_subsidy_amount_info": {
          "subsidy_channel": "1",
          "subsidy_status": "1",
          "subsidya_amount": "100"
        },
        "subsidy_receive_status": "待发放",
        "supplier_code": "73849324",
        "supplier_name": "嗨回收"
      },
      "order_status": "3",
      "order_status_desc": "已发货",
      "order_tag": {},
      "order_type": "0",
      "order_type_desc": "普通订单",
      "original_shop_id": "1234",
      "packing_amount": "0",
      "pay_amount": "20500",
      "pay_time": "1.682479081e+09",
      "pay_type": "2",
      "platform_cost_amount": "0",
      "post_addr": {
        "city": {
          "id": "310000",
          "name": "市辖区"
        },
        "encrypt_detail": "金海街道",
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
      "post_amount": "500",
      "post_insurance_amount": "0",
      "post_origin_amount": "500",
      "post_promotion_amount": "0",
      "promise_info": "{\"identifier\":\"S#2023-04-26\"}",
      "promotion_amount": "0",
      "promotion_detail": {
        "kol_discount_detail": {
          "coupon_amount": "0",
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
          "full_discount_amount": "0",
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
          "redpack_amount": "0",
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
          "total_amount": "0"
        },
        "platform_discount_detail": {
          "allowance_amount": "0",
          "coupon_amount": "0",
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
          "full_discount_amount": "0",
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
          "gold_coin_amount": "0",
          "official_deduction_amount": "0",
          "redpack_amount": "0",
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
          "total_amount": "0",
          "user_balance_amount": "0"
        },
        "shop_discount_detail": {
          "coupon_amount": "0",
          "coupon_info": [
            {
              "coupon_activity_id": "47813206821235",
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
          "full_discount_amount": "0",
          "full_discount_info": [
            {
              "campaign_activity_id": "4781320682406083610",
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
          "redpack_amount": "0",
          "redpack_info": [
            {
              "redpack_amount": "0",
              "redpack_trans_id": "634783264",
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "0",
                "shop_cost": "0"
              }
            }
          ],
          "total_amount": "0"
        }
      },
      "promotion_pay_amount": "0",
      "promotion_platform_amount": "0",
      "promotion_redpack_amount": "0",
      "promotion_redpack_platform_amount": "0",
      "promotion_redpack_talent_amount": "0",
      "promotion_shop_amount": "0",
      "promotion_talent_amount": "0",
      "receipt_date": "2023-08-07",
      "receipt_time_map": {},
      "recommend_end_ship_time": "1691063298",
      "recommend_start_ship_time": "1691063298",
      "seller_remark_stars": "0",
      "seller_words": "取消",
      "serial_number_list": "[\\\"546443524543534\\\",\\\"646443524543534\\\"]",
      "ship_time": "1.682479086e+09",
      "shop_cost_amount": "0",
      "shop_id": "94956",
      "shop_name": "订单专用_测试店三",
      "shop_order_tag_ui": [
        {
          "extra": "标签额外信息",
          "help_doc": "帮助文档",
          "key": "标签key",
          "text": "推荐音尊达"
        }
      ],
      "shop_recycle_subsidy_amount_info": {
        "amount_composition_info": {
          "platform_cost": "100",
          "shop_cost": "100"
        },
        "subsidy_amount": "100",
        "subsidy_channel": "1",
        "subsidy_status": "1"
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
          "author_id": "341234",
          "author_name": "XXXX",
          "b_type": "1",
          "b_type_desc": "抖音",
          "biz": "1",
          "biz_desc": "鲁班",
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
              "campaign_activity_id": "4781320682406083612",
              "campaign_amount": "200",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "7",
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
          "channel_payment_no": "PAY234532534534",
          "cid": "43545454556",
          "code": "ahgldjj",
          "confirm_receipt_time": "1617355413",
          "content_id": "43545454556",
          "contract_info": {
            "contract_id": "62e7af251e41002c",
            "encrypt_mobile_no": "13888888888"
          },
          "create_time": "1617355413",
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
          "given_product_activity_info": {
            "given_product_activity_type": "NORMAL",
            "given_product_activity_value": "200"
          },
          "given_product_type": "FREE",
          "goods_price": "100",
          "goods_type": "1",
          "has_tax": "true",
          "home_installation_service_info": {
            "latest_status": "1",
            "service_info": {
              "appointment_slice_time": {
                "end_time": "1707191091",
                "start_time": "1707190091",
                "update_time": "1707190091"
              },
              "service_finish_time": "1707190091",
              "service_status": "5",
              "service_status_desc": "安装服务已完成",
              "sign_in_time": "1707190091"
            },
            "supplier_info": {
              "auxiliary_material_url": "https://school.jinritemai.YOUR_SECRET_KEY?from=shop_article",
              "supplier_charge_desc": "因安装环境可能产生的辅材、配件等额外费用需要消费者线下支付，当前报价标准由平台提供",
              "supplier_name": "周一科技有限公司",
              "supplier_shop_id": "98643",
              "supplier_tel": "4000000056"
            },
            "worker_info": {
              "worker_name": "王师傅",
              "worker_tel": "13023432217"
            }
          },
          "inventory_list": [
            {
              "count": "2",
              "inventory_type": "1",
              "inventory_type_desc": "普通库存",
              "out_warehouse_id": "2343243245",
              "warehouse_id": "32434243432",
              "warehouse_name": "测试仓11",
              "warehouse_type": "0"
            }
          ],
          "inventory_type": "2",
          "inventory_type_desc": "普通库存",
          "is_activity": "false",
          "is_comment": "1",
          "item_num": "2",
          "logistics_receipt_time": "1617355413",
          "low_price_info": {
            "low_price_product": {
              "img": "https://p6-aio.ecombdimg.com/obj/ecom-shop-material/wYxIpQzK_m_5e47ebab4b3ca5681b89114c96a50666_sx_298973_www800-800",
              "product_id": "374893578943",
              "product_name": "测试商品",
              "sku_id": "3789354",
              "sku_specs": [
                {
                  "name": "颜色",
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
          "mask_post_receiver": "王**",
          "mask_post_tel": "1********35",
          "master_sku_order_id": "1",
          "master_sku_order_id_list": "[\"4781320682406083640\"]",
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
          "post_amount": "10",
          "post_insurance_amount": "10",
          "pre_sale_type": "1",
          "prescription_info_list": [
            {
              "consultation_detail": {
                "consultation_id": "1234",
                "patient_info": {
                  "age": "22",
                  "gender": "男",
                  "id_card_num": "1**************23",
                  "is_follow_up_visit": "true",
                  "medical_history": "[1]",
                  "name": "张三"
                }
              },
              "prescription_detail": {
                "consultation_id": "123456",
                "create_time": "1711531958",
                "img_urls": "链接地址",
                "prescription_id": "123456",
                "status": "1"
              }
            }
          ],
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
              "allowance_amount": "100",
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
              "gold_coin_amount": "100",
              "official_deduction_amount": "100",
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
              "total_amount": "200",
              "user_balance_amount": "100"
            },
            "shop_discount_detail": {
              "coupon_amount": "100",
              "coupon_info": [
                {
                  "coupon_activity_id": "4781320682102",
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
                  "campaign_activity_id": "4781320682406083621",
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
              "redpack_amount": "0",
              "redpack_info": [
                {
                  "redpack_amount": "0",
                  "redpack_trans_id": "623894372",
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
                  }
                }
              ],
              "total_amount": "200"
            }
          },
          "promotion_pay_amount": "10",
          "promotion_pay_amount_details": [
            {
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
          "quality_inspection_status": "质检状态",
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
          "sku_car_model_desc": "车型",
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
            "store_tel": "13888888888"
          },
          "sub_b_type": "1",
          "sub_b_type_desc": "app",
          "sum_amount": "200",
          "supplier_id": "fsgfgsdg",
          "tax_amount": "8",
          "tax_amount_not_come_out": "0",
          "theme_type": "1",
          "theme_type_desc": "直播间",
          "third_cid": "20174",
          "trade_type": "1",
          "trade_type_desc": "拼团",
          "update_time": "1617355413",
          "video_id": "43545454556",
          "voucher_deduction_amount": "200",
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
      "sub_b_type": "3",
      "sub_b_type_desc": "H5",
      "supermarket_order_serial_no": "135334",
      "target_arrival_time": "0",
      "tax_amount": "0",
      "tax_amount_not_come_out": "0",
      "total_promotion_amount": "0",
      "trade_type": "0",
      "trade_type_desc": "普通",
      "update_time": "1.682479087e+09",
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
