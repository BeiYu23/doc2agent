# ISV客服工具可用性预检查接口

> pigeon.ISVToolEventPreCheck — ISV客服工具可用性预检查接口，用于查询指定会话中各个客服工具的可执行状态和频控限制

| 元信息 | 值 |
| --- | --- |
| 中文名 | ISV客服工具可用性预检查接口 |
| 文档地址 | `/docs/doudian/feige/feige-pigeon-ISVToolEventPreCheck` |
| 接口 ID | `doudian.feige.pigeon.ISVToolEventPreCheck` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/ISVToolEventPreCheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/7955 |
| 更新日期 | `2025-12-17` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `doudian_open_id` | body | string | 否 | 用户ID（用于AB实验分流） | `"1@#0n0iM1mdffUpnP+ZsNTCDQIjknfxQfgiUOZRJFU5nm1jAuO4EtbjEEqYA4G9lepbLTocwRkymA=="` |
| `tool_codes` | body | array | 否 | 工具代码列表 | `[         "URGE_PURCHASE",         "BASIC_PRODUCT_CARD",         "GOODS_RECOMMEND",         "ACK_ORDER_ADDRESS",         "APPLY_REFUND",         "APPLY_EXCHANGE",         "APPLY_AFTERSALE",         "URGE_DELIVERY",         "CLARIFY_ORDER",         "URGE_AFTERSALE",         "AFTERSALE_PROGRESS",         "SENDBACK_GOODS",         "REVERSE_LOGISTIC",         "FREIGHT_REFUND",         "LOGISTIC",         "GIFT_LOGISTIC",         "DIRECT_SWITCH_HUMAN",         "INVOICE",         "SEND_IMAGE"     ]` |
| `conversation_id` | body | string | 否 | 会话ID（用于会话维度频控） | `"7582570312244544808"` |
| `ext` | body | string | 否 | 扩展字段 | `""` |
| `pigeon_biz_type` | body | mixed | 否 | 飞鸽业务类型 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/ISVToolEventPreCheck?app_key=your_appkey_here&method=pigeon.ISVToolEventPreCheck&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tool_availability` | string | 工具可用性，key为tool_code，value为是否可用 | `{"ACK_ORDER_ADDRESS":true,"AFTERSALE_PROGRESS":true,"APPLY_AFTERSALE":true,"APPLY_EXCHANGE":true,"APPLY_REFUND":true,"BASIC_PRODUCT_CARD":false,"CLARIFY_ORDER":true,"DIRECT_SWITCH_HUMAN":true,"FREIGHT_REFUND":true,"GIFT_LOGISTIC":true,"GOODS_RECOMMEND":true,"INVOICE":true,"LOGISTIC":true,"REVERSE_LOGISTIC":true,"SENDBACK_GOODS":true,"SEND_IMAGE":true,"URGE_AFTERSALE":true,"URGE_DELIVERY":true,"URGE_PURCHASE":true}` |
| `ext` | string | 扩展字段 | `""` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "ext": "\"\"",
    "tool_availability": {}
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
