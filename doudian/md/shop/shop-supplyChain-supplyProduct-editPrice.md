# supplyChain.supplyProduct.editPrice

> 编辑价格

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.supplyChain.supplyProduct.editPrice` |
| 中文名 | 编辑价格 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2127 |
| 更新日期 | `2022-06-28` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 否 | 产品id | `11111111111111` |
| `sku_id` | body | number | 是 | skuId | `11111111111111` |
| `supply_price` | body | number | 否 | 供货价（单位分） | `10000` |
| `spec_price_list` | body | array | 否 | 特定供货价 | `` |
| `  └ distributor_id_list` | body | array | 是 | 分销商列表 | `[111111111111]` |
| `  └ supply_price` | body | number | 是 | 供货价（单位分） | `10000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProduct.editPrice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "err_no": 0,
  "message": "success",
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
