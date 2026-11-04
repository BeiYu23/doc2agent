# crossBorder.getTradeOrderStatus

> 获取交易订单状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossBorder.getTradeOrderStatus` |
| 中文名 | 获取交易订单状态 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/getTradeOrderStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/1650 |
| 更新日期 | `2022-02-10` |

## 接口说明

- 文档书: 跨境API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vendor` | body | string | 否 | 服务商编码 | `-` |
| `order_id` | body | string | 否 | 订单id | `4789899944007763859` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/getTradeOrderStatus?app_key=your_appkey_here&method=crossBorder.getTradeOrderStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_status` | number | 订单状态 | `1` |
| `final_status` | number | 最终状态 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单号不存在（sub_code: isv.business-failed:1005） | 订单号不存在 |
| `50002` | 业务处理失败 / orderId值不能为空！（sub_code: isv.business-failed:1002） | 校验参数 |

## 响应示例

成功：

```json
{
  "data": {
    "final_status": "1",
    "order_status": "1"
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
  "sub_code": "isv.business-failed:1005",
  "sub_msg": "订单号不存在"
}
```

## 备注
