# retail.downloadSupermarketTradeBillItem

> 即时零售交易账单下载

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-bill.retail.downloadSupermarketTradeBillItem` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/retail/downloadSupermarketTradeBillItem` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1518/7184 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 账单管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 是 | 查询开始时间，格式为：yyyy-MM-dd HH:mm:ss | `2024-11-28 21:46:44` |
| `end_time` | body | string | 是 | 查询结束时间，和end_time的时间间隔建议不超过31天，格式为：yyyy-MM-dd HH:mm:ss | `2024-11-29 21:46:44` |
| `time_type` | body | mixed | 是 | 时间类型 1 订单提交时间 2 订单完成时间 3 订单交易时间 4 订单结算时间 订单交易时间：正向用户支付完成时间，逆向退款完成时间 | `3` |
| `shop_order_id` | body | string | 否 | 店铺订单号 | `6917560149869397892` |
| `order_id` | body | string | 否 | 子订单号 | `6917560149869397892` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/retail/downloadSupermarketTradeBillItem?app_key=your_appkey_here&method=retail.downloadSupermarketTradeBillItem&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回code 100000为成功，其他为失败 | `100000` |
| `code_msg` | string | 返回描述 | `SUCCESS` |
| `download_id` | string | 下载id，有效期24小时 | `DL202410261638110918901284` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "100000",
    "code_msg": "SUCCESS",
    "download_id": "DL202410261638110918901284"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
