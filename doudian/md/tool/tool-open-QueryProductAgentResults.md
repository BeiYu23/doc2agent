# 查询任务结果

> open.QueryProductAgentResults — 查询任务结果

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询任务结果 |
| 文档地址 | `/docs/doudian/tool/tool-open-QueryProductAgentResults` |
| 接口 ID | `doudian.tool.open.QueryProductAgentResults` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/QueryProductAgentResults` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/8429 |
| 更新日期 | `2026-07-31` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_id` | body | string | 否 | 任务id | `ac131` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 每页数量 | `10` |
| `extra` | body | string | 否 | 额外参数的原始 JSON 字符串(map)，可空；非空时透传为 JSON | `{"key": "value"}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/QueryProductAgentResults?app_key=your_appkey_here&method=open.QueryProductAgentResults&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status` | string | Runing/Success/Fail | `Runing` |
| `data` | string | 下游 data 原样透传(raw JSON) | `[{"task_id": "123"}]` |
| `code` | mixed | 状态码 | `0` |
| `message` | string | 状态信息 | `success` |
| `page_info` | string | 下游 page_info 原样透传(raw JSON) | `{"page": 1, "page_size": 10, "total_count": 50}` |
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
    "data": "[{\"task_id\": \"123\"}]",
    "extra": "{\"key\": \"value\"}",
    "message": "success",
    "page_info": "{\"page\": 1, \"page_size\": 10, \"total_count\": 50}",
    "status": "Runing"
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
