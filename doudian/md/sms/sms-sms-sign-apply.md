# sms.sign.apply

> 提交短信签名申请单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.sign.apply` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sign/apply` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1525 |
| 更新日期 | `2026-04-08` |

## 接口说明

- 文档书: 短信API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `12345` |
| `sign` | body | string | 是 | 签名 | `abc` |
| `version` | body | string | 否 | 版本号 v2则走新链路 | `v2` |
| `auto_use_isv_dedicated_message_group` | body | boolean | 否 | 是否使用isv专用消息组，为true且申请签名与抖店后台签名不一致时，将签名申请到isv专用消息组 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/apply?app_key=your_appkey_here&method=sms.sign.apply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sms_account` | string | 短信发送渠道，主要做资源隔离 | `1234` |
| `sms_sign_apply_id` | string | 短信签名申请单id | `23423423` |
| `code` | mixed | 是否成功 0表示成功 | `0` |
| `message` | string | 说明 | `成功` |
| `sign` | string | 签名 | `abc` |
| `status` | mixed | 审核状态： 1:审核中 2:未通过 3:已开通 4:已关闭 5:免审核（店铺名和签名完全一致时返回） | `1` |
| `shop_sub_account` | string | 签名申请到了哪个消息组 | `sefsfe` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 签名已经存在（sub_code: isv.parameter-invalid:7） | 签名已经存在 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 参数不合法 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:4） | 内部错误 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:500） | 超时 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |
| `20000` | 系统错误 / 超时（sub_code: isp.service-error:628004002） | 服务处理超时，请重试 |
| `40004` | 非法的参数 / 商家不存在（sub_code: isv.parameter-invalid:628005202） | 商家不存在 |
| `40002` | 缺少必选参数 / 输入参数不正确，请检查后重试（sub_code: isv.missing-parameter:628002001） | 请根据错误信息检查入参是否正确 |
| `20000` | 系统错误 / 服务内部错误，请重试（sub_code: isp.service-error:628004001） | 服务内部错误，请重试 |
| `50002` | 业务处理失败 / HttpPost请求失败（sub_code: isv.business-failed:628004702） | 服务内部错误，请重试 |
| `50002` | 业务处理失败 / 628004000:服务器开小差了，请稍后重试（sub_code: isv.business-failed:628004000） | 628004000:服务器开小差了，请稍后重试 |
| `50002` | 业务处理失败 / 628004004:get cache err（sub_code: isv.business-failed:628004004） | 628004004:get cache err |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "message": "成功",
    "shop_sub_account": "sefsfe",
    "sign": "abc",
    "sms_account": "1234",
    "sms_sign_apply_id": "23423423",
    "status": "1"
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
  "sub_code": "isv.parameter-invalid:7",
  "sub_msg": "签名已经存在"
}
```

## 备注
