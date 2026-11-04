# mini.queryLuxPreOrderCustomInfo

> 奢品小程序-查询购前定制定制信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.mini.queryLuxPreOrderCustomInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/queryLuxPreOrderCustomInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/8415 |
| 更新日期 | `2026-07-28` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | mixed | 是 | 店铺orderId | `6954265941868352798` |
| `sku_order_id` | body | mixed | 是 | SkuOrderId | `6954265941868352723` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/queryLuxPreOrderCustomInfo?app_key=your_appkey_here&method=mini.queryLuxPreOrderCustomInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `lux_order_custom_info_json` | string | 奢品定制信息的json字符串 | `"{\"preview_pic_url\":\"预览图url\",\"detail\":{\"pic\":[{\"id\":2,\"url\":\"图片url\"}],\"text\":[{\"id\":3,\"key\":\"文字key\",\"content\":\"文字内容\"}],\"extra\":\"业务额外的json string\"}}"` |
| `consumer_confirm_status` | mixed | 消费者确认状态: 0-未确认,1-已确认 | `0` |
| `merchant_confirm_status` | mixed | 商家确认状态: 0-未确认,1-已确认 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 请求参数问题（sub_code: isv.missing-parameter:28007004） | 请按要求传递所有必填参数 |
| `20000` | 系统错误 / 系统组件相关错误（sub_code: isp.service-error:28001005） | 提供logId咨询技术支持 |
| `40004` | 非法的参数 / 订单查询失败（sub_code: isv.parameter-invalid:28007006） | 请咨询技术支持检查订单详细信息 |

## 响应示例

成功：

```json
{
  "data": {
    "consumer_confirm_status": "0",
    "lux_order_custom_info_json": "\"{\\\"preview_pic_url\\\":\\\"预览图url\\\",\\\"detail\\\":{\\\"pic\\\":[{\\\"id\\\":2,\\\"url\\\":\\\"图片url\\\"}],\\\"text\\\":[{\\\"id\\\":3,\\\"key\\\":\\\"文字key\\\",\\\"content\\\":\\\"文字内容\\\"}],\\\"extra\\\":\\\"业务额外的json string\\\"}}\"",
    "merchant_confirm_status": "0"
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
  "sub_code": "isv.missing-parameter:28007004",
  "sub_msg": "请求参数问题"
}
```

## 备注
