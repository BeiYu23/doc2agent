# sms.saveSecondPartyAudience

> 保存二方人群

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.saveSecondPartyAudience` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/saveSecondPartyAudience` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7929 |
| 更新日期 | `2025-12-11` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `resource` | body | string | 是 | 人群资源 | `资源值` |
| `biz_source` | body | mixed | 是 | 二方业务域 | `0:抖店 1:罗盘 ...` |
| `resource_type` | body | mixed | 是 | 人群资源类型 | `0:url 1:uri ...` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/saveSecondPartyAudience?app_key=your_appkey_here&method=sms.saveSecondPartyAudience&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `audience_id` | string | 人群id | `1` |
| `produce_id` | string | 人群包生产信息id | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数异常（sub_code: isv.business-failed:628004000） | 检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "audience_id": "1",
    "produce_id": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:628004000",
  "sub_msg": "参数异常"
}
```

## 备注
