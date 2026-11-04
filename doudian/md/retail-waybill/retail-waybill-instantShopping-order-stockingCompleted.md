# 自提订单商家上报备货完成

> instantShopping.order.stockingCompleted — 自提订单商家上报备货完成

| 元信息 | 值 |
| --- | --- |
| 中文名 | 自提订单商家上报备货完成 |
| 文档地址 | `/docs/doudian/retail-waybill/retail-waybill-instantShopping-order-stockingCompleted` |
| 接口 ID | `doudian.retail-waybill.instantShopping.order.stockingCompleted` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1578/7258 |
| 更新日期 | `2025-08-14` |

## 接口说明

- 文档书: 电子面单API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 否 | 门店id | `155339026` |
| `shop_order_id` | body | string | 否 | 主订单号 | `6939269863945017210` |
| `device_code_list` | body | array | 否 | 设备码列表 | `` |
| `  └ sku_order_id` | body | string | 否 | 子订单号 | `6935074313978779194` |
| `  └ bar_code` | body | string | 否 | 69码 | `456` |
| `  └ serial_no` | body | string | 否 | 序列码 | `789` |
| `  └ imei_code` | body | array | 否 | IMEI码 | `["1234"]` |
| `sku_order_info_list` | body | array | 否 | sku单信息 | `` |
| `  └ sku_order_id` | body | string | 否 | sku单id | `"6935074313978779194"` |
| `  └ trace_info` | body | object | 否 | 溯源码信息 | `` |
| `    └ sku_order_id` | body | string | 否 | 对应sku单id | `"6935074313978779194"` |
| `    └ batch_and_trace_code_list` | body | array | 否 | 批次+溯源码list（设计为list是可能有多个item单） | `` |
| `      └ batch_code` | body | string | 否 | 批次code | `“123”` |
| `      └ trace_code` | body | string | 否 | 溯源码code | `“123”` |
| `scene` | body | string | 否 | 场景，上传溯源码【必传】upload_medical_trace_info | `upload_medical_trace_info` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.order.stockingCompleted&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:100001） | 参数错误 |
| `50002` | 业务处理失败 / 非本店铺订单，不允许操作（sub_code: isv.business-failed:200009） | 更换本店铺订单 |
| `20000` | 系统错误 / 查询订单失败，请重试（sub_code: isp.service-error:200010） | 查询订单失败，请重试 |
| `50002` | 业务处理失败 / 设备码必填信息为空（sub_code: isv.business-failed:200028） | 设备码必填信息为空 |
| `50002` | 业务处理失败 / 设备码校验失败（sub_code: isv.business-failed:200029） | 设备码校验失败 |
| `50002` | 业务处理失败 / 设备码保存失败（sub_code: isv.business-failed:200030） | 设备码保存失败 |
| `50002` | 业务处理失败 / 设备码占用失败（sub_code: isv.business-failed:200031） | 设备码占用失败 |
| `50002` | 业务处理失败 / 核销发码失败（sub_code: isv.business-failed:200032） | 核销发码失败 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:10001） | 系统异常 |

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
  "sub_code": "isv.missing-parameter:100001",
  "sub_msg": "参数错误"
}
```

## 备注
