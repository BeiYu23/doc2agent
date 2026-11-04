# sms.sign.apply.revoke

> 撤销短信签名申请单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.sign.apply.revoke` |
| 中文名 | 撤销短信签名申请单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sign/apply/revoke` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1519 |
| 更新日期 | `2026-03-24` |

## 接口说明

- 文档书: 短信API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `sms_sign_apply_id` | body | string | 是 | 申请单id | `1234435435` |
| `version` | body | string | 否 | 版本号 | `v2` |
| `shop_sub_account` | body | string | 否 | 商家消息组，不传则默认使用商家消息组 | `sjdofajs` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/apply/revoke?app_key=your_appkey_here&method=sms.sign.apply.revoke&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 是否成功 0表示成功 | `0` |
| `message` | string | 说明 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 628005100:status is not reviewing（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |
| `50002` | 业务处理失败 / 628002001:您输入参数不正确，请检查后重试（sub_code: isv.business-failed:628002001） | 请检查输入参数 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "message": "成功"
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
  "sub_code": "isv.business-failed:628005100",
  "sub_msg": "628005100:status is not reviewing"
}
```

## 备注
