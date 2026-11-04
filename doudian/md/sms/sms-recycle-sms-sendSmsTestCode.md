# 发送短信验证码

> recycle.sms.sendSmsTestCode — 发送短信验证码

| 元信息 | 值 |
| --- | --- |
| 中文名 | 发送短信验证码 |
| 文档地址 | `/docs/doudian/sms/sms-recycle-sms-sendSmsTestCode` |
| 接口 ID | `doudian.sms.recycle.sms.sendSmsTestCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/sms/sendSmsTestCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7865 |
| 更新日期 | `2025-11-13` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sign` | body | string | 是 | 签名 | `抖音商城` |
| `template_id` | body | string | 是 | 模版id | `ST_XXXX` |
| `template_param` | body | string | 否 | 模版参数 | `{}` |
| `post_tel` | body | string | 是 | 明文手机号 | `12345678901` |
| `sms_account` | body | string | 是 | 消息组id | `12es` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/sms/sendSmsTestCode?app_key=your_appkey_here&method=recycle.sms.sendSmsTestCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
