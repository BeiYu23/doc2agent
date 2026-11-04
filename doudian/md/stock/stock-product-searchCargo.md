# 货品检索

> product.searchCargo — 货品检索

| 元信息 | 值 |
| --- | --- |
| 中文名 | 货品检索 |
| 文档地址 | `/docs/doudian/stock/stock-product-searchCargo` |
| 接口 ID | `doudian.stock.product.searchCargo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/searchCargo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/8419 |
| 更新日期 | `2026-07-16` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `id_code_name_list` | body | array | 否 | id code name混合检索 | `["AAA","123"]` |
| `code_list` | body | array | 否 | 货品编码数组 | `["AAA"]` |
| `name_list` | body | array | 否 | 名称数组 | `["货品"]` |
| `cargo_id_list` | body | array | 否 | 货品id数组 | `[123]` |
| `status_list` | body | array | 否 | 货品状态数组 | `[0]` |
| `page` | body | mixed | 否 | 页码 0开始 | `0` |
| `size` | body | mixed | 否 | 分页大小 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/searchCargo?app_key=your_appkey_here&method=product.searchCargo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cargo_list` | array | 检索结果 | `` |
| `total` | mixed | 总数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cargo_list": [
      {
        "cargo_id": "123",
        "code": "ABC",
        "img": "xxx",
        "name": "ABC",
        "status": "0",
        "warehouse_stock": [
          {
            "stock_num": "1",
            "warehouse_code": "ABC",
            "warehouse_id": "123"
          }
        ]
      }
    ],
    "total": "1"
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
