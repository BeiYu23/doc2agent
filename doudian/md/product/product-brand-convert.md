# brand.convert

> 兼容老品牌id转为新品牌id

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.brand.convert` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/brand/convert` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1500 |
| 更新日期 | `2021-11-26` |

## 接口说明

- 文档书: 商品API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `related_id` | body | number | 是 | 品牌关系id，即/shop/brandList返回的id | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/brand/convert?app_key=your_appkey_here&method=brand.convert&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_id` | number | 品牌id，对应商品发布接口standard_brand_id字段 | `12345` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 品牌授权信息不存在（sub_code: isv.business-failed:2010004） | 品牌授权信息不存在，请检查 |
| `50002` | 业务处理失败 / 查询品牌授权信息失败（sub_code: isv.business-failed:2010001） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "brand_id": "12345"
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
  "sub_code": "isv.business-failed:2010004",
  "sub_msg": "品牌授权信息不存在"
}
```

## 备注
