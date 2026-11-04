# 拣货前退款后订单查询接口【即时零售】

> sendHome.order.getOrderDetailAfterPicking — 拣货前退款后订单查询接口【即时零售】

| 元信息 | 值 |
| --- | --- |
| 中文名 | 拣货前退款后订单查询接口【即时零售】 |
| 文档地址 | `/docs/doudian/order/order-sendHome-order-getOrderDetailAfterPicking` |
| 接口 ID | `doudian.order.sendHome.order.getOrderDetailAfterPicking` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sendHome/order/getOrderDetailAfterPicking` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/6634 |
| 更新日期 | `2025-08-18` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 否 | 店铺订单id | `6930331302740104585` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sendHome.order.getOrderDetailAfterPicking&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_picked` | mixed | 是否拣货完成,0-拣货未完成,1-拣货完成 | `1` |
| `refund_type` | mixed | 退款类型,0-无售后退款,1-发生了部分退款,2-发生了整单退款 | `0` |
| `downgrade` | mixed | 是否降级,0-有降级（部分数据尚未完成计算）,1-无降级（全部数据已完成计算 | `1` |
| `downgrade_reason` | mixed | 降级原因,1-订单信息查询失败2-退款信息查询失败3-存在未完成的退款4-拣货信息查询失败5-未完成拣货6-资金分摊查询失败7-资金分摊计算结果不符合预期8-支付优惠查询失败9-支付优惠计算结果不符合预期10-其他原因 | `0` |
| `shop_order_detail` | object | 订单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 拣货未完成（sub_code: isv.business-failed:5100802） | 上报拣货完成后重新请求 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入必填参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常-不可重试的错误（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常-可重试（sub_code: isp.service-error:5100002） | 系统异常，可尝试重试 |
| `50002` | 业务处理失败 / 存在未完成的售后单（sub_code: isv.business-failed:5100801） | 等待售后单完成后再请求 |
| `50002` | 业务处理失败 / 资金明细计算失败（sub_code: isv.business-failed:5100803） | 可尝试重试 |
| `50002` | 业务处理失败 / 支付优惠分摊计算失败（sub_code: isv.business-failed:5100804） | 可尝试重试 |
| `50002` | 业务处理失败 / 查询订单详情失败（sub_code: isv.business-failed:5000801） | 可尝试重试，大规模出现时可降低请求qps |
| `50002` | 业务处理失败 / 查询退款详情失败（sub_code: isv.business-failed:5000802） | 可尝试重试，大规模出现时可降低请求qps |
| `50002` | 业务处理失败 / 获取拣货完成情况失败（sub_code: isv.business-failed:5000803） | 可尝试重试，大规模出现时可降低请求qps |
| `50002` | 业务处理失败 / 查询资金明细失败（sub_code: isv.business-failed:5000804） | 可尝试重试，大规模出现时可降低请求qps |
| `50002` | 业务处理失败 / 获取支付优惠分摊失败（sub_code: isv.business-failed:5000805） | 可尝试重试，大规模出现时可降低请求qps |

## 响应示例

成功：

```json
{
  "data": {
    "downgrade": "1",
    "downgrade_reason": "0",
    "is_picked": "1",
    "refund_type": "0",
    "shop_order_detail": {
      "author_cost_amount": "100",
      "extra_promotion_amount_detail": [
        {
          "extra_map": {},
          "instant_discount_type": "活动类型",
          "promotion_desc": "优惠描述",
          "promotion_id": "平台活动id",
          "promotion_type": "优惠类型",
          "share_cost": {
            "author_cost": "200",
            "platform_cost": "200",
            "shop_cost": "200"
          }
        }
      ],
      "main_status": "3",
      "main_status_desc": "已全部发货",
      "only_platform_cost_amount": "100",
      "order_amount": "20500",
      "order_id": "6917533224570258991",
      "order_level": "2",
      "order_status": "3",
      "order_status_desc": "已发货",
      "original_shop_id": "1234",
      "packing_amount": "1",
      "packing_charge_amount": "100",
      "pay_amount": "20500",
      "platform_cost_amount": "0",
      "post_amount": "500",
      "post_insurance_amount": "已全部发货",
      "post_origin_amount": "500",
      "post_promotion_amount": "0",
      "promotion_amount": "0",
      "promotion_detail": {
        "kol_discount_detail": {
          "coupon_amount": "0",
          "coupon_info": [
            {
              "coupon_activity_id": "47813206821235",
              "coupon_amount": "100",
              "coupon_id": "4781320682406",
              "coupon_meta_id": "43543523532",
              "coupon_name": "优惠券",
              "coupon_type": "1",
              "credit": "0",
              "discount": "0.1",
              "extra_map": {},
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "0",
                "shop_cost": "0"
              },
              "threshold": "0"
            }
          ],
          "full_discount_amount": "100",
          "full_discount_info": [
            {
              "campaign_activity_id": "4781320682406083610",
              "campaign_amount": "100",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "150",
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "50",
                "shop_cost": "50"
              }
            }
          ],
          "redpack_amount": "0",
          "redpack_info": [
            {
              "redpack_amount": "100",
              "redpack_trans_id": "675657456546547",
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "100",
                "shop_cost": "0"
              }
            }
          ],
          "total_amount": "200"
        },
        "platform_discount_detail": {
          "allowance_amount": "0",
          "coupon_amount": "100",
          "coupon_info": [
            {
              "coupon_amount": "100",
              "coupon_id": "4781320682406",
              "coupon_meta_id": "43543523532",
              "coupon_name": "优惠券",
              "coupon_type": "1",
              "credit": "0",
              "discount": "0.1",
              "extra_map": {},
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "0",
                "shop_cost": "0"
              },
              "threshold": "9"
            }
          ],
          "full_discount_amount": "0",
          "full_discount_info": [
            {
              "campaign_amount": "200",
              "campaign_id": "4781320682406083640",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "150",
              "campaign_type": "150",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "0",
                "shop_cost": "100"
              }
            }
          ],
          "gold_coin_amount": "0",
          "official_deduction_amount": "0",
          "redpack_amount": "100",
          "redpack_info": [
            {
              "redpack_amount": "100",
              "redpack_trans_id": "675657456546547",
              "share_discount_cost": {
                "author_cost": "100",
                "platform_cost": "0",
                "shop_cost": "0"
              }
            }
          ],
          "total_amount": "100",
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
              "credit": "0",
              "discount": "0.1",
              "extra_map": {},
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "100",
                "shop_cost": "0"
              },
              "threshold": "0"
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
                "author_cost": "0",
                "platform_cost": "0",
                "shop_cost": "0"
              }
            }
          ],
          "redpack_amount": "0",
          "redpack_info": [
            {
              "redpack_amount": "0",
              "redpack_trans_id": "675657456546547",
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
      "shop_cost_amount": "0",
      "shop_id": "94956",
      "shop_name": "订单专用_测试店三",
      "sku_order_list": [
        {
          "author_cost_amount": "0",
          "campaign_info": [
            {
              "campaign_activity_id": "4781320682406083612",
              "campaign_amount": "200",
              "campaign_id": "3214324342342",
              "campaign_name": "XXX活动",
              "campaign_sub_type": "1",
              "campaign_type": "150",
              "extra_map": {},
              "share_discount_cost": {
                "author_cost": "0",
                "platform_cost": "100",
                "shop_cost": "100"
              }
            }
          ],
          "first_cid": "20005",
          "fourth_cid": "20174",
          "goods_price": "100",
          "item_num": "1",
          "main_status": "3",
          "main_status_desc": "已全部发货",
          "only_platform_cost_amount": "100",
          "order_amount": "600",
          "order_id": "4781320682406083640",
          "order_level": "3",
          "order_status": "3",
          "order_status_desc": "已发货",
          "order_type": "0",
          "order_type_desc": "普通订单",
          "origin_amount": "100",
          "out_product_id": "432655662343",
          "out_sku_id": "43564553",
          "packing_charge_amount": "100",
          "parent_order_id": "4781320682406083640",
          "pay_amount": "100",
          "platform_cost_amount": "0",
          "post_insurance_amount": "0",
          "product_id": "3473196049974326153",
          "product_name": "XX鞋子",
          "promotion_amount": "0",
          "promotion_detail": {
            "kol_discount_detail": {
              "coupon_amount": "0",
              "coupon_info": [
                {
                  "coupon_amount": "0",
                  "coupon_id": "4781320682406",
                  "coupon_meta_id": "43543523532",
                  "coupon_name": "优惠券",
                  "coupon_type": "1",
                  "credit": "0",
                  "discount": "0.1",
                  "extra_map": {},
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
                  },
                  "threshold": "0"
                }
              ],
              "full_discount_amount": "0",
              "full_discount_info": [
                {
                  "campaign_amount": "200",
                  "campaign_id": "4781320682406083640",
                  "campaign_name": "XX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "150",
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
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
            },
            "platform_discount_detail": {
              "allowance_amount": "0",
              "coupon_amount": "0",
              "coupon_info": [
                {
                  "coupon_amount": "0",
                  "coupon_id": "4781320682406",
                  "coupon_meta_id": "43543523532",
                  "coupon_name": "优惠券",
                  "coupon_type": "1",
                  "credit": "0",
                  "discount": "0.1",
                  "extra_map": {},
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
                  },
                  "threshold": "0"
                }
              ],
              "full_discount_amount": "0",
              "full_discount_info": [
                {
                  "campaign_amount": "XXX活动",
                  "campaign_id": "4781320682406083640",
                  "campaign_name": "XXX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "150",
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
                  }
                }
              ],
              "gold_coin_amount": "0",
              "official_deduction_amount": "0",
              "redpack_amount": "0",
              "redpack_info": [
                {
                  "redpack_amount": "0",
                  "redpack_trans_id": "675657456546547",
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
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
                  "credit": "0",
                  "discount": "0.1",
                  "extra_map": {},
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "100",
                    "shop_cost": "0"
                  },
                  "threshold": "0"
                }
              ],
              "full_discount_amount": "0",
              "full_discount_info": [
                {
                  "campaign_activity_id": "4781320682406083610",
                  "campaign_amount": "XXX活动",
                  "campaign_id": "4781320682406083640",
                  "campaign_name": "XXX活动",
                  "campaign_sub_type": "1",
                  "campaign_type": "150",
                  "share_discount_cost": {
                    "author_cost": "0",
                    "platform_cost": "0",
                    "shop_cost": "0"
                  }
                }
              ],
              "official_deduction_amount": "0",
              "redpack_amount": "0",
              "redpack_info": [
                {
                  "redpack_amount": "0",
                  "redpack_trans_id": "675657456546547",
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
          "promotion_pay_amount_details": [
            {
              "share_cost": {
                "platform_cost": "0",
                "shop_cost": "0"
              }
            }
          ],
          "promotion_platform_amount": "0",
          "promotion_redpack_amount": "100",
          "promotion_redpack_platform_amount": "0",
          "promotion_redpack_talent_amount": "100",
          "promotion_shop_amount": "0",
          "promotion_talent_amount": "0",
          "second_cid": "20174",
          "shop_cost_amount": "0",
          "sku_id": "3254535",
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
          "sum_amount": "100",
          "supplier_id": "fsgfgsdg",
          "third_cid": "20174"
        }
      ],
      "total_promotion_amount": "0"
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
  "sub_code": "isv.business-failed:5100802",
  "sub_msg": "拣货未完成"
}
```

## 备注
