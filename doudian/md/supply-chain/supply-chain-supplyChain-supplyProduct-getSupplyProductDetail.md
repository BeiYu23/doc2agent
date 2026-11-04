# supplyChain.supplyProduct.getSupplyProductDetail

> 获取产品详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.getSupplyProductDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2548 |
| 更新日期 | `2026-08-05` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 是 | 产品id | `2222` |
| `outer_product_id` | body | string | 否 | 外部产品id | `1111` |
| `query_sku_stock` | body | boolean | 否 | 是否查询sku信息，默认false | `false` |
| `query_sku_price` | body | boolean | 否 | 是否查询价格信息，默认false | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProduct.getSupplyProductDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 返回值 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 3200:未查询到分销品，请检查检索条件（sub_code: isv.business-failed:3200） | 3200:未查询到分销品，请检查检索条件 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:3200",
  "sub_msg": "3200:未查询到分销品，请检查检索条件"
}
```

## 备注
