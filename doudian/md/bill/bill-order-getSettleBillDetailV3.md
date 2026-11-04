# order.getSettleBillDetailV3

> 商家结算账单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.getSettleBillDetailV3` |
| 中文名 | 商家结算账单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getSettleBillDetailV3` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/7226 |
| 更新日期 | `2026-07-16` |

## 接口说明

- 文档书: 账单API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | mixed | 否 | 页数，支持范围1~100 | `5011` |
| `start_time` | body | string | 否 | 查询开始时间，格式为：yyyy-MM-dd HH:mm:ss，订单号未传的情况下，开始时间必须传，注意：分页查询时，除首次查询外，应填入上一次返回的next_start_time | `2021-05-18 00:00:00` |
| `end_time` | body | string | 否 | 查询结束时间，和end_time的时间间隔建议不超过7天，格式为：yyyy-MM-dd HH:mm:ss，订单号未传的情况下，结束时间必须传 | `2021-05-18 00:00:00` |
| `order_id` | body | string | 否 | SKU单，子订单号，支持通过英文逗号分隔传入多个参数 | `4778345176320227200` |
| `product_id` | body | string | 否 | 商品id | `123456` |
| `pay_type` | body | string | 否 | 结算账户，不传则默认为全部，枚举： 1（微信：升级前）、 2（微信）、 3（支付宝）、 4（合众支付）、 5（聚合账户），支持通过英文逗号分隔传入多个参数 | `1` |
| `flow_type` | body | string | 否 | 业务类型，不传则默认为全部，枚举： 1（巨量千川）、2（值点商城）, 3（精选联盟）、 4（小店自卖） | `1` |
| `time_type` | body | string | 否 | 时间类型 ，不传则默认为结算时间，枚举： 0（结算时间） 1（下单时间） | `0` |
| `start_index` | body | string | 否 | 查询开始索引，注意：分页查询时，除首次查询可不填外，应填入上一次返回的next_start_index | `123445` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getSettleBillDetailV3?app_key=your_appkey_here&method=order.getSettleBillDetailV3&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回code 100000为成功，其他为失败 | `1000001` |
| `code_msg` | string | 返回信息描述，失败状态下会有失败描述 | `success` |
| `data` | array | 订单流水明细列表 | `` |
| `size` | mixed | 请求的size | `100` |
| `next_start_index` | string | 下一次查询start_index | `12345678` |
| `next_start_time` | string | 下一次查询start_time | `2021-05-18 03:00:00` |
| `is_end` | mixed | 判断查询是否结束。0 未结束, 1 结束。未结束时，需要把next_start_index作为下一次请求的start_index,next_start_time作为下一次请求的start_time | `0` |
| `data_size` | mixed | 结果data的大小 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请检查参数（sub_code: isv.parameter-invalid:100026） | 请检查参数 |
| `50002` | 业务处理失败 / 100010:DB异常（sub_code: isv.business-failed:100010） | 请重试 |
| `50002` | 业务处理失败 / 100027:RPC请求失败（sub_code: isv.business-failed:100027） | 请重试 |
| `50002` | 业务处理失败 / 100023:参数校验出错（sub_code: isv.business-failed:100023） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "1000001",
    "code_msg": "success",
    "data": [
      {
        "app_type": "豆包",
        "author_coupon": "0",
        "author_id": "1231231231",
        "author_name": "达人名称示例",
        "bank_promotion": "0",
        "channel_promotion_fee": "0",
        "colonel_service_fee": "0",
        "commission": "0",
        "flow_type_desc": "小店自卖",
        "free_commission_flag": "是",
        "good_learn_channel_fee": "0",
        "goods_count": "10",
        "gov_promotion_amount": "0",
        "gov_promotion_shop_reduce_amount": "0",
        "is_contains_refund_before_settle": "0",
        "old_for_new_promotion": "0",
        "order_id": "4778345176320227200",
        "order_time": "2021-04-07 11:05:56",
        "order_type": "普通订单",
        "other_platform_promotion_amount": "0",
        "other_sharing_amount": "0",
        "packing_amount": "0",
        "partner_commission": "0",
        "pay_type_desc": "支付宝",
        "platform_coupon": "0",
        "platform_service_fee": "0",
        "post_amount": "0",
        "post_promotion_amount": "0",
        "product_id": "3461567267249244016",
        "product_name": "商品名称示例",
        "real_free_commission_amount": "0",
        "real_pay_amount": "0",
        "refund_before_settle": "0",
        "remark": "\"\"",
        "request_no": "6945807072718045454",
        "settle_amount": "950",
        "settle_time": "2021-05-17 11:05:56",
        "shop_coupon": "0",
        "shop_order_id": "4778345176320227200",
        "total_amount": "950",
        "total_goods_amount": "5",
        "total_income": "10",
        "total_outcome": "0",
        "trade_type": "0",
        "zr_pay_promotion": "0",
        "zt_pay_promotion": "0"
      }
    ],
    "data_size": "100",
    "is_end": "0",
    "next_start_index": "12345678",
    "next_start_time": "2021-05-18 03:00:00",
    "size": "100"
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
  "sub_code": "isv.parameter-invalid:100026",
  "sub_msg": "请检查参数"
}
```

## 备注
