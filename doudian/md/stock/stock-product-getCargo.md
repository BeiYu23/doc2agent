# product.getCargo

> 查询货品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.product.getCargo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getCargo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/8418 |
| 更新日期 | `2026-07-16` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cargo_id` | body | mixed | 是 | 货品ID | `123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getCargo?app_key=your_appkey_here&method=product.getCargo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `img` | string | 货品图片 | `xxx` |
| `status` | mixed | 0-生效 1-删除 | `0` |
| `warehouse_stock` | array | 仓库存 | `` |
| `cargo_id` | mixed | 货品ID | `123456` |
| `shop_id` | mixed | 店铺ID | `123456` |
| `code` | string | 货品编码 | `ABC` |
| `name` | string | 货品名称 | `货品AAA` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cargo_id": "123456",
    "code": "ABC",
    "img": "xxx",
    "name": "货品AAA",
    "shop_id": "123456",
    "status": "0",
    "warehouse_stock": [
      {
        "stock_num": "123",
        "warehouse_code": "ABC",
        "warehouse_id": "123"
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
