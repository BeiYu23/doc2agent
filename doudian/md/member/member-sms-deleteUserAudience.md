# sms.deleteUserAudience

> 删除人群包

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.deleteUserAudience` |
| 中文名 | 删除人群包 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/deleteUserAudience` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6773 |
| 更新日期 | `2024-08-14` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `audience_id` | body | string | 是 | 人群包id | `123456789` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/deleteUserAudience?app_key=your_appkey_here&method=sms.deleteUserAudience&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 该人群包不允许删除（sub_code: isv.parameter-invalid:628005604） | 此类型人群包不允许删除 |
| `80000` | 风控拦截 / 系统不可用拦截（sub_code: isv.risk-control-failed:628004410） | 待系统恢复 |
| `40004` | 非法的参数 / 请求资源非法（sub_code: isv.parameter-invalid:628005600） | 请求资源非法 |

## 响应示例

成功：

```json
{
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:628005604",
  "sub_msg": "该人群包不允许删除"
}
```

## 备注
