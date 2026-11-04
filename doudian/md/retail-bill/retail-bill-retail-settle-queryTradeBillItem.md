# retail.settle.queryTradeBillItem

> 即时零售交易账单查询接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-bill.retail.settle.queryTradeBillItem` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/retail/settle/queryTradeBillItem` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1518/6772 |
| 更新日期 | `2026-07-16` |

## 接口说明

- 文档书: 账单管理API【即时零售】（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 是 | 查询开始时间，格式为：yyyy-MM-dd HH:mm:ss，订单号未传的情况下，开始时间必须传 | `2024-01-28 21:46:44` |
| `end_time` | body | string | 是 | 查询结束时间，和end_time的时间间隔建议不超过31天，格式为：yyyy-MM-dd HH:mm:ss，订单号未传的情况下，结束时间必须传 | `2024-08-29 21:46:44` |
| `time_type` | body | mixed | 是 | 时间类型   1 订单提交时间 2 订单完成时间  3 订单交易时间 4 订单结算时间 订单交易时间：正向用户支付完成时间，逆向退款完成时间 | `3` |
| `shop_order_id` | body | string | 否 | 店铺订单号(如果订单号未传，则时间必须传) | `6917560149869397892` |
| `order_id` | body | string | 否 | 子订单号(如果订单号未传，则时间必须传) | `6917560149869397892` |
| `cursor` | body | string | 是 | 查询游标，查询第一页时传空，后续查询使用前一次查询返回的next_cursor | `1716963724\|1689` |
| `size` | body | mixed | 是 | 查询数量，支持范围1～100 | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=retail.settle.queryTradeBillItem&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回code 100000为成功，其他为失败 | `100000` |
| `code_msg` | string | 返回信息描述，失败状态下会有失败描述 | `success` |
| `has_next` | boolean | 满足当前查询条件的数据是否还有下一批，true代表还有数据，false代表没有数据 | `false` |
| `next_cursor` | string | 下一次查询的游标 | `1716963724\|1689` |
| `data` | array | 交易账单流水明细 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 100023:参数校验出错（sub_code: isv.business-failed:100023） | 请校验参数 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "100000",
    "code_msg": "success",
    "data": [
      {
        "account_type": "2",
        "app_type": "豆包",
        "author_commission": "18",
        "author_coupon_amount": "1000",
        "author_id": "976",
        "author_name": "bKVDlsW4Gl",
        "bank_pay_promotion_amount": "888",
        "colonel_commission": "6",
        "delivery_type": "1",
        "dou_customer_commission": "789",
        "free_commission_desc": "次日达水果生鲜类目免佣；9.99元",
        "free_commission_flag": "0",
        "government_promotion_shop_reduce_amount": "200",
        "income_total_amount": "-140",
        "main_divide": "113",
        "main_shop_id": "1138798616",
        "main_shop_name": "3KnYIcv7cX",
        "medical_insurance_pay_amount": "123",
        "mixed_coupon_shop_cost_apport_amount": "409",
        "off_platform_pay_amount": "123",
        "order_create_time": "2024-05-20 21:02:40",
        "order_finish_time": "2024-05-22 21:02:40",
        "order_id": "3421163549898596541",
        "order_trade_time": "2024-05-21 21:02:40",
        "order_type": "1",
        "outcome_total_amount": "140",
        "packing_amount": "276",
        "partner_commission": "1234",
        "partner_name": "DAYINzEuN7",
        "partner_shop_id": "952",
        "pay_amount": "-72",
        "platform_service_fee": "3",
        "platform_service_fee_rate": "6.06",
        "post_amount": "510",
        "post_deduction_platform": "127",
        "post_deduction_shop": "821",
        "post_promotion_amount": "555",
        "product_price_total_amount": "1138798616",
        "promotion_amount": "-40",
        "recycler_amount": "999",
        "refund_sales_no": "236996231948147292",
        "remark": "备注",
        "settle_amount": "209",
        "settle_status": "1",
        "settle_time": "2024-05-23 21:02:40",
        "shop_coupon": "407",
        "shop_deduction_amount": "702",
        "shop_order_id": "441943063297378591",
        "source": "2",
        "store_divide": "35",
        "store_shop_id": "0",
        "store_shop_name": "J6zOGpScnG",
        "unit_divide": "20",
        "unit_shop_id": "0",
        "unit_shop_name": "PXACAWLLgr",
        "zr_platform_pay_promotion_amount": "777",
        "zt_platform_pay_promotion_amount": "666"
      }
    ],
    "has_next": "false",
    "next_cursor": "1716963724|1689"
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
  "sub_code": "isv.business-failed:100023",
  "sub_msg": "100023:参数校验出错"
}
```

## 备注
