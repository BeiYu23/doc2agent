# pigeon.GetPigeonToolList

> 该接口用于根据业务身份和相关参数获取可用的客服工具列表。主要应用场景包括：

1. 初始化时获取可用工具
2. 根据不同业务场景动态展示工具列表
3. 支持多种业务身份和客服场景的工具配置
4. 提供扩展字段支持未来功能迭代

请求参数包括必需的业务身份标

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.GetPigeonToolList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/GetPigeonToolList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/7668 |
| 更新日期 | `2025-08-04` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pigeon_biz_type` | body | number | 是 | 业务ID | `2` |
| `ext` | body | string | 否 | 扩展字段 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.track.bytedance.query&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tool_list` | array | 工具列表 | `[       "BASIC_SCRIPT",       "URGE_PURCHASE",       "GOODS_RECOMMEND",       "ACK_ORDER_ADDRESS",       "APPLY_REFUND",       "APPLY_EXCHANGE",       "APPLY_AFTERSALE",       "URGE_DELIVERY",       "CLARIFY_ORDER",       "URGE_AFTERSALE",       "AFTERSALE_PROGRESS",       "SENDBACK_GOODS",       "REVERSE_LOGISTIC",       "FREIGHT_REFUND",       "LOGISTIC",       "GIFT_ORDER",       "GIFT_LOGISTIC",       "DIRECT_SWITCH_HUMAN"     ]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -1001:pigeon_biz_type参数错误，当前只允许传入值2（sub_code: isv.business-failed:-1001） | pigeon_biz_type目前只允许传入值2（商家） |

## 响应示例

成功：

```json
{
  "data": {
    "data": "\"{\\\"timestamp\\\":\\\"2020-09-10 12:04:05\\\",\\\"track_no\\\":\\\"123456\\\",\\\"traces\\\": [{\\\"trace_type\\\":\\\"GOT\\\",\\\"trace_sub_type\\\":\\\"GOT_SUCCESS\\\",\\\"timestamp\\\":\\\"2020-09-09 12:04:05\\\",\\\"content\\\":\\\"您的订单已被收件员揽收,【东莞寮步镇横坑营业部】库存中\\\",\\\"site_name\\\":\\\"东莞寮步镇横坑营业部\\\",\\\"site_code\\\":\\\"123\\\"}]}\"",
    "result": "true",
    "returnCode": "\"200\""
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
  "sub_code": "isv.business-failed:-1001",
  "sub_msg": "-1001:pigeon_biz_type参数错误，当前只允许传入值2"
}
```

## 备注
