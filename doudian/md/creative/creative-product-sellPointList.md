# product.sellPointList

> 查询商品卖点列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.creative.product.sellPointList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/sellPointList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/5979 |
| 更新日期 | `2023-12-25` |

## 接口说明

- 文档书: 创意管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 是 | 商品id | `3655859374502583355` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/sellPointList?app_key=your_appkey_here&method=product.sellPointList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_sell_point_list` | array | 商品卖点列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "product_sell_point_list": [
      {
        "content": "创新设计",
        "sell_point_category": "趋势话题",
        "sell_point_category_id": "18",
        "sell_point_id": "1068"
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
