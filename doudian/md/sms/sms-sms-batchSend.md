# 批量短信发送

> sms.batchSend — 批量短信发送

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量短信发送 |
| 文档地址 | `/docs/doudian/sms/sms-sms-batchSend` |
| 接口 ID | `doudian.sms.sms.batchSend` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/batchSend` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1521 |
| 更新日期 | `2026-09-18` |

## 接口说明

- 文档书: 短信API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `sign` | body | string | 是 | 短信签名 | `abc` |
| `sms_message_list` | body | array | 是 | 短信列表 | `` |
| `  └ scene_type` | body | mixed | 否 | 场景类型，1-售后退货寄件人 | `1` |
| `  └ after_sale_id` | body | string | 否 | 售后单id | `13837776263` |
| `  └ template_param` | body | string | 是 | 参数 | `{\"code\":\"1234\"}` |
| `  └ post_tel` | body | string | 否 | 已废弃 | `13837776263` |
| `  └ order_id` | body | string | 否 | 订单id | `13837776263` |
| `  └ douyin_open_id` | body | string | 否 | 抖音小程序openID | `1282618212` |
| `  └ outbound_id` | body | string | 否 | 外呼id，由/member/getOutboundId接口获取。/member/getOutboundId当前还未开放，outbound_id暂不支持使用 | `17037442535v6Nz7_3u0` |
| `template_id` | body | string | 是 | 短信模板id | `60505C68` |
| `tag` | body | string | 否 | 透传字段，回执的时候原样返回给调用方，最大长度512字符 | `123456` |
| `user_ext_code` | body | string | 否 | 用户自定义扩展码，仅当允许自定义扩展码的时候生效 | `abc` |
| `link_id` | body | string | 否 | 需要链接统计效果时必传，且    2. tag需要以map[string]interface{}的json形式传入，并且带上"link_id":"" | `121292221` |
| `mini_app_link_id` | body | string | 否 | 需要链接统计效果时必传，且    2. tag需要以map[string]interface{}的json形式传入，并且带上"mini_app_link_id":"" | `21628162812` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/batchSend?app_key=your_appkey_here&method=sms.batchSend&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `send_result_list` | array | 发送结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 根据文档检查参数 |
| `40004` | 非法的参数 / 参数Sign对应签名不存在（sub_code: isv.parameter-invalid:7） | 参数Sign对应签名不存在 |
| `20000` | 系统错误 / 服务内部错误，请重试（sub_code: isp.service-error:4） | 服务内部错误，请重试 |
| `20000` | 系统错误 / 超时，请重试（sub_code: isp.service-error:500） | 超时，请重试 |
| `20000` | 系统错误 / 超时（sub_code: isp.service-error:628004002） | 服务内部错误，请重试 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |
| `20000` | 系统错误 / 服务内部错误（sub_code: isp.service-error:628004001） | 服务内部错误，请重试 |
| `40002` | 缺少必选参数 / 输入参数不正确（sub_code: isv.missing-parameter:628002001） | 请根据错误信息检查入参是否正确 |
| `20000` | 系统错误 / 服务内部错误，请重试（sub_code: isp.service-error:628004702） | 服务内部错误，请重试 |
| `20000` | 系统错误 / 服务内部错误，请重试（sub_code: isp.service-error:628004205） | 服务内部错误，请重试 |
| `50002` | 业务处理失败 / 外呼id已过期（sub_code: isv.business-failed:628003201） | 外呼id已过期，请重新获取 |
| `50002` | 业务处理失败 / 短信发送命中频控（sub_code: isv.business-failed:628003202） | 短信发送命中频控，具体请参考短信频控规则 |
| `50002` | 业务处理失败 / 628004004:Access Database error（sub_code: isv.business-failed:628004004） | 628004004:Access Database error |
| `50002` | 业务处理失败 / 禁止使用明文手机号发送短信（sub_code: isv.business-failed:628003500） | 禁止使用明文手机号发送短信 |
| `50002` | 业务处理失败 / 628004000:参数异常%!(EXTRA string=店铺未开通短信服务)（sub_code: isv.business-failed:628004000） | 店铺未开通短信服务 |

## 响应示例

成功：

```json
{
  "data": {
    "send_result_list": [
      {
        "code": "0",
        "message": "abc",
        "message_id": "435435435435"
      }
    ]
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
