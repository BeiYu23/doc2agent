# 调用ISV云内应用

> microapp.invoke.cloudApi — 调用ISV云内应用接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 调用ISV云内应用 |
| 文档地址 | `/docs/doudian/cloud/cloud-microapp-invoke-cloudApi` |
| 接口 ID | `doudian.cloud.microapp.invoke.cloudApi` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/6523 |
| 更新日期 | `2024-05-27` |

## 接口说明

- 文档书: 电商云API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `interface_name` | body | string | 是 | 云内应用提供的接口名 | `testName` |
| `biz_param_json` | body | string | 是 | 入参，json字符串 | `{"name":"test}` |
| `use_test` | body | mixed | 是 | 是否调用至"测试环境"云内应用的接口 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getCatePropertyV2?app_key=your_appkey_here&method=product.getCatePropertyV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `biz_result_json` | string | 后端接口的返回值，json string | `{"age":12345}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `60000` | 触发限流，请稍后重试 / 触发商品流控（sub_code: isp.traffic-limited:1000207） | 联系平台同学 |
| `50002` | 业务处理失败 / 1000014:http client请求返回值非200（sub_code: isv.business-failed:1000014） | 联系平台同学 |
| `50002` | 业务处理失败 / 1000130:调用后端地址异常（sub_code: isv.business-failed:1000130） | 后端转发地址有问题，请检测是否在产品页面填写，并且确认后端服务是否启动成功 |
| `50002` | 业务处理失败 / 100000:参数错误（sub_code: isv.business-failed:100000） | 请再次检测参数问题 |
| `50002` | 业务处理失败 / 1000301:没有匹配上应用申请的域名，请检测是否有申请（sub_code: isv.business-failed:1000301） | 没有找到已申请的入云服务单，请先申请 |
| `50002` | 业务处理失败 / 1000201:request转换list<>失败，key:available_coupons（sub_code: isv.business-failed:1000201） | 参数转换失败，确认一下实际入参与服务单入参是否一致 |
| `50002` | 业务处理失败 / 1000131:调用失败（sub_code: isv.business-failed:1000131） | 1000131:调用失败 |

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
        "has_sub_property": "false",
        "important_type": "1",
        "measure_templates": [
          {
            "display_name": "xx模版",
            "template_id": "23",
            "value_modules": [
              {
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
  "code": 60000,
  "msg": "触发限流，请稍后重试",
  "sub_code": "isp.traffic-limited:1000207",
  "sub_msg": "触发商品流控"
}
```

## 备注
