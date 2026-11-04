# 查询短视频数据

> second.ecomInsight.queryShortVideoData — 查询短视频数据接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询短视频数据 |
| 文档地址 | `/docs/doudian/video/video-second-ecomInsight-queryShortVideoData` |
| 接口 ID | `doudian.video.second.ecomInsight.queryShortVideoData` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8182 |
| 更新日期 | `2026-04-08` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `filters` | body | array | 否 | 过滤 | `` |
| `  └ field` | body | string | 否 | 筛选字段名，必须在允许的筛选字段白名单内 | `share_cnt_7d` |
| `  └ option` | body | string | 否 | 筛选条件表达式 | `>100` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 每页条数，最多20 | `20` |
| `is_industry` | body | boolean | 否 | 是否行业数据 | `true` |
| `search` | body | array | 否 | 搜索 | `` |
| `  └ field` | body | string | 否 | 搜索字段名，必须在允许的搜索字段白名单内 | `video_title` |
| `  └ type` | body | string | 否 | 搜索类型，仅允许：fuzzy（模糊搜索，LIKE '%value%'）、exact（精确匹配） | `fuzzy` |
| `  └ value` | body | string | 否 | 搜索值。为 null 时该条搜索条件被跳过 | `海` |
| `sort` | body | array | 否 | 排序条件 | `` |
| `  └ order` | body | string | 否 | 排序方向，仅允许 asc 或 desc（不区分大小写）。默认 desc | `desc` |
| `  └ aggregation` | body | string | 否 | 聚合函数名，当排序字段是聚合指标时需传入。支持 sum、avg、count_distinct | `count_distinct` |
| `  └ field` | body | string | 否 | 排序字段名 | `key_word` |
| `group_by` | body | array | 否 | 聚合分组字段列表，必须至少包含一个字段。目前仅支持聚合查询模式，不传将报错 | `key_word` |
| `metrics` | body | array | 否 | 聚合指标列表，定义需要计算的聚合字段 | `` |
| `  └ aggregation` | body | string | 否 | 聚合方式，仅允许以下 3 种（不区分大小写）：sum、avg、count_distinct | `sum` |
| `  └ field` | body | string | 否 | 聚合字段名，必须在允许的聚合字段白名单内（见附录） | `share_cnt_7d` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.queryShortVideoData&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 业务数据，成功时返回，失败时为 null | `` |
| `msg` | string | 消息 | `xxx` |
| `code` | mixed | 状态码 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "field_values": "\"xxxxx<SEP>xxx<SEP>0-20000<SEP>0-20000<SEP>0-20000\",  \"xxxxx<SEP>xxx<SEP>0-20000<SEP>0-20000<SEP>0-20000\"",
      "fields": "\"key_word\",\"video_id\",\"sum_share_cnt_7d\",\"avg_share_cnt_7d\",  \"count_distinct_key_word\"",
      "page": "1",
      "page_size": "20",
      "request_id": "req_be5ce4ac672f4325a2ff9961fa4cf112",
      "total": "12313"
    },
    "msg": "xxx"
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
