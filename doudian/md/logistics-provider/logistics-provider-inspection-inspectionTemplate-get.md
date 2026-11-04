# 获取检测模版

> inspection.inspectionTemplate.get — 获取检测模版

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取检测模版 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-inspection-inspectionTemplate-get` |
| 接口 ID | `doudian.logistics-provider.inspection.inspectionTemplate.get` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/inspectionTemplate/get` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7341 |
| 更新日期 | `2025-03-07` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_code` | body | string | 是 | 业务身份，固定值，由对接运营/研发提供 | `second_luxury` |
| `task_type` | body | string | 是 | 任务类型，固定值，由对接运营/研发提供 | `each_goods_inspection` |
| `order_code` | body | string | 否 | 订单码 | `123123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/inspectionTemplate/get?app_key=your_appkey_here&method=inspection.inspectionTemplate.get&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `inspection_template` | object | 检测模版信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:30000） | 参考官网使用文档 |
| `20000` | 系统错误（sub_code: isp.service-error:50000） | 联系相关运营、技术解决 |

## 响应示例

成功：

```json
{
  "data": {
    "inspection_template": {
      "collection_code": "7409903349104361778_1",
      "collection_name": "钟表类商品质检标准",
      "inspection_flow_list": [
        {
          "flow_id": "7409900754275909915",
          "flow_name": "基础信息",
          "inspection_item_list": [
            {
              "is_must_inspection": "false",
              "item_code": "7468357016798314771_2",
              "item_detail": "标准项详情",
              "item_name": "机身外观",
              "material_rule_list": [
                {
                  "is_must": "false",
                  "lower_limit": "0",
                  "material_name": "图片",
                  "material_rule_id": "7409896542142284069",
                  "material_type": "1",
                  "select_item_list": [
                    {
                      "select_code": "item_1_xx",
                      "select_desc": "测试名称"
                    }
                  ],
                  "size_limit": "1",
                  "upper_limit": "100"
                }
              ],
              "national_standard": "依据标准",
              "operate_example": [
                {
                  "example_name": "操作示例名称",
                  "url": "url"
                }
              ],
              "operate_example_list": [
                {
                  "example_name": "操作示例名称",
                  "url": "操作示例url"
                }
              ],
              "operate_explain": "操作说明",
              "qualified_rule_explain": "合格规则解释",
              "qualified_rule_list": [
                {
                  "input_value": "5",
                  "rule_code": "规则code",
                  "rule_id": "231231",
                  "rule_index": "1",
                  "rule_name": "重量",
                  "rule_op": ">",
                  "rule_unit": "克",
                  "rule_value": "10",
                  "value_lower_limit": "500",
                  "value_upper_limit": "100"
                }
              ],
              "qualified_type": "1",
              "unqulified_reason_list": [
                {
                  "certificate_lower_limit": "1",
                  "certificate_upper_limit": "10",
                  "fault_level": "1",
                  "is_upload_certificate": "false",
                  "quality_level": "1",
                  "reason": "缺少效期标签",
                  "reason_id": "3643212345",
                  "target_object_list": "目标对象列表"
                }
              ]
            }
          ],
          "operate_example_list": [
            {
              "example_name": "示例名称",
              "url": "操作示例文件url"
            }
          ],
          "operate_explain": "操作说明"
        }
      ],
      "is_need_remark": "false",
      "is_need_unqualified_count": "false",
      "sample_info": {
        "sample_count_list": [
          {
            "accept_count": "1",
            "code": "抽样code",
            "name": "抽样名称",
            "sample_count": "1"
          }
        ]
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:30000",
  "sub_msg": "缺少必填参数"
}
```

## 备注
