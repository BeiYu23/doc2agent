# sms.sign.delete

> 删除短信签名

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.sign.delete` |
| 中文名 | 删除短信签名 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sign/delete` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1520 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `sign` | body | string | 是 | 签名 | `abc` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/delete?app_key=your_appkey_here&method=sms.sign.delete&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |

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
  "sub_msg": "响应结果不符合预期"
}
```

## 备注
