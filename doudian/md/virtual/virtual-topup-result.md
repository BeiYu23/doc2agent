# 商家充值结果回调

> topup.result — 商家充值结果回调

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家充值结果回调 |
| 文档地址 | `/docs/doudian/virtual/virtual-topup-result` |
| 接口 ID | `doudian.virtual.topup.result` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/result` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/1639 |
| 更新日期 | `2024-10-21` |

## 接口说明

- 文档书: 虚拟充值API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trade_order_no` | body | string | 是 | 订单号 | `47544092076043809181` |
| `topup_biz` | body | string | 是 | 充值业务 | `MOBILE_TOPUP` |
| `seller_order_no` | body | string | 是 | 商家充值单号 | `DY8123123` |
| `seller_order_status` | body | string | 是 | 充值结果 | `SUCCESS` |
| `err_code` | body | string | 否 | 错误码 | `1003` |
| `err_desc` | body | string | 否 | 错误信息 | `参数校验失败` |
| `url` | body | string | 否 | 去使用链接 | `https://xxxx.com` |
| `url_type` | body | string | 否 | 去使用链接类型 小程序：microapp 普通链接：normal | `normal` |
| `topup_failure_reason_code` | body | string | 否 | 充值失败错误码 10001：手机号码无效 10002：商家缺货 10003 ： 命中运营商风控策略 | `10001` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/result?app_key=your_appkey_here&method=topup.result&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `trade_order_no` | string | 平台订单号. | `4754409207604380918` |
| `topup_biz` | string | 充值业务 | `MOBILE_TOPUP` |
| `result` | string | 平台接口充值结果失败 | `FAILED` |
| `seller_order_no` | string | 商家充值单号 | `DY8123123` |
| `err_code` | string | 错误码 | `-1` |
| `err_desc` | string | 错误信息 | `内部错误` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "err_code": "-1",
    "err_desc": "内部错误",
    "result": "FAILED",
    "seller_order_no": "DY8123123",
    "topup_biz": "MOBILE_TOPUP",
    "trade_order_no": "4754409207604380918"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
