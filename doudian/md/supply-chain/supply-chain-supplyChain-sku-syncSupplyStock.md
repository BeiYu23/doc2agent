# 设置库存

> supplyChain.sku.syncSupplyStock — 设置库存

| 元信息 | 值 |
| --- | --- |
| 中文名 | 设置库存 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-sku-syncSupplyStock` |
| 接口 ID | `doudian.supply-chain.supplyChain.sku.syncSupplyStock` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2553 |
| 更新日期 | `2025-02-17` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | mixed | 是 | skuid | `111111111111` |
| `product_id` | body | mixed | 否 | productid | `11111111` |
| `out_warehouse_id` | body | string | 否 | 外部仓库编码 | `w12345` |
| `incremental` | body | boolean | 否 | 是否增量同步，当前供销平台只支持增量同步 | `true` |
| `idempotent_id` | body | string | 否 | 请求幂等键 | `w12345_0_1656262875` |
| `stock_num` | body | mixed | 是 | 库存变更量，负值代表减 | `10` |
| `stock_serial_no_list` | body | array | 否 | 库存实物序列号，如手机即为每个手机的IMEI | `["123"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.sku.syncSupplyStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `released_stock_serial_no_list` | array | 库存调减返回释放的库存实物序列号，如手机即为每个手机的IMEI | `["123"]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "released_stock_serial_no_list": "[\"123\"]"
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
