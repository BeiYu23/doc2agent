# product.getPerformance

> 查询商品指标信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.product.getPerformance` |
| 中文名 | 查询商品指标信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getPerformance` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7351 |
| 更新日期 | `2025-03-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品ID | `3626171943981559436` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getPerformance?app_key=your_appkey_here&method=product.getPerformance&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | string | 商品ID | `3626171943981559436` |
| `has_sold` | boolean | 是否动销 | `true` |
| `has_visited` | boolean | 是否曝光 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / productId不能为空（sub_code: isp.service-error:3000001） | productId不能为空 |
| `20000` | 系统错误 / shopId不能为空（sub_code: isp.service-error:3000002） | shopId不能为空 |
| `20000` | 系统错误 / 商品不存在（sub_code: isp.service-error:3000003） | 商品不存在 |
| `20000` | 系统错误 / 商品参数不合法（sub_code: isp.service-error:3000004） | 商品参数不合法 |

## 响应示例

成功：

```json
{
  "data": {
    "has_sold": "true",
    "has_visited": "true",
    "product_id": "3626171943981559436"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:3000001",
  "sub_msg": "productId不能为空"
}
```

## 备注
