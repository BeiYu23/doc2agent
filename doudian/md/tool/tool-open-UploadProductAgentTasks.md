# open.UploadProductAgentTasks

> 上传任务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.UploadProductAgentTasks` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/UploadProductAgentTasks` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/8428 |
| 更新日期 | `2026-07-31` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tasks` | body | string | 是 | Task 数组的原始 JSON 字符串 | `[{"xx": "xx"}]` |
| `task_type` | body | string | 否 | 任务类型：single_day(单天，不填默认 single_day)/multi_day(多天) | `multi_day` |
| `start_date` | body | string | 否 | 开始日期(包含)，task_type=multi_day 时必填，格式 20270701 | `20260713` |
| `end_date` | body | string | 否 | 结束日期(包含)，task_type=multi_day 时必填，格式 20270727 | `20260726` |
| `extra` | body | string | 否 | 额外参数的原始 JSON 字符串(map)，可空；非空时透传为 JSON | `{"key": "value"}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/UploadProductAgentTasks?app_key=your_appkey_here&method=open.UploadProductAgentTasks&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 状态码 | `0` |
| `message` | string | 状态信息 | `success` |
| `data` | string | 下游 data 原样透传(raw JSON) | `[{"id": "xx", "xx": "xx"}]` |
| `extra` | string | 下游 extra 原样透传(raw JSON) | `{"key": "value"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": "[{\"id\": \"xx\", \"xx\": \"xx\"}]",
    "extra": "{\"key\": \"value\"}",
    "message": "success"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
