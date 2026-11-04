# open.unionIdToOpenId

> UnionId转成OpenId

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.unionIdToOpenId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/unionIdToOpenId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7611 |
| 更新日期 | `2025-07-17` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `union_id` | body | string | 否 | union_id | `327a11ff-4222-5ffa-9e74-7f630e06b697` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/unionIdToOpenId?app_key=your_appkey_here&method=open.unionIdToOpenId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `open_id` | string | open_id | `xxxxxxxxxxxxxxxxxx` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "open_id": "xxxxxxxxxxxxxxxxxx"
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
