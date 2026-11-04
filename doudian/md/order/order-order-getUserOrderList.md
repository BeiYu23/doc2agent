# 支持按抖店open_id或抖音小程序open_…

> order.getUserOrderList — 支持按抖店open_id或抖音小程序open_id查询订单简要信息，仅电商小程序在C端面向用户呈现订单任务类场景使用

| 元信息 | 值 |
| --- | --- |
| 中文名 | 支持按抖店open_id或抖音小程序open_… |
| 文档地址 | `/docs/doudian/order/order-order-getUserOrderList` |
| 接口 ID | `doudian.order.order.getUserOrderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getUserOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1915 |
| 更新日期 | `2022-05-12` |

## 接口说明

- 文档书: 订单API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `create_time_start` | body | number | 否 | 下单时间：开始，秒级时间戳 | `1617355413` |
| `create_time_end` | body | number | 否 | 下单时间：截止，秒级时间戳 | `1617355413` |
| `size` | body | number | 是 | 单页大小，限制100以内 | `20` |
| `page` | body | number | 是 | 页码，0页开始 | `0` |
| `open_id` | body | string | 是 | 用户openId | `3b829624-67bc-5c26-93be-32d9bc7c1922` |
| `open_id_type` | body | string | 是 | 用户openId类型，固定为 douyin 抖音 | `douyin` |
| `order_status` | body | string | 否 | 订单状态：all-全部，under_sure-待确认，unpaid-待支付，stock_up-待发货，on_delivery-已发货，received-已完成，closed-已关闭，to_groups-待成团 | `under_sure` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getUserOrderList?app_key=your_appkey_here&method=order.getUserOrderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `page` | number | 页数，从0开始 | `0` |
| `total` | number | 总订单数 | `1000` |
| `size` | number | 单页大小 | `20` |
| `shop_order_list` | array | 订单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 订单查询只支持查询最近90天内的数据（sub_code: isv.parameter-invalid:20022） | 把下单开始时间设置为最近90天内 |
| `40004` | 非法的参数 / 订单查询最多支持查询5万（sub_code: isv.parameter-invalid:20013） | 缩短查询时间范围 |
| `40004` | 非法的参数 / 订单查询状态条件超过限制，只支持1个元素（sub_code: isv.parameter-invalid:20012） | 状态查询条件是list，但现在只支持传入一个元素，重新组装参数查询 |
| `40004` | 非法的参数 / 单次查询订单数超过限制（sub_code: isv.parameter-invalid:20008） | 单页最大支持100，size设置需要 u003c= 100 |
| `40004` | 非法的参数 / 系统繁忙，请稍后重试（sub_code: isv.parameter-invalid:20005） | 如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `40004` | 非法的参数 / 系统繁忙，请稍后重试（sub_code: isv.parameter-invalid:20004） | 如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "0",
    "shop_order_list": [
      {
        "create_time": "1617355413",
        "order_id": "4781320682406083640",
        "order_status": "3",
        "pay_amount": "500",
        "sku_order_list": [
          {
            "sku_info": {
              "product_id": "3473196049974326153",
              "product_name": "衣服",
              "sku_id": "3254535"
            }
          }
        ]
      }
    ],
    "size": "20",
    "total": "1000"
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
  "sub_code": "isv.parameter-invalid:20022",
  "sub_msg": "订单查询只支持查询最近90天内的数据"
}
```

## 备注
