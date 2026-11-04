# sms.template.apply.list

> 查询短信模板申请单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.template.apply.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/template/apply/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1516 |
| 更新日期 | `2025-12-18` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `template_content` | body | string | 否 | 短信模板内容： 英文短信：整条短信（包括签名+模板+变量中的内容）最多支持140个英文字符，超出将按140个字符截取为多条短信进行发送，费用按截取的条数收费； 非英文短信：整条短信（包括签名+模板+变量中的内容）最多支持70字符，超出将按70个字符截取为多条短信进行发送，费用按截取的条数收费； | `您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。` |
| `sms_template_apply_id` | body | string | 否 | 短信模板申请单id | `23423423` |
| `size` | body | mixed | 否 | 每页数量，默认10 | `10` |
| `page` | body | mixed | 否 | 页码，默认0 | `0` |
| `status` | body | mixed | 否 | 审核状态： 1:审核中 2:未通过 3:已开通 4:已关闭 5:免审 | `1` |
| `version` | body | string | 否 | 短信版本，v2表示新版本 | `v2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.template.apply.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_apply_list` | array | 短信模板申请单列表 | `` |
| `total` | mixed | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误码描述检查请求参数 |
| `20000` | 系统错误 / 628004205:Redis Get错误（sub_code: isp.service-error:628004205） | 系统内部错误，请重试 |
| `50002` | 业务处理失败 / 628004002:接口超时（sub_code: isv.business-failed:628004002） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "template_apply_list": [
      {
        "channel_type": "模版类型",
        "public_fail_reason": "失败原因",
        "public_status": "3",
        "sms_account": "1234",
        "sms_template_apply_id": "23423423",
        "status": "1",
        "status_remark": "签名重复",
        "template_content": "您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。",
        "template_id": "ST_123456",
        "template_name": "618大促"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:628005100",
  "sub_msg": "响应结果不符合预期"
}
```

## 备注
