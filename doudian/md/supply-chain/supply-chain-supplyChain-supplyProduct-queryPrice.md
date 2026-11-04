# 查询价格

> supplyChain.supplyProduct.queryPrice — 查询价格

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询价格 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-supplyProduct-queryPrice` |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.queryPrice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2559 |
| 更新日期 | `2022-09-28` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | number | 否 | skuid | `11111` |
| `product_id` | body | number | 否 | productid | `1111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProduct.queryPrice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回值 | `` |

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
        "sku_id": "1111",
        "spec_price_list": [
          {
            "distributor_id_list": "1111",
            "supply_price": "111111"
          }
        ],
        "supply_price": "1111"
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
