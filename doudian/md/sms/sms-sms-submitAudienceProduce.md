# 提交人群包圈选生产任务

> sms.submitAudienceProduce — 提交人群包圈选生产任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 提交人群包圈选生产任务 |
| 文档地址 | `/docs/doudian/sms/sms-sms-submitAudienceProduce` |
| 接口 ID | `doudian.sms.sms.submitAudienceProduce` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/submitAudienceProduce` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7786 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `audience_id` | body | string | 是 | 人群包id | `12312312` |
| `audience_type` | body | mixed | 是 | 人群包类型 0公域人群包 1私域人群包 2组合人群包 | `1` |
| `valid_period` | body | string | 是 | 生产包有效期，可用枚举：1d/3d/7d/15d/30d | `1d` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/submitAudienceProduce?app_key=your_appkey_here&method=sms.submitAudienceProduce&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `produce_id` | string | 生产包id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "produce_id": "123"
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
