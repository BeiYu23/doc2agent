# 查询资金流水明细

> sendHome.settle.getShopAccountItem — 查询资金流水明细，查询方式为时间轮训方式，数据T+1生成，建议第二天15点之后查询。如因任务积压导致延迟的情况，建议重试。
如果流水明细为订单相关，会关联门店ID与门店商家自编码。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询资金流水明细 |
| 文档地址 | `/docs/doudian/bill/bill-sendHome-settle-getShopAccountItem` |
| 接口 ID | `doudian.bill.sendHome.settle.getShopAccountItem` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/6641 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 账单API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `end_time` | body | string | 否 | 查询结束时间 | `2021-10-01 23:59:59` |
| `order_id` | body | string | 否 | 子订单ID(如果订单号未传，则时间必须传) | `4847151209529677080` |
| `time_type` | body | string | 否 | 时间类型 0 动账时间 1 下单时间 | `0` |
| `product_id` | body | string | 否 | 产品id | `33323233` |
| `start_time` | body | string | 否 | 查询开始时间 | `2021-10-01 00:00:00` |
| `size` | body | string | 否 | 查询数量(不传默认100，最大为1000) | `100` |
| `account_type` | body | string | 否 | 动账账户 0: 所有 1: 微信 2:支付宝 3:合众支付 4:聚合支付 | `0` |
| `biz_type` | body | string | 否 | 计费类型 0:全部 1:巨量千川 2:精选联盟 3:值点商城 4:小店自卖 5:橙子建站 6:POI 7:抖+ 8:穿山甲 9:服务市场 10:服务市场外包客服 11:学浪 | `0` |
| `start_index` | body | string | 否 | 开始下标 请求值为上一次响应参数的next_index，第一次请求不传 | `d746da31eee45e65d07b20f87d6844bbf72041350acc66af1711408070b62428` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=order.shopOperate.getSkuReviewResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 资金流水明细 | `` |
| `next_start_index` | string | 下一次请求参数start_index 的值 | `d746da31eee45e65d07b20f87d6844bbf72041350acc66af1711408070b62428` |
| `next_start_time` | string | 下一次请求参数start_time的值 | `2021-10-01 06:00:00` |
| `size` | string | 查询数量，请求参数size传了值得话为请求参数传的值，未传的话，值为100 | `100` |
| `data_size` | string | 返回结果data的数量 | `100` |
| `is_end` | string | 判断查询是否结束。0 未结束, 1 结束。未结束时，需要把next_start_index作为下一次请求的start_index,next_start_time作为下一次请求的start_time。 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入必填参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常-不可重试的错误（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常-可重试（sub_code: isp.service-error:5100002） | 系统异常，可尝试重试 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:4100001",
  "sub_msg": "缺少必填参数"
}
```

## 备注
