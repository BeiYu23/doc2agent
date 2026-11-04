# supplyChain.supplyProductV2.getProductUpdateRule

> 查询货品发布规则

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.getProductUpdateRule` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6671 |
| 更新日期 | `2025-01-16` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 否 | 类目ID(叶子类目) | `21455` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProductV2.getProductUpdateRule&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 返回码 | `1000` |
| `msg` | string | 返回信息 | `“”` |
| `product_spec_rule` | object | 商品规格的规则要求 必返回 + SpuRule控制部分信息 | `` |
| `component_template_rule` | object | 尺码模板配置规则 ComponentTemplateRule | `` |
| `after_sale_rule` | object | 售后相关规则 AfterSaleRule | `` |
| `delay_rule` | object | 延迟发货规则 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductUpdateRule] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[2010001] BizStatusMessage:[获取类目属性信息失败]}（sub_code: isv.business-failed:2000） | 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductUpdateRule] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[2010001] BizStatusMessage:[获取类目属性信息失败]} |
| `50002` | 业务处理失败 / 1020:参数异常，请检查后重试\|该接口灰度测试中，暂不支持（sub_code: isv.business-failed:1020） | 1020:参数异常，请检查后重试\|该接口灰度测试中，暂不支持 |

## 响应示例

成功：

```json
{
  "data": {
    "after_sale_rule": {
      "allergy_return_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "allergy_return_v2_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "authentic_guarantee_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "damage_order_return_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "large_product_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "quality_problem_return_time_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "red_ass_return_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "sale_channel_type_rule": {
        "default_value": "xxx",
        "enable": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "supply_day_return_rule": {
        "enable": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      },
      "three_guarantees": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "name": "xxx",
            "options": [
              {
                "name": "xxx",
                "value": "xxx"
              }
            ],
            "value": "xxx"
          }
        ]
      }
    },
    "code": "1000",
    "component_template_rule": {
      "is_show": "true",
      "must_input": "true",
      "support_template_sub_type": "xxx"
    },
    "delay_rule": {
      "config_type": "1",
      "config_value": "1",
      "enable": "false",
      "end_time": "1",
      "start_time": "1"
    },
    "msg": "“”",
    "product_spec_rule": {
      "display_spec": "true",
      "legal_spec_combination": "111",
      "max_spec_num_limit": "1",
      "required_spec_details": [
        {
          "is_required": "true",
          "measure_items": [
            {
              "is_default": "true",
              "max": "1",
              "measure_unit_id": "1",
              "measure_unit_name": "xx",
              "min": "1"
            }
          ],
          "measure_template": {
            "display_name": "1",
            "hint_text": "1",
            "related_sku_classification": "1",
            "template_id": "1",
            "unsupported_sku_classification": "1",
            "value_modules": [
              {
                "input_type": "1",
                "module_id": "1",
                "module_shading_words": "1",
                "prefix": "1",
                "suffix": "1",
                "unit_linkage": {},
                "units": [
                  {
                    "unit_id": "1",
                    "unit_name": "1"
                  }
                ],
                "validate_rule": {
                  "data_type": "xx",
                  "max": "1",
                  "min": "1",
                  "precision": "1",
                  "time_format": "1",
                  "unit_rules": [
                    {}
                  ]
                },
                "value_required": "1",
                "values": [
                  {
                    "value_name": "1"
                  }
                ]
              }
            ]
          },
          "measure_templates": [
            {
              "display_name": "1",
              "hint_text": "1",
              "related_sku_classification": "1",
              "template_id": "1",
              "unsupported_sku_classification": "1",
              "value_modules": [
                {
                  "input_type": "1",
                  "module_id": "1",
                  "module_shading_words": "1",
                  "prefix": "1",
                  "suffix": "1",
                  "unit_linkage": {},
                  "units": [
                    {
                      "unit_id": "18",
                      "unit_name": "L"
                    }
                  ],
                  "validate_rule": {
                    "data_type": "1",
                    "max": "1",
                    "min": "1",
                    "precision": "1",
                    "time_format": "1",
                    "unit_rules": [
                      {}
                    ]
                  },
                  "value_required": "1",
                  "values": [
                    {}
                  ]
                }
              ]
            }
          ],
          "navigation_properties": [
            {
              "property_id": "1",
              "property_name": "1"
            }
          ],
          "navigation_property_values": [
            {
              "children": [
                {
                  "sell_property_id": "11",
                  "value": {
                    "sell_property_value_id": "35497",
                    "sell_property_value_name": "白色",
                    "value_pic": {
                      "pic_type": "pic_type",
                      "pic_value": "pic_value"
                    }
                  }
                }
              ],
              "sell_property_id": "11",
              "value": {
                "sell_property_value_id": "111",
                "sell_property_value_name": "111",
                "value_pic": {
                  "pic_type": "11",
                  "pic_value": "11"
                }
              }
            }
          ],
          "need_paging_query_value": "true",
          "property_default_display": "true",
          "property_display_content": "111",
          "property_values": [
            {
              "sell_property_value_id": "xx",
              "sell_property_value_name": "xx",
              "value_pic": {
                "pic_type": "xx",
                "pic_value": "图片类型，\"url\"或\"rgb\""
              }
            }
          ],
          "sell_property_id": "111",
          "sell_property_name": "sell_property_name",
          "support_diy": "true",
          "support_remark": "true",
          "value_display_style": "111"
        }
      ],
      "spec_combination_limit": "1",
      "spec_rule_code": "111",
      "spec_single_limit": "1",
      "support_property_diy": "true",
      "support_property_sequence_variable": "true"
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
  "sub_code": "isv.business-failed:2000",
  "sub_msg": "2000:业务处理异常|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductUpdateRule] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[2010001] BizStatusMessage:[获取类目属性信息失败]}"
}
```

## 备注
