# sms.queryAudienceByCondition

> 查询人群信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.queryAudienceByCondition` |
| 中文名 | 查询人群信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/queryAudienceByCondition` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6681 |
| 更新日期 | `2025-10-17` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `match_search` | body | string | 否 | 人群包名称查询 | `自定义人群包` |
| `audience_id` | body | string | 否 | 人群包id | `22074278516698983` |
| `create_time_range` | body | object | 否 | 创建时间 | `` |
| `  └ start_time_unix` | body | string | 否 | 开始时间，秒级时间戳 | `1719763200` |
| `  └ end_time_unix` | body | string | 否 | 结束时间，秒级时间戳 | `1719763200` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 单页容纳记录数 | `20` |
| `query_audience_type` | body | mixed | 否 | 查询人群包类型 ISVDefault=1 // isv默认人群包，包含AudienceType 1、5 OfficalRecommended=2 // 官方推荐人群包，包含AudienceType 2 | `1` |
| `include_audience_ids` | body | array | 否 | 最多50个 | `[1]` |
| `exclude_audience_ids` | body | array | 否 | 最多50个 | `[1]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/queryAudienceByCondition?app_key=your_appkey_here&method=sms.queryAudienceByCondition&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 结果总数 | `100` |
| `results` | array | 结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:628002001） | 请正确输入参数 |
| `40004` | 非法的参数 / 请求非法（sub_code: isv.parameter-invalid:628005600） | 请正确输入参数 |
| `80000` | 风控拦截 / 系统不可用拦截（sub_code: isv.risk-control-failed:628004410） | 待系统恢复 |

## 响应示例

成功：

```json
{
  "data": {
    "results": [
      {
        "audience_id": "22074278516698983",
        "audience_name": "自定义人群",
        "audience_status": "1",
        "audience_type": "1",
        "content_desc": "测试人群",
        "create_time_unix": "1719763200",
        "label_list": [
          {
            "extra_map": {},
            "label_id": "1",
            "label_list": [
              {
                "extra_map": {},
                "label_id": "1",
                "label_list": [
                  {
                    "extra_map": {},
                    "label_id": "1",
                    "logic_operation": "1",
                    "param_list": [
                      {
                        "param_id": "1",
                        "param_name": "参数名称",
                        "param_str": "''",
                        "sub_param_list": [
                          {
                            "param_id": "1",
                            "param_name": "河南省",
                            "param_str": "河南省"
                          }
                        ]
                      }
                    ]
                  }
                ],
                "logic_operation": "1",
                "param_list": [
                  {
                    "param_id": "4",
                    "param_name": "中华地区",
                    "sub_param_list": [
                      {
                        "param_id": "1",
                        "param_name": "河南省",
                        "param_str": "\"\""
                      }
                    ]
                  }
                ]
              }
            ],
            "logic_operation": "1",
            "param_list": [
              {
                "param_desc": "\"\"",
                "param_id": "1",
                "param_name": "\"\"",
                "param_str": "\"\"",
                "sub_param_list": [
                  {
                    "param_id": "1",
                    "param_name": "\"\"",
                    "param_str": "\"\""
                  }
                ]
              }
            ]
          }
        ],
        "logic_operation": "1",
        "shop_id": "12345",
        "update_time_unix": "1719763200"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.missing-parameter:628002001",
  "sub_msg": "参数错误"
}
```

## 备注
