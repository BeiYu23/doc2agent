# product.getBindBySaleProduct

> 通过前台销售商品查供货商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.product.getBindBySaleProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getBindBySaleProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/8329 |
| 更新日期 | `2026-05-22` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_list` | body | array | 否 | 查询列表 | `` |
| `  └ product_id` | body | mixed | 否 | 商品id | `3820584917637660672` |
| `  └ sku_id` | body | mixed | 否 | skuid | `3659238057270816` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getBindBySaleProduct?app_key=your_appkey_here&method=product.getBindBySaleProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `relation_list` | array | 关系列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:-10007） | 根据具体报错提示调整 |

## 响应示例

成功：

```json
{
  "data": {
    "relation_list": [
      {
        "cargo_id": "3820584917637660672",
        "cargo_sku_id": "3659238057270816",
        "product_id": "3820739174718380209",
        "shop_id": "95078",
        "sku_id": "3659238054343040"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:-10007",
  "sub_msg": "系统错误"
}
```

## 备注
