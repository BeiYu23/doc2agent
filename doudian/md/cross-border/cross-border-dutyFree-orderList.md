# dutyFree.orderList

> 商家拉单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.dutyFree.orderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/dutyFree/orderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/703 |
| 更新日期 | `2021-07-22` |

## 接口说明

- 文档书: 跨境API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 是 | 开始时间 | `2018-06-03 00:00:00` |
| `end_time` | body | string | 是 | 结束时间，必须大于等于开始时间 | `2018-06-03 00:00:00` |
| `order_by` | body | string | 是 | 默认按订单（跨境履约单）创建时间搜索 | `create_time` |
| `is_desc` | body | string | 否 | 订单排序方式：0按时间升序， 1按时间降序 默认为1 | `1` |
| `order_list` | body | array | 否 | 需要查询的订单id列表 如果该字段不为空（列表至少包含 1 个订单号），此时参数只有vendor有用，其他参数不起作用。批量查询数量不超过100。 | `['order_id1','order_id2']` |
| `page` | body | number | 否 | 页数（默认为1） | `1` |
| `size` | body | number | 否 | 每页模板数（默认为10） | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/dutyFree/orderList?app_key=your_appkey_here&method=dutyFree.orderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 订单数据结构 | `-` |
| `has_next` | boolean | 是否还有下一页 | `true` |
| `total` | number | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 开始时间必须早于结束时间（sub_code: isv.business-failed:1002） | 请检查开始时间、结束时间 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "actural_paid": "2100",
        "buyer_id_number": "321312123243454",
        "buyer_id_type": "1",
        "buyer_name": "赵雷",
        "buyer_reg_no": "235345346454",
        "buyer_telephone": "15261890777",
        "consignee": "赵雷",
        "consignee_address": "{\"province\":{\"name\":\"江苏省\",\"id\":\"320000\"},\"city\":{\"name\":\"泰州市\",\"id\":\"321200\"},\"town\":{\"name\":\"姜堰区\",\"id\":\"321204\"},\"detail\":\"南苑二区5号楼102室\"}",
        "consignee_telephone": "15261890777",
        "create_time": "1624260016",
        "customs_clear_type": "4",
        "delivery_location": "**自提点地址",
        "delivery_method": "1",
        "discount": "400",
        "exp_ship_time": "1624260016",
        "freight": "0",
        "frequency_no": "HU7661",
        "goods_value": "2500",
        "leave_date": "1624260016",
        "leave_type": "2",
        "no_public_discount": "300",
        "order_date": "1624260016",
        "order_detail_list": [
          {
            "bar_code": "14324545",
            "cdf_category": "30",
            "coupon_amount": "300",
            "discount": "400",
            "fulldiscount_amount": "100",
            "is_suit": "1",
            "item_name": "SHERMY婴儿尿布裤",
            "original_price": "1250",
            "out_sku_id": "453464542343",
            "price": "1250",
            "qty": "2",
            "sku_id": "453464542343",
            "suit_num": "2",
            "total_price": "2500",
            "volume": "1000"
          }
        ],
        "order_id": "2021061619395010955",
        "pay_time": "1624260016",
        "pay_transaction_id": "2353453464542343",
        "pay_type": "1",
        "pre_sale_type": "1",
        "shop_id": "14802",
        "status": "100"
      }
    ],
    "has_next": "true",
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:1002",
  "sub_msg": "开始时间必须早于结束时间"
}
```

## 备注
