# 售后列表接口

> afterSale.List — 1、售后列表接口，可以支持多种筛选规则，详情见请求参数。
2、时间类型参数均为以秒为单位的时间戳，金额均以分为单位。
3、接口中page*size最多不能超过5万条数据。如果超过5万条，请使用时间参数分割数据。
4、默认情况下，只能查到近6个月以内的数据，

| 元信息 | 值 |
| --- | --- |
| 中文名 | 售后列表接口 |
| 文档地址 | `/docs/doudian/refund/refund-afterSale-List` |
| 接口 ID | `doudian.refund.afterSale.List` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/List` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/1295 |
| 更新日期 | `2025-04-27` |

## 接口说明

- 文档书: 售后退款API（版本 V19.16）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 父订单号 | `4821845786203981633` |
| `aftersale_type` | body | number | 否 | 售后类型；0-退货退款；1-已发货退款；2-未发货退款；3-换货；6-价保；7-补寄；8-维修 | `1` |
| `aftersale_status` | body | number | 否 | 已废弃，推荐使用standard_aftersale_status字段。售后状态，枚举为6(待商家同意),7(待买家退货),8(待商家发货),11(待商家二次同意),12(售后成功),13(换货待买家收货),14(换货成功),27(商家一次拒绝),28(售后失败),29(商家二次拒绝) | `2` |
| `reason` | body | number | 否 | 售后理由；1-七天无理由退货；2-非七天无理由退货； | `1` |
| `logistics_status` | body | number | 否 | 退货物流状态，枚举为1(全部),2(已发货),3(未发货) | `2` |
| `pay_type` | body | number | 否 | 付款方式，枚举为1(全部), 2(货到付款),3(线上付款) | `2` |
| `refund_type` | body | number | 否 | 退款类型，枚举为0(原路退款),1(线下退款),2(备用金),3(保证金),4(无需退款) | `1` |
| `arbitrate_status` | body | array | 否 | 仲裁状态，枚举为0(未介入),1(客服处理中),2(仲裁结束-支持买家),3(仲裁结束-支持卖家),4(待商家举证),5(待与买家协商),6(仲裁结束),255(取消) | `0` |
| `order_flag` | body | array | 否 | 插旗信息：0：灰 1：紫 2: 青 3：绿 4： 橙 5： 红 | `[1,2,3]` |
| `start_time` | body | number | 否 | 申请时间开始，单位为秒（查询范围包含开始值） | `1626770133` |
| `end_time` | body | number | 否 | 申请时间结束，单位为秒（查询范围不包含结束值） | `1626856525` |
| `amount_start` | body | number | 否 | 金额下限，单位为分（查询范围包含开始值） | `300` |
| `amount_end` | body | number | 否 | 金额上限，单位为分（查询范围不包含结束值） | `1000` |
| `risk_flag` | body | number | 否 | 风控标签，枚举为-1(退货正常),1(退货异常) | `-1` |
| `order_by` | body | array | 否 | 排序方式，优先级按照列表顺序从前往后依次减小，写法为"<字段名称> <排序方式>"，字段名称目前支持"status_deadline"（逾期时间）、"apply_time"（申请时间）和 "update_time"（更新时间），排序方式目前支持"asc"（升序）和"desc"（降序）。按照"逾期时间"升序排列，会优先返回临近逾期时间的数据。 | `["status_deadline desc"]` |
| `page` | body | number | 是 | 页数，从0开始 | `0` |
| `size` | body | number | 是 | 每页数量，最多100个 | `50` |
| `aftersale_id` | body | string | 否 | 售后单号 | `6987272148133888300` |
| `standard_aftersale_status` | body | array | 否 | 售后状态；6-待商家同意；7-待买家退货；8-待商家发货；11-待商家二次同意；12-售后成功；13-换货\补寄\维修待买家收货；14-换货\补寄\维修成功；27-商家一次拒绝；28-售后失败；29-商家二次拒绝；支持传多种状态，使用英文“,”分隔；注意：如传入非枚举值信息会被系统忽略，如传入都不合法则默认查询所有； | `[6,7,11]` |
| `need_special_type` | body | boolean | 否 | 是否展示特殊售后 | `true/false` |
| `update_start_time` | body | number | 否 | 更新时间开始，单位为秒（查询范围包含开始值）；当使用update_start_time和update_end_time时，请配合传入order_by= update_time否则会导致基于更新时间查询售后列表轮询数据遗漏； | `1626856525` |
| `update_end_time` | body | number | 否 | 更新时间结束，单位为秒（查询范围包含开始值）；当使用update_start_time和update_end_time时，请配合传入order_by= update_time否则会导致基于更新时间查询售后列表轮询数据遗漏； | `1626856525` |
| `order_logistics_tracking_no` | body | array | 否 | 正向物流单号 | `["SF12345678910"]` |
| `order_logistics_state` | body | array | 否 | 正向物流状态（仅支持拒签场景下的状态筛选，状态更新有一定时延。1：买家已拒签；2：买家已签收；3：快递退回中，运往商家，包含快递拦截成功；4：商家已签收） | `[1,2,3,4]` |
| `agree_refuse_sign` | body | array | 否 | 是否拒签后退款（1：已同意拒签, 2：未同意拒签） | `[1,2]` |
| `aftersale_sub_type` | body | number | 否 | 售后子类型；8001-以换代修。 | `8001` |
| `aftersale_status_to_final_start_time` | body | number | 否 | 售后完结时间开始，单位为秒（查询范围包含开始值），仅支持售后完结时间在近6个月内的售后单，按完结时间筛选；售后完结时间生成规则是平台根据商品的类型，售后状态等综合判断生成，当售后单有完结时间返回时售后单不可再做任何操作； | `1626856525` |
| `aftersale_status_to_final_end_time` | body | number | 否 | 售后完结时间结束，单位为秒（查询范围包含开始值），仅支持售后完结时间在近6个月内的售后单，按完结时间筛选；售后完结时间生成规则是平台根据商品的类型，售后状态等综合判断生成，当售后单有完结时间返回时售后单不可再做任何操作； | `1626856525` |
| `store_id_list` | body | array | 否 | 即时零售专用, 查询门店id list入参 其中最多传入50个门店id | `[1626856525,1123416]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 售后列表元素 | `` |
| `has_more` | boolean | 是否还有更多 | `true` |
| `total` | number | 当前搜索条件下，匹配到的总数量 | `1025` |
| `page` | number | 页码，从0开始 | `0` |
| `size` | number | 当前返回售后数量 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:11000） | 请检查输入参数是否合法 |
| `20000` | 系统错误 / 系统超时（sub_code: isp.service-error:10000） | 请重试 |
| `20000` | 系统错误 / 系统处理失败（sub_code: isp.service-error:10002） | 请重试 |
| `40004` | 非法的参数 / 数据不存在（sub_code: isv.parameter-invalid:11003） | 请检查输入参数是否合法 |
| `50002` | 业务处理失败 / 系统处理失败（sub_code: isv.business-failed:12001） | 请检查输入参数是否合法 |
| `50002` | 业务处理失败 / 未知错误（sub_code: isv.business-failed:12000） | 请辛苦联系平台排障 |

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
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误"
}
```

## 备注
