# 外呼计划生产信息查询

> member.queryOutboundAudiencePlan — 外呼计划生产信息查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 外呼计划生产信息查询 |
| 文档地址 | `/docs/doudian/sms/sms-member-queryOutboundAudiencePlan` |
| 接口 ID | `doudian.sms.member.queryOutboundAudiencePlan` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/queryOutboundAudiencePlan` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/6878 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_id` | body | mixed | 是 | 外呼人群包生产计划ID | `1821927192` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/queryOutboundAudiencePlan?app_key=your_appkey_here&method=member.queryOutboundAudiencePlan&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_status` | mixed | 任务状态,1：待生产，2:生产失败，3:生产成功，4:转化成功 | `4` |
| `download_link` | string | 加密明细下载链接，当任务状态为转化成功时才可以查询到 | `https://ddddd` |
| `fail_reason` | string | 失败原因 | `不好意思出错啦` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "download_link": "https://ddddd",
    "fail_reason": "不好意思出错啦",
    "task_status": "4"
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
