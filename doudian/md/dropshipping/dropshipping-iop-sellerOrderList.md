# iop.sellerOrderList

> 【商家】查看代发订单列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.sellerOrderList` |
| 中文名 | 【商家】查看代发订单列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/sellerOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/960 |
| 更新日期 | `2021-09-09` |

## 接口说明

- 文档书: 代发API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_update_time` | body | number | 否 | 与订单成交时间段二选一传入，更新时间开始时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总秒数 PS：开始时间结束时间间距不超过半小时 | `1625628558` |
| `end_update_time` | body | number | 否 | 与订单成交时间段二选一传入，更新时间结束时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总秒数 PS：开始时间结束时间间距不超过半小时 | `1625628558` |
| `page` | body | number | 是 | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `0` |
| `size` | body | number | 是 | 返回数量，最大 100 | `10` |
| `product_name` | body | string | 否 | 商品名称，模糊查询，商家可以根据商品筛选所有的订单，分配给某个厂商 | `鞋子` |
| `product_id` | body | string | 否 | 商品ID | `3473196049974326153` |
| `shop_order_id` | body | string | 否 | 店铺订单号（父订单号） | `4781320682406083640` |
| `order_status` | body | string | 否 | 订单状态 101-部分发货 2-备货中 3-已发货 4-已关闭 5-已完成 | `2` |
| `distr_order_id` | body | string | 否 | 代打订单号 | `77878786688878787` |
| `distr_status` | body | string | 否 | 分配状态0-未分配 1-已经分配 2-已回传 3-已取消 | `1` |
| `after_sale_status` | body | string | 否 | 售后状态 1-无售后 2-售后中 | `1` |
| `supplier_shop_id` | body | number | 否 | 绑定的厂商的店铺ID | `77977` |
| `province_id` | body | string | 否 | 省ID | `11000` |
| `start_deal_time` | body | number | 否 | 与更新时间段二选一传入，订单成交开始时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总毫秒数 PS：开始时间结束时间间距不超过半小时 | `1630482091` |
| `end_deal_time` | body | number | 否 | 与更新时间段二选一传入，订单成交结束时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总毫秒数 PS：开始时间结束时间间距不超过半小时 | `1630482091` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/sellerOrderList?app_key=your_appkey_here&method=iop.sellerOrderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `distr_order_list` | array | 代打订单列表 | `` |
| `page` | number | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `0` |
| `size` | number | 返回数量，最大 100 | `20` |
| `total` | number | 订单总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20000） | 系统繁忙，请稍后重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 请检查参数 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:10005） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:1000） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10008） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "distr_order_list": [
      {
        "after_sale_status": "1",
        "city": "北京",
        "city_id": "110000",
        "company_name": "shunfeng",
        "distr_cancel_reason": "订单已取消",
        "distr_order_id": "2222333332223",
        "distr_status": "1",
        "distr_time": "1630484005",
        "district": "海淀",
        "district_id": "110000",
        "exp_ship_time": "1630484005",
        "order_status": "2",
        "out_sku_id": "123123",
        "pack_list": [
          {
            "company_code": "jd",
            "track_no": "123456"
          }
        ],
        "pay_time": "1630484005",
        "product_count": "1",
        "product_id": "2313131313",
        "product_name": "鞋子",
        "product_price": "1000",
        "province": "北京",
        "province_id": "110000",
        "seller_words": "发货黑色",
        "serial_number_list": "[\"546443524543534\",\"646443524543534\"]",
        "ship_time": "1630484005",
        "shop_order_id": "22131323322",
        "sku_spec": "褐色",
        "street": "中关村",
        "street_id": "110000",
        "supplier_shop_id": "77977",
        "supplier_shop_name": "厂家店铺名",
        "tracking_no": "5443445"
      }
    ],
    "page": "0",
    "size": "20",
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:20000",
  "sub_msg": "系统繁忙，请稍后重试"
}
```

## 备注
