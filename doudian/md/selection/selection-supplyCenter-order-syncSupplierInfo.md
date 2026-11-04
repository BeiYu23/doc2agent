# supplyCenter.order.syncSupplierInfo

> 支付前回传数据信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.order.syncSupplierInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5084 |
| 更新日期 | `2023-10-17` |

## 接口说明

- 文档书: 精选货源API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pur_order_id` | body | string | 是 | 精选货源订单号 | `12345` |
| `supplier_order_id` | body | string | 是 | 供货平台订单号 | `123` |
| `supplier_order_url` | body | object | 是 | 供货平台跳转链接 | `` |
| `  └ pc_url` | body | string | 是 | pc端 | `xx.com/xx` |
| `  └ h5_url` | body | string | 是 | h5端 | `xx.com/h5/xx` |
| `sku_orders` | body | array | 是 | 子订单信息 | `` |
| `  └ pur_sku_order_id` | body | string | 是 | 精选货源子订单号 | `123455` |
| `  └ supplier_sku_order_id` | body | string | 是 | 供货平台子订单号 | `123123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.order.syncSupplierInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
