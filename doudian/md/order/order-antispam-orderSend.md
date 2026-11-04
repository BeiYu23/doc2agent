# antispam.orderSend

> 支持使用在ISV系统商户发送（外部系统或模块，如快递平台）场景

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.antispam.orderSend` |
| 中文名 | 支持使用在ISV系统商户发送（外部系统或模块 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/antispam/orderSend` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1840 |
| 更新日期 | `2021-07-05` |

## 接口说明

- 文档书: 订单API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `event_time` | body | number | 是 | 事件时间 | `1624514492` |
| `user` | body | object | 否 | 用户 | `-` |
| `  └ uid_type` | body | string | 否 | 用户类型 | `12` |
| `  └ user_id` | body | number | 否 | 用户 ID | `1` |
| `params` | body | string | 是 | 可变参数 | `{"account_id":12345}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/antispam/orderSend?app_key=your_appkey_here&method=antispam.orderSend&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `decision` | object | 决策 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:-1） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "decision": {
      "decision": "PASS",
      "decision_detail": "detail",
      "hit_status": "hint"
    }
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
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "系统繁忙，请稍后重试"
}
```

## 备注
