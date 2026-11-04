# 查询短信模板

> sms.template.search — 查询短信模板

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询短信模板 |
| 文档地址 | `/docs/doudian/sms/sms-sms-template-search` |
| 接口 ID | `doudian.sms.sms.template.search` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/template/search` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1514 |
| 更新日期 | `2026-04-20` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `template_id` | body | string | 否 | 短信模板id | `7238746` |
| `template_content` | body | string | 否 | 短信模版内容 | `您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。` |
| `page` | body | mixed | 否 | 页码，默认0 | `0` |
| `size` | body | mixed | 否 | 每页大小，默认10 | `10` |
| `template_name` | body | string | 否 | 短信模版名称 | `618大促` |
| `is_public` | body | boolean | 否 | 是否查询公域模板 | `false` |
| `version` | body | string | 否 | 短信版本，v2表示新版本 | `v2` |
| `template_biz_sub_type` | body | mixed | 否 | 模板业务子类型 | `100000` |
| `template_biz_type` | body | mixed | 否 | 模板业务类型 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/template/search?app_key=your_appkey_here&method=sms.template.search&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_search_list` | array | 模板列表 | `` |
| `total` | mixed | 总条数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 628004205:Redis Get错误（sub_code: isp.service-error:628004205） | 系统内部错误，请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "template_search_list": [
      {
        "channel_type": "CN_NTC",
        "is_public": "false",
        "sms_account": "1234",
        "template_content": "您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。",
        "template_id": "43534",
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:628004205",
  "sub_msg": "628004205:Redis Get错误"
}
```

## 备注
