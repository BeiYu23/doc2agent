# 上传序列号

> order.batchBindSerialNumber — 上传序列号

| 元信息 | 值 |
| --- | --- |
| 中文名 | 上传序列号 |
| 文档地址 | `/docs/doudian/order/order-order-batchBindSerialNumber` |
| 接口 ID | `doudian.order.order.batchBindSerialNumber` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/batchBindSerialNumber` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7383 |
| 更新日期 | `2025-03-27` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bind_list` | body | array | 否 | 绑定列表; | `` |
| `  └ shop_order_id` | body | string | 否 | 订单号; | `"6940658920780535662"` |
| `  └ sku_order_id` | body | string | 否 | Sku单号; | `"6940658920780535662"` |
| `  └ serial_no_list` | body | array | 否 | 序列号信息; | `` |
| `    └ value` | body | array | 否 | 序列号相关的信息; | `{"1","2"}` |
| `    └ key` | body | string | 否 | 序列号类型,SN - SN码，69 - 69码，IMEI - IMEI码; 对于空调国补，内机SN对应SN_INDOOR，外机SN对应SN_OUTDOOR | `"SN"` |
| `bind_scene` | body | string | 否 | 绑定场景  1 // 发货后  2 // 发货前 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/addV2?app_key=your_appkey_here&method=product.addV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total_fail_bind_cnt` | number | 绑定失败的数量; | `1` |
| `success_bind_list` | array | 成功绑定的列表; | `` |
| `fail_bind_list` | array | 绑定失败的列表; | `` |
| `total_request_bind_cnt` | number | 请求绑定的数量; | `10` |
| `total_success_bind_cnt` | number | 成功绑定的数量; | `5` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "create_time": "create_time",
    "out_product_id": "out_product_id",
    "outer_product_id": "outer_product_id",
    "product_id": "product_id",
    "sku": [
      {
        "code": "1",
        "out_sku_id": "1",
        "outer_sku_id": "1",
        "sku_id": "1",
        "spec_detail_id1": "1",
        "spec_detail_id2": "1",
        "spec_detail_id3": "1",
        "spec_detail_ids": "[111,222,333]"
      }
    ]
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
