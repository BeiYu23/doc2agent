# supplyChain.queryReturnOrderByOrderNo

> 通过售后单ID或者渠道交易单ID查询售后明细

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.queryReturnOrderByOrderNo` |
| 中文名 | 通过售后单ID或者渠道交易单ID查询售后明细 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/queryReturnOrderByOrderNo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/3360 |
| 更新日期 | `2026-03-05` |

## 接口说明

- 文档书: 供销平台API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `after_sale_order_no` | body | string | 否 | 售后单号，一定要注意是售后单号。 与渠道单号不能同时为空 | `GSH23031612561361` |
| `channel_trade_order_no` | body | string | 否 | 渠道交易单号，与售后单号不能同时为空 | `CT7211002433110327596` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getCatePropertyV2?app_key=your_appkey_here&method=product.getCatePropertyV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 是否成功 | `0` |
| `msg` | string | 接口是否成功 | `success` |
| `return_order_info_list` | array | 售后单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1000） | 重试 |
| `20000` | 系统错误 / 业务处理失败（可以直接展示给用户）（sub_code: isp.service-error:1040） | 根据提示处理 |
| `40004` | 非法的参数 / 参数问题（sub_code: isv.parameter-invalid:1020） | 修改参数 |
| `50002` | 业务处理失败 / 2000:（sub_code: isv.business-failed:2000） | 2000: |
| `50002` | 业务处理失败 / -1:（sub_code: isv.business-failed:-1） | -1: |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1015） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "category_id": "31918",
        "cid": "31918",
        "diy_type": "1",
        "feature_type_list": "[48]",
        "has_sub_property": "false",
        "important_type": "1",
        "measure_templates": [
          {
            "display_name": "xx模版",
            "input_rule": {
              "dependency_check_rules": [
                {
                  "rule_condition": {
                    "module_id": "0",
                    "operator": "\"\"",
                    "value": "\"\""
                  },
                  "rule_constraint": {
                    "err_msg": "\"\"",
                    "group_func": "\"\"",
                    "module_id": "0",
                    "operator": "\"\"",
                    "value": "\"\""
                  },
                  "template_id": "0"
                }
              ],
              "global_check_rules": [
                {
                  "err_msg": "\"\"",
                  "module_id": "0",
                  "operator": "\"\"",
                  "target_value": "\"\"",
                  "template_id": "0"
                }
              ]
            },
            "template_id": "23",
            "value_modules": [
              {
                "extra": {},
                "input_type": "input",
                "module_id": "123",
                "prefix": "\"\"",
                "suffix": "\"\"",
                "units": [
                  {
                    "unit_id": "1",
                    "unit_name": "克"
                  }
                ],
                "validate_rule": {
                  "data_type": "integer",
                  "max": "10",
                  "min": "2",
                  "precision": "2",
                  "time_format": "YYYY-MM-DD",
                  "unit_rules": [
                    {
                      "max": "10",
                      "min": "2",
                      "unit_id": "1"
                    }
                  ]
                },
                "value_required": "true",
                "values": [
                  {
                    "value_name": "棉"
                  }
                ]
              }
            ]
          }
        ],
        "multi_select_max": "5",
        "options": [
          {
            "name": "ON:THE BODY/安宝笛",
            "sequence": "2",
            "value": "1062254699",
            "value_id": "1"
          }
        ],
        "property_id": "14133",
        "property_name": "\"材质\"",
        "property_pic_rule": {
          "available": "true",
          "required": "true"
        },
        "property_type": "1",
        "relation_id": "1",
        "required": "0",
        "sequence": "2",
        "status": "1",
        "type": "text"
      }
    ],
    "tpl_type": "2"
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
  "sub_code": "isv.business-failed:1000",
  "sub_msg": "业务处理失败"
}
```

## 备注
