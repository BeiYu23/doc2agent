# order.conversationLabel

> 订单进线情况

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.service.order.conversationLabel` |
| 中文名 | 订单进线情况 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/conversationLabel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1532/6761 |
| 更新日期 | `2024-08-14` |

## 接口说明

- 文档书: 三方客服API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单ID | `123343563` |
| `date_time` | body | mixed | 是 | 时间分区（t+1更新），仅支持查询近7天数据 | `1723046400` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/conversationLabel?app_key=your_appkey_here&method=order.conversationLabel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `conversation_count` | mixed | 进线次数 | `1` |
| `third_label` | string | 三级标签 | `太好啦` |
| `date_time` | mixed | 时间分区，若为0代表暂未查询到该时间分区下订单进线信息 | `1723046400` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:10010） | 请检查入参 |
| `40004` | 非法的参数 / 订单不属于该店铺（sub_code: isv.parameter-invalid:605024001） | 请传入自己店铺的数据 |

## 响应示例

成功：

```json
{
  "data": {
    "conversation_count": "1",
    "date_time": "1723046400",
    "third_label": "太好啦"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:10010",
  "sub_msg": "缺少必选参数"
}
```

## 备注
