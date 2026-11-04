# supplyCenter.base.productUpdateRule

> 获取类目下发布规则

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.base.productUpdateRule` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5338 |
| 更新日期 | `2023-11-15` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 是 | 类目id | `20219` |
| `spu_id` | body | number | 否 | spu_id | `23291` |
| `standard_brand_id` | body | number | 否 | 品牌ID | `20319` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.productUpdateRule&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `recommend_name_rule` | object | 商品标题推荐规则 | `` |
| `reference_price_rule` | object | 参考价相关规则 | `` |
| `product_spec_rule` | object | 商品规格约束 | `` |
| `spu_control_rule` | object | spu管控规则 | `` |
| `component_template_rule` | object | 商品尺码模板配置规则 | `` |
| `sku_rule` | object | sku规则 | `` |
| `main_image_three_to_four_rule` | object | 商品主图3:4配置规则 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照商品发布规则接口（sub_code: isv.parameter-invalid:66666） | https://op.jinritemai.com/docs/api-docs/14/1614 |

## 响应示例

成功：

```json
{
  "data": {
    "component_template_rule": {
      "is_show": "true",
      "must_input": "false"
    },
    "main_image_three_to_four_rule": {
      "is_show": "true",
      "must_input": "false"
    },
    "product_spec_rule": {
      "max_spec_num_limit": "3",
      "required_spec_details": [
        {
          "is_required": "false",
          "measure_templates": [
            {
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
                        "max": "100",
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
      "spec_single_limit": "200",
      "support_property_diy": "false",
      "support_property_sequence_variable": "true"
    },
    "recommend_name_rule": {
      "property_ids": "[365,3987]",
      "satisfy_prefix": "true",
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
      "sku_classification_rule": {
        "enable": "true",
        "must_select": "true",
        "options": [
          {
            "description": "\"SKU为单个商品，与标题、主图、叶子类目描述一致，为该商品主要售卖款式\"",
            "example": "\"标题/主图主要售卖洗发水，洗发水1瓶为主售款（单品）。主要销售成箱装饮料，饮料1箱为主售款单品\"",
            "name": "\"主售款（单品）\"",
            "value": "\"main_sale_single_product\""
          }
        ]
      }
    },
    "spu_control_rule": {
      "control_type": "2",
      "no_need_audit_spu": "false",
      "support_create_spu": "true",
      "support_rectify_spu": "false",
      "support_report_spu": "true",
      "support_spu_product": "true"
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
  "sub_code": "isv.parameter-invalid:66666",
  "sub_msg": "参照商品发布规则接口"
}
```

## 备注
