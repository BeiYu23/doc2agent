# instantShopping.sku.batchEditPrice

> 批量修改SKU价格

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-product.instantShopping.sku.batchEditPrice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1570/7159 |
| 更新日期 | `2025-01-14` |

## 接口说明

- 文档书: 商品管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_list` | body | array | 否 | sku列表，最多50个 | `` |
| `  └ price` | body | mixed | 是 | 售价 (单位 分) | `100` |
| `  └ code` | body | string | 否 | sku编码 | `123123` |
| `  └ sku_id` | body | mixed | 否 | skuid | `45678945678` |
| `  └ out_sku_id` | body | mixed | 否 | 外部skuid | `45678945678` |
| `  └ product_id` | body | mixed | 否 | 商品id | `78945678123132` |
| `  └ out_product_id` | body | mixed | 否 | 外部商品id | `78945678123132` |
| `  └ store_id` | body | mixed | 否 | 即时零售连锁版，通过传入主品id+门店id对该门店下的子品进行操作，即时零售单店版，无需使用 | `145633432` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.sku.batchEditPrice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | array | sku更新结果明细 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "base_resp": {
          "extra": {},
          "status_code": "0",
          "status_message": "sucess"
        },
        "code": "123123",
        "out_product_id": "78945678123132",
        "out_sku_id": "45678945678",
        "outer_product_id": "78945678123132",
        "price": "100",
        "product_id": "78945678123132",
        "sku_id": "45678945678",
        "store_id": "145633432"
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
