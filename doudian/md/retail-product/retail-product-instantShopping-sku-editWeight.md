# 修改sku重量

> instantShopping.sku.editWeight — 修改sku重量

| 元信息 | 值 |
| --- | --- |
| 中文名 | 修改sku重量 |
| 文档地址 | `/docs/doudian/retail-product/retail-product-instantShopping-sku-editWeight` |
| 接口 ID | `doudian.retail-product.instantShopping.sku.editWeight` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1570/7464 |
| 更新日期 | `2025-05-15` |

## 接口说明

- 文档书: 商品管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店id | `206944182` |
| `product_id` | body | mixed | 是 | 子品id | `3751190486992420981` |
| `sku_id` | body | mixed | 是 | 子品skuid | `3480951341198338` |
| `delivery_infos` | body | array | 否 | 配送信息 | `` |
| `  └ info_value` | body | string | 否 | 数字 | `100` |
| `  └ info_unit` | body | string | 否 | 单位 | `g` |
| `  └ info_type` | body | string | 否 | 类型 | `weight` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.sku.editWeight&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `msg` | string | 错误信息 | `“”` |
| `code` | mixed | 错误码 | `0` |

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
    "msg": "“”"
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
