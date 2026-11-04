# sms.sendResult

> 查询短信发送结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.sendResult` |
| 中文名 | 查询短信发送结果 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sendResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1517 |
| 更新日期 | `2026-08-18` |

## 接口说明

- 文档书: 短信API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `from_time` | body | mixed | 是 | 开始时间-时间戳，单位秒 | `1618652575` |
| `to_time` | body | mixed | 是 | 结束时间-时间戳，单位秒 | `1618652575` |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `template_id` | body | string | 否 | 模版id | `444` |
| `status` | body | mixed | 否 | 发送状态： 未回执：1 发送失败：2 发送成功：3 | `1` |
| `size` | body | mixed | 否 | 查询结果大小，默认是10 | `10` |
| `page` | body | mixed | 否 | 查询结果页数，从0开始，默认是0 | `0` |
| `sign` | body | string | 否 | 签名内容 | `21312` |
| `post_tel` | body | string | 否 | 既支持明文，又支持密文 | `15088788987` |
| `message_id` | body | string | 否 | 消息的唯一标识，可以用于查询短信到达等 | `7238746` |
| `tpl_type` | body | mixed | 否 | 查询短信类型，默认是查普通文本短信： 0是查询所有类型短信，1是查询普通文本短信，2是查询视频短信 | `1` |
| `sms_test_verification` | body | object | 否 | 明文手机号查询验证码 | `` |
| `  └ code` | body | string | 否 | 验证码 | `214213` |
| `  └ post_tel` | body | string | 否 | 明文手机号 | `12132131231` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sendResult?app_key=your_appkey_here&method=sms.sendResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 数量 | `100` |
| `sms_send_result_list` | array | 短信结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 超时，请重试（sub_code: isp.service-error:500） | 超时，请重试 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |
| `20000` | 系统错误 / 628004205:Redis Get错误（sub_code: isp.service-error:628004205） | 系统内部错误，请重试 |
| `50002` | 业务处理失败 / 628002001:您输入参数不正确，请检查后重试（sub_code: isv.business-failed:628002001） | 业务错误，请检查 |
| `50002` | 业务处理失败 / 628004002:请求超时（sub_code: isv.business-failed:628004002） | 请求超时，请重试 |
| `50002` | 业务处理失败 / 628004004:Access Database error（sub_code: isv.business-failed:628004004） | 628004004:Access Database error |

## 响应示例

成功：

```json
{
  "data": {
    "sms_send_result_list": [
      {
        "code": "0",
        "count": "1",
        "message": "abc",
        "message_id": "MessageID1",
        "send_time": "1618652575",
        "sms_content": "您购买的商品已重新发出，圆通快递快递运单号：1234，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。",
        "status": "1",
        "tag": "12345"
      }
    ],
    "total": "100"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:500",
  "sub_msg": "超时，请重试"
}
```

## 备注
