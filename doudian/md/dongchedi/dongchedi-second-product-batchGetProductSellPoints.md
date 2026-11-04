# second.product.batchGetProductSellPoints

> 【二方接口】查询商品卖点信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.product.batchGetProductSellPoints` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/batchGetProductSellPoints` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6940 |
| 更新日期 | `2024-10-17` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `extra` | body | string | 否 | 扩展信息（比如直播间id，key定义见 ProductSellPointExtraKey） | `"1":"1"` |
| `user_id` | body | mixed | 否 | 用户ID，新场景必传，未登录用户请传0 | `1` |
| `params` | body | array | 否 | 参数 | `` |
| `  └ productId` | body | mixed | 否 | 商品ID | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.batchGetProductSellPoints&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sell_points` | string | 参数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "sell_points": {}
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
