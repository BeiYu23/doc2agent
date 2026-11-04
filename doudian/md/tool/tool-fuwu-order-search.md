# 服务市场商家订购搜索

> fuwu.order.search — 服务市场商家订购搜索接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务市场商家订购搜索 |
| 文档地址 | `/docs/doudian/tool/tool-fuwu-order-search` |
| 接口 ID | `doudian.tool.fuwu.order.search` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/order/search` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/6529 |
| 更新日期 | `2024-07-01` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | mixed | 否 | 订单号 | `1` |
| `buyer_id` | body | mixed | 否 | 买家id（买家是购买服务市场服务的用户，比如商家） | `2` |
| `service_type_list` | body | array | 否 | 服务类型：1-软件类 | `[1]` |
| `order_status_list` | body | array | 否 | 订单状态：1-订单创建，105-订单已支付，2-订单待履约，3-订单履约中，4-订单取消（关闭)，5-订单完成 | `[1]` |
| `payment_no` | body | string | 否 | 支付流水号 | `GTPA6586364464625012047115` |
| `time_type` | body | mixed | 否 | 筛选时间类型：1-下单时间，2-支付时间，3-服务开始时间，4-服务结束时间 | `1` |
| `start_time` | body | mixed | 否 | 筛选开始时间，匹配时间类型，时间戳，单位：秒 | `1716376322` |
| `end_time` | body | mixed | 否 | 筛选结束时间，匹配时间类型，时间戳，单位：秒 | `1716376422` |
| `order_by` | body | mixed | 否 | 排序条件：1-服务结束时间，2-订单创建时间，3-服务开始时间，4-支付时间 | `1` |
| `order_asc` | body | boolean | 否 | 排序类型，小到大或大到小，默认大到小 | `true` |
| `page_num` | body | mixed | 是 | 页数，第一页从1开始 | `1` |
| `page_size` | body | mixed | 是 | 每页订单数，最大100 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/order/search?app_key=your_appkey_here&method=fuwu.order.search&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `orders` | array | 订单列表 | `` |
| `total` | mixed | 订单总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1000001） | 根据错误描述修改请求参数 |
| `20000` | 系统错误（sub_code: isp.service-error:1000000） | 请求重试，一直失败请联系平台 |
| `20000` | 系统错误 / 系统错误（用于内部识别异常原因）（sub_code: isp.service-error:1000003） | 请求重试，一直失败请联系平台 |
| `20000` | 系统错误 / 系统错误（用于内部识别异常原因）（sub_code: isp.service-error:1000002） | 请求重试，一直失败请联系平台 |

## 响应示例

成功：

```json
{
  "data": {
    "orders": [
      {
        "order": {
          "buyer_id": "2",
          "buyer_name": "xx店铺",
          "create_time": "1716376222",
          "num": "1",
          "order_id": "12323241243",
          "order_status": "1",
          "pay_amount": "100",
          "pay_time": "1716376322",
          "pay_type": "16",
          "price": "100",
          "remark": "备注",
          "service_begin_time": "1716376322",
          "service_end_time": "1716377322",
          "service_id": "23",
          "service_name": "这是一个服务",
          "update_time": "1716376232"
        }
      }
    ],
    "total": "100"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1000001",
  "sub_msg": "参数错误"
}
```

## 备注
