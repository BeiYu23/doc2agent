# mini.product.isWanted

> 查询是否收藏

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.mini.product.isWanted` |
| 中文名 | 查询是否收藏 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/product/isWanted` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4229 |
| 更新日期 | `2024-07-08` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品id | `111222` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/erpCargoSinglePush?app_key=your_appkey_here&method=yunc.erpCargoSinglePush&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_wanted` | boolean | 是否想要 | `true` |
| `product_id` | string | 商品id | `11222` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 查询是否收藏失败（sub_code: isv.business-failed:605013002） | 检查参数，重试 |

## 响应示例

成功：

```json
{
  "data": {
    "cargo_code": "X01",
    "erp_sku_id": "1001"
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
  "sub_code": "isv.business-failed:605013002",
  "sub_msg": "查询是否收藏失败"
}
```

## 备注
