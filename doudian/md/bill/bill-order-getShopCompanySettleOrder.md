# order.getShopCompanySettleOrder

> 获取抖超小时达子公司模式结算账单明细

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.getShopCompanySettleOrder` |
| 中文名 | 获取抖超小时达子公司模式结算账单明细 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getShopCompanySettleOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/2890 |
| 更新日期 | `2023-01-11` |

## 接口说明

- 文档书: 账单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | number | 是 | 页码，从0开始 | `0` |
| `page_size` | body | number | 是 | 分页大小，取值范围[1, 100] | `10` |
| `role_type` | body | string | 是 | 子公司，默认COMPANY； | `COMPANY` |
| `role_id` | body | string | 是 | 子公司id | `78155640` |
| `start_time` | body | string | 是 | 起始时间 | `2022-12-15 00:00:00` |
| `end_time` | body | string | 是 | 截止时间 | `2022-12-15 23:59:59` |
| `order_id` | body | string | 否 | 订单号（子单号维度，即sku单维度） | `5009587224845426593` |
| `pay_type` | body | string | 否 | 支付方式;PA-聚合支付，WX-微信支付； | `PA` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getShopCompanySettleOrder?app_key=your_appkey_here&method=order.getShopCompanySettleOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回码 | `100000` |
| `code_msg` | string | 返回消息 | `success` |
| `data` | array | 返回的订单信息 | `` |
| `page_no` | number | 页码 | `0` |
| `page_size` | number | 页面大小 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "100000",
    "code_msg": "success",
    "data": [
      {
        "author_coupon": "0",
        "channel_promotion_fee": "0",
        "colonel_service_fee": "0",
        "commission": "0",
        "contains_refund_before_settle": "否",
        "flow_type_desc": "小店自卖",
        "good_learn_channel_fee": "0",
        "goods_count": "1",
        "order_id": "5009587224845426593",
        "order_time": "2022-12-08 19:18:41",
        "order_type": "普通订单",
        "other_sharing_amount": "0",
        "other_sharing_amount_explain": "'",
        "packing_amount": "0",
        "pay_type_desc": "聚合账户",
        "platform_coupon": "0",
        "platform_service_fee": "12",
        "post_amount": "10",
        "product_id": "3576259793918237102",
        "real_pay_amount": "100",
        "refund_before_settle": "0",
        "remark": "'",
        "request_no": "7175898794666524986",
        "settle_amount": "100",
        "settle_time": "2022-12-15 16:24:14",
        "shop_coupon": "0",
        "shop_order_id": "5009587224845426593",
        "total_amount": "90",
        "total_goods_amount": "100",
        "total_income": "100",
        "total_outcome": "12",
        "trade_type_desc": "已结算",
        "zr_pay_promotion": "0",
        "zt_pay_promotion": "0"
      }
    ],
    "page_no": "0",
    "page_size": "10"
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
