# order.downloadSettleItemToShop

> 1、通过url方式，下载文件生成结算账单下单接口，调用接口生成个download_id ，通过返回的download_id调用【/order/downloadToShop】查询下载url文件链接。如果当天账单数据未完全生成会拦截下载请求。
2、如需非url

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.downloadSettleItemToShop` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/downloadSettleItemToShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1191 |
| 更新日期 | `2023-01-12` |

## 接口说明

- 文档书: 账单API（版本 V2.07）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 是 | 开始时间 | `2021-02-01 17:06:49` |
| `end_time` | body | string | 是 | 结束时间 | `2021-03-21 17:06:49` |
| `time_type` | body | string | 是 | 时间类型 0:结算时间 1：下单时间 | `0` |
| `order_id` | body | string | 否 | 订单ID | `1222333333` |
| `bill_id` | body | string | 否 | 字段已作废,勿填 | `1234555` |
| `product_id` | body | string | 否 | 商品ID | `123456` |
| `pay_type` | body | string | 否 | 结算账户 0:全部 1:微信（升级前） 2:微信 3:支付宝 4:合众支付 5:聚合账户 | `0` |
| `flow_type` | body | string | 否 | 业务类型，不传则默认为0 0:全部 1:巨量千川, 2:值点商城, 3:精选联盟  4:小店自卖 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `download_id` | string | 下载id，通过返回的download_id调用【/order/downloadToShop】查询下载url文件链接。 | `DL202108191056192174226975` |
| `code` | string | 状态码 | `100000` |
| `code_msg` | string | 状态信息 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 账单明细未完全生成，暂不支持下载，避免下载的明细数据不全（sub_code: isv.business-failed:100027） | 等5分钟之后重试 |

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
  "sub_code": "isv.business-failed:100027",
  "sub_msg": "账单明细未完全生成，暂不支持下载，避免下载的明细数据不全"
}
```

## 备注
