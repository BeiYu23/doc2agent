# 查询账单明细

> order.getSettleBillDetail — 查询账单明细

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询账单明细 |
| 文档地址 | `/docs/doudian/bill/bill-order-getSettleBillDetail` |
| 接口 ID | `doudian.bill.order.getSettleBillDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getSettleBillDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1192 |
| 更新日期 | `2022-09-28` |

## 接口说明

- 文档书: 账单API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 是 | 页数（默认为0，第一页从0开始） | `0` |
| `size` | body | number | 是 | 每页结果数,默认为20 | `10` |
| `start_time` | body | string | 是 | 查询开始时间 | `2021-05-18 23:59:59` |
| `end_time` | body | string | 是 | 查询结束时间，建议开始时间和结束时间间隔不超过7天 | `2021-06-18 23:59:59` |
| `order_id` | body | string | 否 | 子订单id | `4778345176320227200` |
| `product_id` | body | string | 否 | 商品id | `12343` |
| `pay_type` | body | string | 否 | 结算账户 0:全部 1:微信（升级前） 2:微信 3:支付宝 4:合众支付 5:聚合账户 | `0` |
| `flow_type` | body | string | 否 | 业务类型，不传则默认为0 0:全部 1:鲁班广告, 2:值点商城, 3:精选联盟  4:小店自卖 | `0` |
| `time_type` | body | string | 是 | 时间类型 0:结算时间 1：下单时间 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getSettleBillDetail?app_key=your_appkey_here&method=order.getSettleBillDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回code   100000为成功，其他为失败 | `100000` |
| `code_msg` | string | 返回信息描述，成功时返回SUCCESS，其他状态下会有失败描述 | `SUCCESS` |
| `data` | array | 账单明细列表 | `-` |
| `total_cnt` | number | 总数 | `0` |
| `page` | number | 页数 | `0` |
| `size` | number | 每页数量 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / size大于1000，请缩小size（sub_code: isv.parameter-invalid:500） | 减小传入的size |

## 响应示例

成功：

```json
{
  "data": {
    "code": "100000",
    "code_msg": "SUCCESS",
    "data": [
      {
        "actual_author_coupon": "0",
        "actual_pay_promotion": "0",
        "actual_platform_coupon": "0",
        "actual_subsidy_amount": "0",
        "author_coupon": "0",
        "colonel_service_fee": "0",
        "commission": "0",
        "flow_type": "1",
        "flow_type_desc": "广告",
        "good_learn_channel_fee": "0",
        "goods_count": "10",
        "order_id": "4778345176320227200",
        "order_time": "2021-04-07 11:05:56",
        "pay_promotion": "0",
        "pay_type": "1",
        "pay_type_desc": "支付宝",
        "phase_cnt": "2",
        "phase_id": "1",
        "phase_order_no": "1232",
        "platform_coupon": "0",
        "platform_service_fee": "950",
        "post_amount": "0",
        "product_id": "3461567267249244016",
        "profit": "950",
        "real_pay_amount": "0",
        "refund": "0",
        "request_no": "6945807072718045454",
        "settle_amount": "950",
        "settle_time": "2021-05-17 11:05:56",
        "settled_pay_amount": "0",
        "shop_coupon": "0",
        "shop_id": "12345",
        "shop_order_id": "4778345176320227200",
        "shop_refund_loss": "0",
        "total_amount": "0",
        "total_goods_amount": "0",
        "total_income": "950",
        "total_outcome": "0",
        "trade_type": "0",
        "trade_type_desc": "已结算"
      }
    ],
    "page": "0",
    "size": "0",
    "total_cnt": "0"
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
  "sub_code": "isv.parameter-invalid:500",
  "sub_msg": "size大于1000，请缩小size"
}
```

## 备注
