# 【二方接口】获取SKU属性

> second.product.getSkuAttribute — 【二方接口】获取SKU属性

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【二方接口】获取SKU属性 |
| 文档地址 | `/docs/doudian/dongchedi/dongchedi-second-product-getSkuAttribute` |
| 接口 ID | `doudian.dongchedi.second.product.getSkuAttribute` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/getSkuAttribute` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6948 |
| 更新日期 | `2024-10-17` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `productId` | body | mixed | 否 | 名称: 商品 ID | `1` |
| `shopId` | body | mixed | 否 | 名称: 店铺 ID 要求: 需要和 productId 对应 | `1` |
| `items` | body | array | 否 | items | `` |
| `  └ skuId` | body | mixed | 否 | 名称: SKU ID 列表 要求: 需要和 productId 对应 | `1` |
| `  └ attributeKey` | body | string | 否 | attributeKey | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.getSkuAttribute&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 出参列表数量和入参列表数量始终一致, 如果属性不存在那么 attributeKey 将为 nil, 如果属性值不存在那么 attributeVal 将为 nil | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "items": [
      {
        "attributeKey": "1",
        "attributeVal": "1",
        "skuId": "1",
        "version": "1"
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
