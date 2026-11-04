# 批量获取库存

> supplyChain.batchGetSupplyStock — 批量获取库存

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量获取库存 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-batchGetSupplyStock` |
| 接口 ID | `doudian.supply-chain.supplyChain.batchGetSupplyStock` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/batchGetSupplyStock` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/7334 |
| 更新日期 | `2025-03-05` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 否 | 货品id | `123` |
| `sku_list` | body | array | 否 | sku库存列表 | `` |
| `  └ sku_id` | body | mixed | 否 | skuid | `123` |
| `  └ outer_sku_id` | body | string | 否 | 外部sku编码 | `123` |
| `  └ out_warehouse_id` | body | string | 否 | 外部仓编码 | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/batchGetSupplyStock?app_key=your_appkey_here&method=supplyChain.batchGetSupplyStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | data | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "sku_id": "123",
        "stock_list": [
          {
            "alloc_qty": "1",
            "alloc_stock_serial_no_list": "[\"123\"]",
            "out_warehouse_id": "123",
            "remain_qty": "1",
            "total_qty": "1",
            "total_stock_serial_no_list": "[\"123\"]"
          }
        ]
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
