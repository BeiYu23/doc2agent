# 获取门店绑定的限售模版

> shop.getStoreSaleLimit — 获取门店绑定的限售模版

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取门店绑定的限售模版 |
| 文档地址 | `/docs/doudian/shop/shop-shop-getStoreSaleLimit` |
| 接口 ID | `doudian.shop.shop.getStoreSaleLimit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/getStoreSaleLimit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2379 |
| 更新日期 | `2024-02-26` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/getStoreSaleLimit?app_key=your_appkey_here&method=shop.getStoreSaleLimit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_sale_limits` | array | 门店关联的限售模版 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "store_sale_limits": [
      {
        "sale_limit_id": "123",
        "store_id": "123"
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
