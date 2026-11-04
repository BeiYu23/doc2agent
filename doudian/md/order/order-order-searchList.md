# order.searchList

> 根据条件检索满足要求的订单列表，支持下单时间和更新时间排序；最大支持查询近90天的数据；注意！订单在风控中时请勿发货！

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.searchList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/searchList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1342 |
| 更新日期 | `2026-08-31` |

## 接口说明

- 文档书: 订单API（版本 V22.28）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product` | body | string | 否 | 商品，number型代表商品ID，其它代表商品名称 | `3473196049974326153` |
| `b_type` | body | number | 否 | 【下单端】 0、站外   1、火山   2、抖音   3、头条   4、西瓜   5、微信   6、值点app  7、头条lite   8、懂车帝  9、皮皮虾   11、抖音极速版   12、TikTok   13、musically   14、穿山甲   15、火山极速版   16、服务市场   26、番茄小说   27、UG教育营销电商平台   28、Jumanji   29、电商SDK | `2` |
| `after_sale_status_desc` | body | string | 否 | 售后状态：all-全部，in_aftersale-售后中，refund-退款中，refund_success-退款成功，refund_fail-退款失败，exchange_success-换货成功 aftersale_close-售后关闭 | `refund_success` |
| `tracking_no` | body | string | 否 | 物流单号 | `435435` |
| `presell_type` | body | number | 否 | 预售类型：0-普通订单；1-全款预售；2-定金预售；3-定金找货； | `0` |
| `order_type` | body | number | 否 | 订单类型 0、普通订单 2、虚拟商品订单 4、电子券（poi核销） 5、三方核销 | `1` |
| `create_time_start` | body | number | 否 | 下单时间：开始，秒级时间戳 | `1617355413` |
| `create_time_end` | body | number | 否 | 下单时间：截止，秒级时间戳 | `1617355413` |
| `abnormal_order` | body | number | 否 | 异常订单，1-异常取消，2-风控审核中 | `1` |
| `trade_type` | body | number | 否 | 交易类型：0-普通；1-拼团；2-定金预售；3-订金找货；4-拍卖；5-0元单；6-回收；7-寄卖；10-寄样；11-0元抽奖(超级福袋)；12-达人买样；13-普通定制；16-大众竞拍；18-小时达；102-定金预售的赠品单；103-收款； | `1` |
| `combine_status` | body | array | 否 | 状态组合查询，直接输入状态码（只支持一个元素） | `` |
| `  └ order_status` | body | string | 否 | 订单状态，","分隔多个状态；1-待支付；101-部分发货；105-已支付；2-待发货；3-已发货；4-已取消；5-已完成；注意！订单在风控中时请勿发货！ | `1` |
| `  └ main_status` | body | string | 否 | 【已废弃，不推荐使用】主流程状态，","分隔多个状态； | `103` |
| `update_time_start` | body | number | 否 | 更新时间：开始 | `1617355413` |
| `update_time_end` | body | number | 否 | 更新时间：截止 | `1617355413` |
| `size` | body | number | 是 | 单页大小，限制100以内 | `20` |
| `page` | body | number | 是 | 页码，0页开始 | `0` |
| `order_by` | body | string | 否 | 排序条件(create_time 订单创建时间；update_time 订单更新时间；默认create_time；) | `create_time` |
| `order_asc` | body | boolean | 否 | 排序类型，小到大或大到小，默认大到小 | `false` |
| `fulfil_status` | body | string | 否 | 履约状态；如小时达未接单"no_accept" | `no_accept` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `page` | number | 页数，从0开始 | `1` |
| `total` | number | 总订单数 | `1000` |
| `size` | number | 单页大小 | `20` |
| `shop_order_list` | array | 订单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 订单查询只支持查询最近90天内的数据（sub_code: isv.parameter-invalid:20022） | 需要把下单开始时间设置为最近90天内的时间（如果没有传下单开始时间会默认设置当前时间90天前的时间为下单开始时间） |
| `40004` | 非法的参数 / 订单查询最多支持查询5万（sub_code: isv.parameter-invalid:20013） | 翻页查询最多支持查询到5万，需要缩短查询时间范围，降低查询的订单量 |
| `40004` | 非法的参数 / 订单查询状态条件超过限制，只支持1个元素（sub_code: isv.parameter-invalid:20012） | 状态查询条件是list，但现在只支持传入一个元素，重新组装参数查询 |
| `40004` | 非法的参数 / 订单查询开始时间不能为空（sub_code: isv.parameter-invalid:20011） | 时间为必传项，下单开始时间和更新开始时间必传一个 |
| `40004` | 非法的参数 / 单次查询订单数超过限制（sub_code: isv.parameter-invalid:20008） | 单页最大支持100，size设置需要 <= 100 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20005） | 如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20004） | 如遇到该报错，建议再30秒内重试3~5次，如还是报错可提交工单咨询 |
| `40004` | 非法的参数 / 查询订单列表页数不能小于0（sub_code: isv.parameter-invalid:10035） | 查询页数从0开始，需要输入大于等于0的数 |
| `50002` | 业务处理失败 / 店铺ID不能为空（sub_code: isv.business-failed:20009） | 需要传入店铺ID |
| `40004` | 非法的参数 / 查询结果中包含非该门店下订单（sub_code: isv.parameter-invalid:20045） | 需传入合法的订单id |
| `50002` | 业务处理失败 / 20059:查询免息信息错误，请稍后重试（sub_code: isv.business-failed:20059） | 请重试 |

## 响应示例

成功：

```json
{
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
