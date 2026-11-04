# product.getProductUpdateRule

> 查询商品发布规则

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.getProductUpdateRule` |
| 中文名 | 查询商品发布规则 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getProductUpdateRule` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1614 |
| 更新日期 | `2026-09-14` |

## 接口说明

- 文档书: 商品API（版本 V8.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 是 | 类目id | `20219` |
| `senses` | body | array | 否 | 闪购定制参数，普通发品忽略 | `1001` |
| `standard_brand_id` | body | mixed | 否 | 品牌id | `20319` |
| `spu_id` | body | mixed | 否 | spu_id | `23291` |
| `option` | body | object | 否 | 规则定制参数 | `` |
| `  └ need_shipping_origin_id_list` | body | boolean | 否 | 是否需要发货地id列表 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getProductUpdateRule?app_key=your_appkey_here&method=product.getProductUpdateRule&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fulfillment_rule` | object | 履约规则 | `` |
| `recommend_name_rule` | object | 商品标题推荐规则 | `` |
| `after_sale_rule` | object | 售后服务规则 | `` |
| `reference_price_rule` | object | 参考价相关规则 | `` |
| `spu_control_rule` | object | spu管控规则 | `` |
| `product_spec_rule` | object | 商品规格约束 | `` |
| `component_template_rule` | object | 商品尺码模板配置规则 | `` |
| `main_image_three_to_four_rule` | object | 商品主图3:4配置规则 | `` |
| `gold_price_rule` | object | 金价信息，计价金类目下sku价格可以按照公式进行计算（价格=克重*每克价格+加工费），本字段提供相关信息 | `` |
| `extra_rule` | object | 其他规则 | `` |
| `trade_rule` | object | 交易相关的规则 | `` |
| `sku_rule` | object | sku规则 | `` |
| `qualification_rule` | array | 资质规则，类目属性影响资质必填和资质属性必填 | `` |
| `pick_up_method_rule` | object | 提取方式规则 | `` |
| `merchant_cargo_rule` | object | 商家货品规则 | `` |
| `material_rule` | object | 素材规则 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010013:获取账号信息失败（sub_code: isv.business-failed:2010013） | 重试 |
| `50002` | 业务处理失败 / 2010001:获取类目标失败（sub_code: isv.business-failed:2010001） | 重试 |
| `50002` | 业务处理失败 / 2010004:类目ID不合法（sub_code: isv.business-failed:2010004） | 检查类目id |
| `50002` | 业务处理失败 / 2010346:未绑定商家仓（sub_code: isv.business-failed:2010346） | 检查商家仓 |
| `50002` | 业务处理失败 / 2010109:当前类目未开通主图3:4上传功能，请删除主图3:4（sub_code: isv.business-failed:2010109） | 删除主图3:4后重新发布 |
| `50002` | 业务处理失败 / 未查询到该类目（sub_code: isv.business-failed:110201001） | 请检查类目id |
| `50002` | 业务处理失败 / 110210112:商品类目不符合平台规则，请重新选择商品类目（sub_code: isv.business-failed:110210112） | 检查类目是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "after_sale_rule": {
      "allergy_return_v2_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "支持过敏包退",
            "value": "0-不支持，1-支持"
          }
        ]
      },
      "large_product_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "支持大件商品",
            "value": "0-不支持大件，1-支持大件"
          }
        ]
      },
      "supply_day_return_rule": {
        "enable": "true",
        "options": [
          {
            "name": "7天无理由退货（使用后不支持）",
            "value": "7-5"
          }
        ]
      },
      "three_guarantees": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "寄修",
            "options": [
              {
                "name": "180天",
                "value": "180"
              }
            ],
            "value": "1"
          }
        ]
      }
    },
    "component_template_rule": {
      "correct_size_suggestion": {
        "available": "true",
        "options": [
          {
            "sizes": "[0.5,1,2]",
            "value_id": "1",
            "value_name": "尺码偏大"
          }
        ]
      },
      "interval_size_symbol": "[\\\"-\\\",\\\"~\\\",\\\"/\\\",\\\"～\\\",\\\"—\\\"]",
      "is_show": "true",
      "must_input": "false",
      "size_dimension_range": {},
      "size_dimension_rule": {},
      "size_dimensions": {
        "other_dimensions": "[\"肩宽(cm)\", \"衣长(cm)\"]",
        "useful_dimensions": "[\"身高（cm）\",\"体重(斤)\"]"
      },
      "support_template_sub_type": "clothing"
    },
    "extra_rule": {
      "c2b_customize_rule": {
        "app_list": [
          {
            "name": "小程序名称",
            "value": "abcde"
          }
        ],
        "enable": "true",
        "selected_fulfillment_rule": {
          "normal_rule": {
            "delay_options": "[1, 2, 3]",
            "deny_description": "不可用原因",
            "description": "定制商品的发货时间从消费者上传定制信息后开始计算，为提升转化，商详页的时效文案展示为“上传定制信息后x天内发货”，定制商品仅支持配置48小时以上的时间。",
            "display": "true",
            "support": "true"
          }
        },
        "supply_day_return_selector": [
          {
            "name": "七天无理由退货（定制类不支持）",
            "value": "7-6"
          }
        ]
      },
      "home_install_service_rule": {
        "must_select": "true",
        "options": [
          {
            "name": "选择平台合作服务商",
            "options": [
              {
                "name": "模版1",
                "value": "1"
              }
            ],
            "value": "-"
          }
        ]
      }
    },
    "fulfillment_rule": {
      "delay_rule": {
        "config_type": "1",
        "config_value": "1675353599",
        "end_time": "1675353599",
        "start_time": "1675353599"
      },
      "normal_rule": {
        "delay_options": "[9999,1,2]",
        "delay_rule": {
          "config_type": "1",
          "config_value": "1675526399",
          "end_time": "1675353599",
          "start_time": "1673625600"
        },
        "is_special_delay_option": "false",
        "sku_rule": {
          "absolute_max_date": "1761753600",
          "absolute_min_date": "1756656000",
          "relative_max_delay": "90",
          "relative_min_delay": "2",
          "support": "true",
          "support_range_option": "true"
        },
        "support": "true"
      },
      "product_presell_rule": {
        "delivery_after_pay_config": {
          "max_delivery_days": "15",
          "max_presell_end_days": "30",
          "min_delivery_days": "2",
          "need_audit": "true"
        },
        "delivery_after_presell_config": {
          "max_delivery_days": "15",
          "max_presell_end_days": "30",
          "min_delivery_days": "2",
          "need_audit": "true"
        },
        "min_presell_price": "2000",
        "support": "false",
        "support_delivery_after_pay": "true",
        "support_delivery_after_presell": "false"
      },
      "shipping_origin_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "单一发货地/多发货地组合",
            "options": [
              {
                "name": "浙江省杭州市余杭区XXX大厦",
                "value": "123"
              }
            ],
            "value": "1"
          }
        ]
      },
      "sku_presell_rule": {
        "delivery_after_pay_config": {
          "max_delivery_days": "15",
          "max_presell_end_days": "30",
          "min_delivery_days": "2",
          "need_audit": "false"
        },
        "delivery_after_presell_config": {
          "max_delivery_days": "15",
          "max_presell_end_days": "30",
          "min_delivery_days": "2",
          "need_audit": "true"
        },
        "min_presell_price": "2000",
        "support": "false",
        "support_delivery_after_pay": "false",
        "support_delivery_after_presell": "false"
      },
      "step_rule": {
        "delay_options": "[9999,1,2]",
        "delay_rule": {
          "config_type": "1",
          "config_value": "1",
          "end_time": "123",
          "start_time": "121"
        },
        "is_special_delay_option": "false",
        "multi_times": [
          {
            "time_desc": "5天内发",
            "time_type": "5"
          }
        ],
        "step_max_delay": "15",
        "step_min_delay": "7",
        "support": "false"
      },
      "time_sku_presell_with_normal_rule": {
        "min_presell_price": "2000",
        "support": "true",
        "time_sku_spec_detial": [
          {
            "is_presell_spec": "false",
            "spec_code": "product_time_spec_48h",
            "spec_value": "48小时内发货"
          }
        ],
        "time_sku_spec_name": "发货时效"
      },
      "time_sku_pure_presell_rule": {
        "min_presell_price": "2000",
        "support": "true",
        "time_sku_spec_detial": [
          {
            "is_presell_spec": "true",
            "spec_code": "product_time_spec_48h",
            "spec_value": "5天内发货"
          }
        ],
        "time_sku_spec_name": "发货时效"
      }
    },
    "gold_price_rule": {
      "is_required": "true",
      "is_show": "true",
      "price_rules": [
        {
          "can_select": "true",
          "desc": "投资金基础金价：100元/克",
          "type": "1",
          "value": "12300"
        }
      ],
      "sell_property_id": "4530"
    },
    "main_image_three_to_four_rule": {
      "is_show": "true",
      "must_input": "false"
    },
    "material_rule": {
      "food_label_image_rule": {
        "required": "true",
        "support": "false"
      }
    },
    "merchant_cargo_rule": {
      "cargo_can_bind_max_times": "20",
      "cargo_can_bind_product_num_max": "100",
      "sku_art_cargo_num_max": "100",
      "sku_art_cargo_num_min": "1",
      "sku_art_cargo_required": "true"
    },
    "pick_up_method_rule": {
      "virtual_goods_rule": {
        "support_show_checkout_entry": "true"
      }
    },
    "product_spec_rule": {
      "all_spec_pic_required": "true",
      "max_spec_num_limit": "3",
      "required_spec_details": [
        {
          "is_required": "false",
          "measure_templates": [
            {
              "display_name": "xx模版",
              "template_id": "12",
              "value_modules": [
                {
                  "input_type": "input",
                  "module_id": "1",
                  "prefix": "\"\"",
                  "suffix": "\"\"",
                  "units": [
                    {
                      "unit_id": "2",
                      "unit_name": "g"
                    }
                  ],
                  "validate_rule": {
                    "data_type": "integer",
                    "max": "100",
                    "min": "2",
                    "precision": "0",
                    "unit_rules": [
                      {
                        "max": "10",
                        "min": "2",
                        "unit_id": "2"
                      }
                    ]
                  },
                  "values": [
                    {
                      "value_name": "8G"
                    }
                  ]
                }
              ]
            }
          ],
          "navigation_properties": [
            {
              "property_id": "1",
              "property_name": "色系"
            }
          ],
          "need_paging_query_value": "false",
          "property_default_display": "1",
          "property_values": [
            {
              "sell_property_value_id": "1234",
              "sell_property_value_name": "红色",
              "value_pic": {
                "pic_type": "rgb",
                "pic_value": "#FFFF"
              }
            }
          ],
          "sell_property_id": "123",
          "sell_property_name": "颜色",
          "support_diy": "false",
          "support_remark": "true",
          "value_display_style": "cascader"
        }
      ],
      "spec_combination_limit": "450",
      "spec_rule_code": "\"\"",
      "spec_single_limit": "200",
      "support_property_diy": "false",
      "support_property_sequence_variable": "false"
    },
    "qualification_rule": [
      {
        "is_qianchuan_need": "true",
        "is_required": "true",
        "key": "1234567",
        "matchable_rule": [
          {
            "property_effect": {},
            "rule_clause": {}
          }
        ],
        "name": "3C证书编号",
        "text_list": "经营进口商品，需提供近一年内的中华人民共和国海关进口货物报关单。报关单上应展现对应品牌名称，及商品名称。"
      }
    ],
    "recommend_name_rule": {
      "prefix_brand_unauth_can_sel": "false",
      "prefix_prop_has_brand": "false",
      "property_ids": "[365, 3987]",
      "satisfy_prefix": "true",
      "title_illegal_keyword_rule": [
        {
          "keywords": "[\"  \",\"\\n\"]",
          "keywords_in_prefix": "[\" \",\"\\n\"]",
          "keywords_in_suffix": "[\" \",\"\\n\"]",
          "tip": "商品标题不允许出现2个及以上连续空格"
        }
      ],
      "title_limit_rule": {
        "max_length": "60",
        "min_length": "0"
      }
    },
    "reference_price_rule": {
      "certificate_types": {},
      "is_required": "true",
      "is_support": "true",
      "lower_sku_price_times": "10"
    },
    "sku_rule": {
      "area_stock_require": "true",
      "gift_suit_detail_config": {
        "gift_suit_detail_fields": [
          {
            "desc": "净含量",
            "field_name": "net_content",
            "in_template": "true",
            "unit_list": "[\"g\", \"ml\"]"
          }
        ],
        "max_gift_suit_detail_len": "50",
        "max_name_len": "40"
      },
      "gift_suit_detail_require": "true",
      "sku_classification_rule": {
        "enable": "true",
        "must_select": "false",
        "options": [
          {
            "description": "\"SKU为单个商品，与标题、主图、叶子类目描述一致，为该商品主要售卖款式\"",
            "example": "\"标题/主图主要售卖洗发水，洗发水1瓶为主售款（单品）。主要销售成箱装饮料，饮料1箱为主售款单品\"",
            "name": "\"主售款（单品）\"",
            "value": "\"main_sale_single_product\""
          }
        ]
      },
      "sku_picture_rule": {
        "require_type": "1",
        "support": "true"
      },
      "support_barcode": "true",
      "support_spec_model_code": "true"
    },
    "spu_control_rule": {
      "control_type": "2",
      "no_need_audit_spu": "false",
      "support_create_spu": "true",
      "support_rectify_spu": "false",
      "support_report_spu": "true",
      "support_spu_product": "true"
    },
    "trade_rule": {
      "support_auto_charge_rule": {
        "disabled": "1",
        "value": "false"
      }
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
  "sub_code": "isv.business-failed:2010013",
  "sub_msg": "2010013:获取账号信息失败"
}
```

## 备注
