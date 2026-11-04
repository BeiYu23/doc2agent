# order.downloadShopAccountItem

> 请求下载资金流水明细，得到download_id,download_id获取文件需要从order/downloadShopAccountItemFile接口获取，数据T+1生成，建议第二天15点之后下载

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.downloadShopAccountItem` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/downloadShopAccountItem` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1431 |
| 更新日期 | `2023-05-29` |

## 接口说明

- 文档书: 账单API（版本 V1.10）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 否 | 开始时间 | `2021-10-01 00:00:00` |
| `end_time` | body | string | 否 | 结束时间 | `2021-10-01 23:59:59` |
| `order_id` | body | string | 否 | 订单号(如果订单号未传，则时间必须传) | `4847151209529677080` |
| `account_type` | body | string | 否 | 动账账户 0: 所有 1: 微信 2:支付宝 3:合众支付 4:聚合支付 | `0` |
| `biz_type` | body | string | 否 | 计费类型 0:全部 1:巨量千川 2:精选联盟 3:值点商城 4:小店自卖 5:橙子建站 6:POI 7:抖+ 8:穿山甲 9:服务市场 10:服务市场外包客服 11:学浪 | `0` |
| `time_type` | body | string | 否 | 时间类型 0 动账时间 1 下单时间 | `0` |
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
| `download_id` | string | 下载id，有效期24小时 | `DL202110261638110918901284` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数异常，请检查参数（sub_code: isv.parameter-invalid:500） | 输入合法参数 |

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
  "sub_msg": "参数异常，请检查参数"
}
```

## 备注
