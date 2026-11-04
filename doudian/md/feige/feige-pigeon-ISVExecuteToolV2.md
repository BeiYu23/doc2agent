# pigeon.ISVExecuteToolV2

> ISV执行客服工具接口V2

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.ISVExecuteToolV2` |
| 中文名 | ISV执行客服工具接口V2 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/ISVExecuteToolV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/8028 |
| 更新日期 | `2026-01-14` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_idempotent_no` | body | string | 是 | 工具执行幂等ID，过期时间2小时，建议格式：{tool_code}_{唯一标识} | `"test_basic_script_001"` |
| `pigeon_biz_type` | body | mixed | 是 | 业务身份，固定传2（国内电商场景） | `2` |
| `product_id_list` | body | string | 否 | 商品ID列表，JSON数组字符串                                                     // 必传的工具: GOODS_RECOMMEND | `"[\"3740656536352063689\",\"3686240338055397653\"]"` |
| `switch_to_human_type` | body | string | 否 | 转人工类型                                                     // 必传的工具: DIRECT_SWITCH_HUMAN                                                     // 20001: 消费者主动转人工 | `"20001"` |
| `tool_code` | body | string | 是 | 工具编码，支持20种工具类型 | `"BASIC_SCRIPT"` |
| `user_entry` | body | string | 否 | 用户入口                                                     // 必传的工具: DIRECT_SWITCH_HUMAN | `"0"` |
| `doudian_open_id` | body | string | 是 | 执行对象ID，通常为消费者ID | `"1@#0n0iM1mdffUpnP+ZsNTCDQIjknfxQfgiUOZRJFU5nm1jAuO4EtbjEEqYA4G9lepbLTocwRkymA=="` |
| `msg_id` | body | string | 是 | 消息ID（用你要回复的那条消息的ID） | `"1851031936466972"` |
| `talk_id` | body | string | 是 | 子会话ID | `"7581826770509366591"` |
| `script` | body | string | 否 | 必传的工具: BASIC_SCRIPT（回复话术）, SEND_IMAGE（图片URL） | `"这是ISV接口测试发送的一条回复消息"` |
| `sku_order_id` | body | string | 否 | SKU订单ID                                                     // 必传的工具: APPLY_REFUND, APPLY_EXCHANGE, APPLY_AFTERSALE, CLARIFY_ORDER,                                                      //            URGE_AFTERSALE, AFTERSALE_PROGRESS, SENDBACK_GOODS, REVERSE_LOGISTIC,                                                      //            FREIGHT_REFUND | `"6948640812388390043"` |
| `after_sale_id` | body | string | 否 | 售后ID                                                     // 必传的工具: URGE_AFTERSALE, AFTERSALE_PROGRESS, SENDBACK_GOODS, REVERSE_LOGISTIC | `"147258183017671555"` |
| `trace_id` | body | string | 是 | 生命周期ID（链路追踪） | `"trace_test_001"` |
| `shop_order_id` | body | string | 否 | 商城订单ID                                                     // 必传的工具: ACK_ORDER_ADDRESS, APPLY_REFUND, APPLY_EXCHANGE, APPLY_AFTERSALE,                                                      //            URGE_DELIVERY, CLARIFY_ORDER, URGE_AFTERSALE, AFTERSALE_PROGRESS,                                                      //            SENDBACK_GOODS, REVERSE_LOGISTIC, FREIGHT_REFUND, LOGISTIC,                                                      //            GIFT_LOGISTIC, INVOICE | `"6948640812388390043"` |
| `product_id` | body | string | 否 | 产品ID                                                     // 必传的工具: URGE_PURCHASE, BASIC_PRODUCT_CARD | `"3691024156255715625"` |
| `intents` | body | string | 否 | 意图信息，JSON数组字符串                                                     // 必传的工具: GIFT_LOGISTIC | `"[{\"demand\":\"\",\"slot\":\"\",\"query\":\"\",\"reply\":\"\"}]"` |
| `ext` | body | string | 否 | 扩展字段 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/ISVExecuteToolV2?app_key=your_appkey_here&method=pigeon.ISVExecuteToolV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | string | 处理结果                                                     // SUCCESS: 执行成功                                                     // FAILED: 执行失败 | `"SUCCESS"` |
| `trace_id` | string | 链路追踪ID，与请求中传入的trace_id一致 | `"trace_test_001"` |
| `biz_err` | object | 业务异常信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "biz_err": {
      "code": "0",
      "msg": "\"success\""
    },
    "result": "\"SUCCESS\"",
    "trace_id": "\"trace_test_001\""
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
