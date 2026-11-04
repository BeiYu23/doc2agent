# 商家_商家送检线下质检订单

> btas.saveInspectionInfo — 商家_商家送检线下质检订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家_商家送检线下质检订单 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-saveInspectionInfo` |
| 接口 ID | `doudian.btas-inspect.btas.saveInspectionInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/saveInspectionInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/574 |
| 更新日期 | `2021-06-07` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.09）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 父订单（店铺单）编号 | `4775168038676399798` |
| `product_order_id` | body | string | 否 | 首次录入时必输 商品单ID | `4775168038676399798` |
| `order_code` | body | string | 否 | 首次录入时必输 一件商品一个订单码，订单码由字节系统生成。 订单码 | `0123456787` |
| `service_status` | body | string | 是 | 枚举值 1: 新增   2: 修改 | `1` |
| `base_send_logistics_code` | body | string | 否 | service_status 是2 的时候使用，当且仅当 送检方式为邮寄时，且需要修改送检的运单号时：必输，输入时必须与send_logistics_code不同 若仅需要质检机构发货的信息、拦截发货时 则product_order_id、order_code 必输 优先检查base_send_logistics_code 修改送检面单时，基于该店铺单下的运单号进行修改 | `SF12345678901` |
| `send_type` | body | string | 是 | 送检方式 1：快递送检：通过物流快递将商品送到质检机构； 2：线下送检：非物流快递将商品送到质检机构； 当选择自发货时，必须使用线下送检 首次录入时用，不支持修改 | `1` |
| `send_logistics_id` | body | string | 否 | 可以为空（线下送检时）；否则必输 物流公司ID，由接口/order/logisticsCompanyList返回的物流公司列表中对应的ID | `1` |
| `send_logistics_company_code` | body | string | 否 | 预留：物流公司编码 | `shunfeng` |
| `send_logistics_code` | body | string | 否 | 可以为空（线下送检时）；否则必输 快递送检运单号 | `SF12345678901` |
| `is_shipping_self` | body | string | 是 | 0：否  即：质检完成后，质检机构将商品发货给顾客  1：是  即：质检完成后，商家拿回商品，自行发货给顾客；或者是大商派人到商家侧完成质检，然后商家自行发货。 该字段与订单取消后流程有关，注意正确传参  首次录入时用，不支持修改 | `0` |
| `shipping_logistics_type` | body | string | 否 | 质检机构发货时的物流类型，可以为空（自发货时）；否则必输入。 1：顺丰标快； 2：顺丰特惠； | `1` |
| `insurance_cost` | body | string | 否 | 可以为空（自发货时）；否则必输 质检机构代发货时，若发顾客物流需要保价，则录入保价金额，不能高于订单金额。若无需保价则为0 单位为分 | `200` |
| `return_intercept_type` | body | string | 是 | 0：发货优先：线下送检，客户在质检方收货前申请退款，系统将在质检收货环节驳回退款，继续履约。 1：售后优先：线下送检，客户在质检方收货前申请退款，质检方将无法收货鉴定送检商品，并退回给商家（或等待商家处理完成退款申请再做质检）。 自发货时，建议选择正常发货，否则可能出现卡单 | `0` |
| `return_type` | body | string | 否 | 可以为空（自发货时）；否则必输 1：邮寄：若质检过程中订单取消，质检机构将商品邮寄回商家； 2：商家自提：若质检过程中订单取消，商家需要到质检机构处自己取回商品。 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/queryPaymentStatus?app_key=your_appkey_here&method=logistics.queryPaymentStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 状态检查失败，订单不为商家备货，不可送检（sub_code: isv.business-failed:10000） | 无法送检 |
| `50002` | 业务处理失败 / 订单不存在（sub_code: isv.business-failed:4000） | 请检查订单信息 |
| `50002` | 业务处理失败 / 线上质检订单请通过小程序进行操作（sub_code: isv.business-failed:2001） | 线上质检订单请通过小程序进行操作 |
| `50002` | 业务处理失败 / 2030:参数错误（sub_code: isv.business-failed:2030） | - |
| `50002` | 业务处理失败 / 拦截发货时候请先处理退款请求（sub_code: isv.business-failed:2036） | 拦截发货时候请先处理退款请求 |
| `50002` | 业务处理失败 / 1201:获取锁失败（sub_code: isv.business-failed:1201） | - |

## 响应示例

成功：

```json
{
  "data": {
    "encourageFee": "11",
    "insuranceClaimFee": "11",
    "insureClaimFee": "11",
    "operationTime": "2021-01-19 10:00:00",
    "paymentFee": "11",
    "paymentStatus": "1",
    "platformAllowance": "11"
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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "状态检查失败，订单不为商家备货，不可送检"
}
```

## 备注
