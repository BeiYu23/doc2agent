# 删除商品上的主图视频

> product.delProductMainPicVideo — 删除商品上的主图视频

| 元信息 | 值 |
| --- | --- |
| 中文名 | 删除商品上的主图视频 |
| 文档地址 | `/docs/doudian/product/product-product-delProductMainPicVideo` |
| 接口 ID | `doudian.product.product.delProductMainPicVideo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/delProductMainPicVideo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7049 |
| 更新日期 | `2024-11-19` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 是 | 商品id | `3718561388407423310` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/delProductMainPicVideo?app_key=your_appkey_here&method=product.delProductMainPicVideo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | mixed | 删除的素材id | `111` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "material_id": "111"
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
