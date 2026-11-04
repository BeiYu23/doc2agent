# order.orderCancel

> 商家取消待支付订单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.orderCancel` |
| 中文名 | 商家取消待支付订单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/orderCancel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/3381 |
| 更新日期 | `2023-03-30` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 店铺主订单号 | `5050438739367795793` |
| `cancel_reason` | body | string | 是 | 取消原因必须是如下枚举之一：①：用户重复下单②：用户不想买了③：用户买错了/信息填错了④重新下单、联系不上用户⑥：快递无法配送至用户地址⑦：其他；注意请使用枚举值信息，如“用户重复下单”必须要一致，开发者请勿自定义或带有空格等信息，否则无法通过接口校验； | `用户不想买了` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/orderCancel?app_key=your_appkey_here&method=order.orderCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单已取消（sub_code: isv.business-failed:50005） | 订单已取消，无需重试 |
| `50002` | 业务处理失败 / 距用户下单时间未超过1分钟，请稍后再试（sub_code: isv.business-failed:50007） | 距用户下单时间未超过1分钟，请稍后再试 |
| `40002` | 缺少必选参数 / 订单id不能为空（sub_code: isv.missing-parameter:50001） | 订单id不能为空 |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:50002） | 请检查参数 |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:50003） | 请检查参数 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:50004） | 业务处理失败，请稍后重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:70007） | 业务处理失败，请稍后重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:50021） | 业务处理失败，请稍后重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:50060） | 业务处理失败，请稍后重试 |
| `50002` | 业务处理失败 / 定金预售订单不支持取消（sub_code: isv.business-failed:50047） | 定金预售订单不支持取消 |
| `50002` | 业务处理失败 / 当前订单为竞拍订单，不允许取消（sub_code: isv.business-failed:50061） | 当前订单为竞拍订单，不允许取消 |
| `50002` | 业务处理失败 / 当前订单使用了跨店优惠，仅允许买家主动取消（sub_code: isv.business-failed:50048） | 当前订单使用了跨店优惠，仅允许买家主动取消 |
| `50002` | 业务处理失败 / 保险类订单不支持取消（sub_code: isv.business-failed:50046） | 保险类订单不支持取消 |
| `50002` | 业务处理失败 / 拍卖类订单不支持取消（sub_code: isv.business-failed:50057） | 拍卖类订单不支持取消 |
| `50002` | 业务处理失败 / 拍卖保证金订单不支持取消（sub_code: isv.business-failed:50058） | 拍卖保证金订单不支持取消 |
| `50002` | 业务处理失败 / 货到付款订单已完成后不允许取消（sub_code: isv.business-failed:50059） | 货到付款订单已完成后不允许取消 |
| `50002` | 业务处理失败 / 货到付款订单已发货后不允许取（sub_code: isv.business-failed:50008） | 货到付款订单已发货后不允许取 |
| `80000` | 风控拦截 / 业务处理失败（sub_code: isv.risk-control-failed:50999） | 业务处理失败，请检查取消原因 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:20003） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:50009） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 已付款订单不允许取消（sub_code: isv.business-failed:50006） | 已付款订单不允许取消 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:50005",
  "sub_msg": "订单已取消"
}
```

## 备注
