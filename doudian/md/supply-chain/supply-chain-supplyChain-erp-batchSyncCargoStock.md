# erp货品库存同步

> supplyChain.erp.batchSyncCargoStock — erp货品库存同步

| 元信息 | 值 |
| --- | --- |
| 中文名 | erp货品库存同步 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-erp-batchSyncCargoStock` |
| 接口 ID | `doudian.supply-chain.supplyChain.erp.batchSyncCargoStock` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/8109 |
| 更新日期 | `2026-03-06` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cargo_stock_list` | body | array | 是 | 待同步的库存领域对象 | `` |
| `  └ product_id` | body | string | 是 | 平台商品id，来源：抖音商品ID | `3802423036444016000` |
| `  └ erp_sku_id` | body | string | 是 | ERPSKuID， | `3802423036444016000` |
| `  └ transfer_quantity` | body | mixed | 否 | 调拨在途数 | `100` |
| `  └ purchase_quantity` | body | mixed | 否 | 采购在途数 | `100` |
| `  └ stock_quantity` | body | mixed | 否 | 在库库存数， | `100` |
| `  └ erp_spu_id` | body | string | 是 | ERP货品ID， | `7702423036444016000` |
| `  └ cargo_owner_id` | body | string | 是 | erp货主id | `1003434a` |
| `  └ platform_shop_id` | body | mixed | 是 | 平台店铺id | `1224343` |
| `  └ sku_id` | body | string | 是 | 平台skuId，来源：抖音skuId | `3802423036444016000` |
| `  └ order_pending_quantity` | body | mixed | 否 | 待出库订单数 | `100` |
| `  └ sales_return_quantity` | body | mixed | 否 | 销退在途数 | `100` |
| `sync_time` | body | mixed | 否 | 同步时间 | `1770781980` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.erp.batchSyncCargoStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | code | `0` |
| `msg` | string | msg | `success` |
| `failed_list` | array | 失败列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "failed_list": [
      {
        "error_msg": "\"权限缺失\"",
        "product_id": "3802423036444016000",
        "sku_id": "3802423036444016000"
      }
    ],
    "msg": "success"
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
