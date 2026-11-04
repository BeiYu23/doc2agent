# 主动推送消息

> ddp_open.ai.addChatMessage — 主动推送消息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 主动推送消息 |
| 文档地址 | `/docs/doudian/industry/industry-ddp_open-ai-addChatMessage` |
| 接口 ID | `doudian.industry.ddp_open.ai.addChatMessage` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/ddp_open/ai/addChatMessage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8347 |
| 更新日期 | `2026-07-07` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `message` | body | object | 否 | 消息体 | `` |
| `  └ role` | body | string | 否 | 本期固定为assistant | `assistant` |
| `  └ outer_message_id` | body | string | 否 | isv生成的消息id | `outer_sef12321` |
| `  └ type` | body | string | 否 | 消息类型 固定为answer | `answer` |
| `  └ parent_message_id` | body | string | 否 | 父消息ID（上一条） | `12321421` |
| `  └ conversation_id` | body | string | 否 | 会话ID | `12534543` |
| `  └ content` | body | object | 否 | 消息内容 | `` |
| `    └ text` | body | string | 否 | 展示文本 | `mardown文本` |
| `    └ type` | body | string | 否 | 本期固定为mixed_card | `mixed_card` |
| `  └ action` | body | string | 否 | 交互行为 common | `common` |
| `auth_user_id` | body | mixed | 否 | 账号id | `12321` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/ddp_open/ai/addChatMessage?app_key=your_appkey_here&method=ddp_open.ai.addChatMessage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
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
