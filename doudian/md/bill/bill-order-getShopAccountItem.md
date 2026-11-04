# order.getShopAccountItem

> 查询资金流水明细，查询方式为时间轮训方式，数据T+1生成，建议第二天10点之后查询。如因任务积压导致延迟的情况，建议重试。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.getShopAccountItem` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getShopAccountItem` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1430 |
| 更新日期 | `2026-03-19` |

## 接口说明

- 文档书: 账单API（版本 V1.19）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 否 | 开始时间 | `2021-10-01 00:00:00` |
| `end_time` | body | string | 否 | 结束时间 | `2021-10-01 23:59:59` |
| `order_id` | body | string | 否 | 订单号(如果订单号未传，则时间必须传) | `4847151209529677080` |
| `size` | body | string | 否 | 查询数量(不传默认100，最大为1000) | `100` |
| `account_type` | body | string | 否 | 动账账户 0: 所有 1: 微信 2:支付宝 3:合众支付 4:聚合支付 | `0` |
| `biz_type` | body | string | 否 | 计费类型 0:全部 1:鲁班广告 2:精选联盟 3:值点商城 4:小店自卖 5:橙子建站 6:POI 7:抖+ 8:穿山甲 9:服务市场 10:服务市场外包客服 11:学浪 | `0` |
| `time_type` | body | string | 否 | 时间类型 0 动账时间 1 下单时间 | `0` |
| `start_index` | body | string | 否 | 开始下标  请求值为上一次响应参数的next_index，第一次请求不传 | `d746da31eee45e65d07b20f87d6844bbf72041350acc66af1711408070b62428` |
| `product_id` | body | string | 否 | 产品id | `33323233` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回code 100000为成功，其他为失败 | `10000` |
| `code_msg` | string | 返回描述 | `SUCCESS` |
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
| `40004` | 非法的参数 / 500:参数异常，请检查参数start_time（sub_code: isv.parameter-invalid:500） | 请检查参数 |
| `20000` | 系统错误（sub_code: isp.service-error:100001） | 系统错误 |

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
  "sub_code": "isv.parameter-invalid:500",
  "sub_msg": "500:参数异常，请检查参数start_time"
}
```

## 备注
