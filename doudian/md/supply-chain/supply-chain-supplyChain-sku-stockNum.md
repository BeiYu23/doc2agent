# 查询sku库存

> supplyChain.sku.stockNum — 查询sku库存

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询sku库存 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-sku-stockNum` |
| 接口 ID | `doudian.supply-chain.supplyChain.sku.stockNum` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2554 |
| 更新日期 | `2025-02-17` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | mixed | 否 | skuid | `1111111` |
| `outer_sku_id` | body | string | 否 | 外部skuid | `111111` |
| `out_warehouse_id` | body | string | 否 | 外部仓编码 | `W11111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.sku.stockNum&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回数据 | `` |

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
        "alloc_qty": "800",
        "alloc_stock_serial_no_list": "[\"123\"]",
        "out_warehouse_id": "W1111111",
        "remain_qty": "200",
        "total_qty": "1000",
        "total_stock_serial_no_list": "[\"123\"]"
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
