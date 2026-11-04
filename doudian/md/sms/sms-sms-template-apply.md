# 提交短信模板申请单

> sms.template.apply — 提交短信模板申请单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 提交短信模板申请单 |
| 文档地址 | `/docs/doudian/sms/sms-sms-template-apply` |
| 接口 ID | `doudian.sms.sms.template.apply` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/template/apply` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1527 |
| 更新日期 | `2026-07-28` |

## 接口说明

- 文档书: 短信API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `12345` |
| `template_type` | body | string | 是 | CN_NTC 国内通知短信 CN_MKT 国内营销短信 CN_OTP 国内验证码 | `CN_NTC` |
| `template_name` | body | string | 是 | 短信模板名称 | `618大促` |
| `template_content` | body | string | 是 | 短信模板内容： 英文短信：整条短信（包括签名+模板+变量中的内容）最多支持140个英文字符，超出将按140个字符截取为多条短信进行发送，费用按截取的条数收费； 非英文短信：整条短信（包括签名+模板+变量中的内容）最多支持70字符，超出将按70个字符截取为多条短信进行发送，费用按截取的条数收费； | `您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。` |
| `is_public` | body | boolean | 否 | 是否公域短信模板 | `false` |
| `version` | body | string | 否 | 短信版本，v2表示新版本 | `v2` |
| `template_biz_type` | body | mixed | 否 | 模板业务类型 | `1` |
| `template_biz_sub_type` | body | mixed | 否 | 模板业务子类型 | `100000` |
| `sign` | body | string | 否 | volc_version = v2时生效 绑定签名 | `xxx` |
| `template_params` | body | array | 否 | volc_version = v2时生效 模板的参数类型 | `` |
| `  └ name` | body | string | 否 | 变量名称 | `url` |
| `  └ param_type` | body | mixed | 否 | 参数类型,1普通变量,2链接变量 | `2` |
| `template_traffic_driving` | body | array | 否 | volc_version = v2时生效 模板内容 | `` |
| `  └ name` | body | string | 否 | 变量名称 | `url` |
| `  └ content` | body | string | 否 | 变量值 | `z.douyin.com` |
| `  └ param_type` | body | mixed | 否 | 变量类型 | `2` |
| `volc_version` | body | string | 否 | 模板版本 | `v2` |
| `short_url_config` | body | object | 否 | volc_version = v2时生效 | `` |
| `  └ is_need_click_details` | body | boolean | 否 | 0静态短链 1动态短链 | `false` |
| `  └ ua_check_strategy` | body | mixed | 否 | 0短链仅移动设备可访问 1短链所有设备可访问 | `1` |
| `  └ is_enabled` | body | boolean | 否 | 0不开启 1开启 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/template/apply?app_key=your_appkey_here&method=sms.template.apply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sms_account` | string | 短信发送渠道，主要做资源隔离 | `1234` |
| `template_content` | string | 短信模板内容： 英文短信：最多支持140个英文字符，超出将按140个字符截取为多条短信进行发送，费用按截取的条数收费； 非英文短信：最多支持140个英文字符，超出将按140个字符截取为多条短信进行发送，费用按截取的条数收费； | `您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。` |
| `template_name` | string | 短信模版名称 | `618大促` |
| `sms_template_id` | string | 模版id | `234234` |
| `sms_template_apply_id` | string | 短信模板申请单id | `23423423` |
| `code` | mixed | 是否成功 0表示成功 | `0` |
| `message` | string | 说明 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 7:模板中不允许包含"【】"等（sub_code: isv.parameter-invalid:7） | 请根据错误码描述检查请求参数 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "message": "成功",
    "sms_account": "1234",
    "sms_template_apply_id": "23423423",
    "sms_template_id": "234234",
    "template_content": "您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。",
    "template_name": "618大促"
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
  "sub_msg": "7:模板中不允许包含\"【】\"等"
}
```

## 备注
