# 获取商品sku面板schema

> mini.product.skuPanelSchema — 获取商品sku面板schema

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取商品sku面板schema |
| 文档地址 | `/docs/doudian/product/product-mini-product-skuPanelSchema` |
| 接口 ID | `doudian.product.mini.product.skuPanelSchema` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/product/skuPanelSchema` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4251 |
| 更新日期 | `2024-08-30` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品id | `123456` |
| `action` | body | mixed | 是 | 1-加购 2-立购 | `1` |
| `param` | body | object | 是 | - | `` |
| `  └ app_id` | body | mixed | 是 | 1128 | `端Id` |
| `  └ app_version` | body | string | 是 | 230600 | `端版本` |
| `  └ device_id` | body | string | 是 | 1111 | `设备id` |
| `  └ device_platform` | body | string | 是 | android、ios | `端平台` |
| `  └ device_type` | body | string | 是 | iphone14 | `设备类型` |
| `  └ channel` | body | string | 是 | test | `渠道` |
| `  └ os_version` | body | string | 是 | 15 | `端系统` |
| `micro_app_id` | body | string | 否 | 小程序appId | `tt56785648asdf` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=mini.product.skuPanelSchema&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `schema` | string | 生成的schema | `sslocal://ec_goods_sku/?xxx=xxx` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 获取schema失败，请重试（sub_code: isv.business-failed:605013004） | 检查参数并重试 |

## 响应示例

成功：

```json
{
  "data": {
    "schema": "sslocal://ec_goods_sku/?xxx=xxx"
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
  "sub_code": "isv.business-failed:605013004",
  "sub_msg": "获取schema失败，请重试"
}
```

## 备注
