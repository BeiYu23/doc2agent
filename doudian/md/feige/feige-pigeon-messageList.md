# 查询会话消息列表

> pigeon.messageList — 查询会话消息列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询会话消息列表 |
| 文档地址 | `/docs/doudian/feige/feige-pigeon-messageList` |
| 接口 ID | `doudian.feige.pigeon.messageList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/messageList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5909 |
| 更新日期 | `2025-08-04` |

## 接口说明

- 文档书: 飞鸽API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `conversation_id` | body | string | 是 | 飞鸽会话ID | `7307297935836939546` |
| `start_cursor` | body | mixed | 是 | 开始拉消息的位点 | `0` |
| `limit` | body | mixed | 是 | 每次获取消息的数量，最大值不超过50 | `20` |
| `conversation_type` | body | mixed | 否 | 会话类型，默认11，业务方可传10查询用户所有会话信息 | `11` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/messageList?app_key=your_appkey_here&method=pigeon.messageList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `has_more` | boolean | 是否还有更多的消息 | `true` |
| `next_cursor` | mixed | 下一次拉消息的位点 | `1792123122` |
| `message_list` | array | 消息内容信息 | `` |
| `doudian_aid` | string | 用户端 | `1128` |
| `doudian_open_id` | string | 用户OpenId | `121211212` |
| `conv_url` | string | 跳转飞鸽工作台会话URL | `https://im.jinritemai.com/op/conversation?cid=7312282185073984805` |
| `mix_nick` | string | 模糊化的用户昵称 | `许****` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务处理异常（sub_code: isv.business-failed:605022001） | 业务处理异常，请稍后重试 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:605022002） | 参数异常，会话信息不存在 |
| `40002` | 缺少必选参数 / 参数异常（sub_code: isv.missing-parameter:605022003） | 缺少必填的参数，请补充参数 |

## 响应示例

成功：

```json
{
  "data": {
    "conv_url": "https://im.jinritemai.com/op/conversation?cid=7312282185073984805",
    "doudian_aid": "1128",
    "doudian_open_id": "121211212",
    "has_more": "true",
    "message_list": [
      {
        "card_type": "order_card",
        "content": "hello",
        "create_time": "1702298756522",
        "customer_hint": "欢迎光临美妆宣言美妆，很高兴为您服务",
        "data_id": "121212122",
        "extra": "{\"trace_id\": \"02175299357520400000000000000000000ffff0ad040ad27ce1a:1838146990170155\",\"coupon_meta_id\":1231312312312312}",
        "foot_text": "此消息由系统发送",
        "pigeon_cid": "77887788122",
        "sender_role": "CurrentServer",
        "server_msg_id": "778877881221212",
        "type": "text"
      }
    ],
    "mix_nick": "许****",
    "next_cursor": "1792123122"
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
  "sub_code": "isv.business-failed:605022001",
  "sub_msg": "业务处理异常"
}
```

## 备注
