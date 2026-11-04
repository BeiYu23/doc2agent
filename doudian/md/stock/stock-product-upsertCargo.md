# 货品创建、编辑

> product.upsertCargo — 货品创建、编辑

| 元信息 | 值 |
| --- | --- |
| 中文名 | 货品创建、编辑 |
| 文档地址 | `/docs/doudian/stock/stock-product-upsertCargo` |
| 接口 ID | `doudian.stock.product.upsertCargo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/upsertCargo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/8416 |
| 更新日期 | `2026-07-16` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 否 | 货品名称 | `测试货品` |
| `img` | body | string | 否 | 图片url，需要提前在素材中心上传 | `xxx` |
| `cargo_id` | body | mixed | 否 | 货品ID，如果不为0，说明是update | `123456` |
| `code` | body | string | 否 | 货品外部编码 | `ABC` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/upsertCargo?app_key=your_appkey_here&method=product.upsertCargo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cargo_id` | mixed | 货品ID | `123456` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cargo_id": "123456"
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
