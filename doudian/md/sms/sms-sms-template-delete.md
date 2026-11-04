# sms.template.delete

> 删除短信模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.template.delete` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/template/delete` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1518 |
| 更新日期 | `2026-04-17` |

## 接口说明

- 文档书: 短信API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `template_id` | body | string | 是 | 短信模板id | `7238746` |
| `version` | body | string | 否 | v2是新版本 | `v2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/template/delete?app_key=your_appkey_here&method=sms.template.delete&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 是否成功 0表示成功 | `0` |
| `message` | string | 说明 | `abc` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 参数不合法 |
| `40004` | 非法的参数 / 参数template_id对应模板不存在（sub_code: isv.parameter-invalid:7） | 参数template_id对应模板不存在 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "message": "abc"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:5",
  "sub_msg": "参数不合法"
}
```

## 备注
