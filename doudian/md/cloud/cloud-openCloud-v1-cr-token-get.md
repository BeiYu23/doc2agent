# openCloud.v1.cr.token.get

> 获取上传镜像仓库的临时token

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.v1.cr.token.get` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/4153 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `volc_account_id` | body | mixed | 否 | 如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100044514` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=openCloud.v1.cr.token.get&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `authorization_token` | string | 临时访问token | `"docker login cr-cn-beijing.volces.com -u OP1267075819788007@2100044514 -p eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6IklLREk6NTJGRjpVS01HOk1OSVg6V1NFNzo3QUtJOkVNR1I6VUMyQzpMRkNPOjNYWjI6RVZYMjpKQlRYIn0.eyJpc3MiOiJjci1pc3N1ZXIiLCJzdWIiOiJPUDEyNjcwNzU4MTk3ODgwMDdAMjEwMDA0NDUxNCIsImF1ZCI6WyJjciJdLCJleHAiOjE2ODYwMzQzOTksIm5iZiI6MTY4NjAzMDc5OSwiaWF0IjoxNjg2MDMwNzk5LCJqdGkiOiJEUU03bW9OemhjZFlPS09FIiwiaWRlbnRpdHlfdHlwZSI6ImFjY291bnQiLCJpZGVudGl0eV9hY2NvdW50X2lkIjoyMTAwMDQ0NTE0LCJpZGVudGl0eV91c2VyX2lkIjoyMTAwMDQ0NTE0fQ.GTOvGFRrkLxuWKZqNpd3klVfZpLQc8LNQbaFfRSv3N7yDt0ibba4cB9ww-zyLpA58ZExlscFvskcmbp012-Br1OY3f2Clr3K8zJmOdF9cy0WAWgbYOP9EfqpwLqOTqB90VQc5GtCdjBE0SraIdxAVH1YhNpPdjGLS8KOnZGIRTgL2SoFL28IDhKo2NYYa_rBk1go0L9Su23b7ARvyedcUDHGdUyWBPE2-xoI3gmPtgeQlH1E2wTJZE9Mmw1oCLQP-ksoVU6FukOLHHl1dADbWPPCZiAHlGEPOBejAL684Ezr1cnO3Fc16WBv928lLfVrlcrlLus84Rl7V5Z9NpGPKA"` |
| `expire_time` | string | 过期时间 | `2023-06-06T06:53:19Z` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "authorization_token": "\"docker login cr-cn-beijing.volces.com -u OP1267075819788007@2100044514 -p eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6IklLREk6NTJGRjpVS01HOk1OSVg6V1NFNzo3QUtJOkVNR1I6VUMyQzpMRkNPOjNYWjI6RVZYMjpKQlRYIn0.eyJpc3MiOiJjci1pc3N1ZXIiLCJzdWIiOiJPUDEyNjcwNzU4MTk3ODgwMDdAMjEwMDA0NDUxNCIsImF1ZCI6WyJjciJdLCJleHAiOjE2ODYwMzQzOTksIm5iZiI6MTY4NjAzMDc5OSwiaWF0IjoxNjg2MDMwNzk5LCJqdGkiOiJEUU03bW9OemhjZFlPS09FIiwiaWRlbnRpdHlfdHlwZSI6ImFjY291bnQiLCJpZGVudGl0eV9hY2NvdW50X2lkIjoyMTAwMDQ0NTE0LCJpZGVudGl0eV91c2VyX2lkIjoyMTAwMDQ0NTE0fQ.GTOvGFRrkLxuWKZqNpd3klVfZpLQc8LNQbaFfRSv3N7yDt0ibba4cB9ww-zyLpA58ZExlscFvskcmbp012-Br1OY3f2Clr3K8zJmOdF9cy0WAWgbYOP9EfqpwLqOTqB90VQc5GtCdjBE0SraIdxAVH1YhNpPdjGLS8KOnZGIRTgL2SoFL28IDhKo2NYYa_rBk1go0L9Su23b7ARvyedcUDHGdUyWBPE2-xoI3gmPtgeQlH1E2wTJZE9Mmw1oCLQP-ksoVU6FukOLHHl1dADbWPPCZiAHlGEPOBejAL684Ezr1cnO3Fc16WBv928lLfVrlcrlLus84Rl7V5Z9NpGPKA\"",
    "expire_time": "2023-06-06T06:53:19Z"
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
