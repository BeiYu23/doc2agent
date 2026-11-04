# 查询商品 SKU

> buyin.productSkus.v2 — 查询商品 SKU

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询商品 SKU |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-productSkus-v2` |
| 接口 ID | `doudian.alliance.buyin.productSkus.v2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/productSkus/v2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/6468 |
| 更新日期 | `2024-06-06` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品ID | `3553361443837581161` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/productSkus/v2?app_key=your_appkey_here&method=buyin.productSkus.v2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `specs` | array | 商品规格信息列表 | `` |
| `pictures` | string | 图片 | `` |
| `skus` | string | sku 信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 商品没有加入精选联盟（sub_code: isv.business-failed:4133） | 商品没有加入精选联盟 |
| `50002` | 业务处理失败 / 亲爱的用户，因服务器升级，商品展示可能异常，带来不便，敬请见谅。（sub_code: isv.business-failed:8193） | 亲爱的用户，因服务器升级，商品展示可能异常，带来不便，敬请见谅。 |
| `50002` | 业务处理失败 / 无效商品ID（sub_code: isv.business-failed:265） | 无效商品ID |
| `50002` | 业务处理失败 / 商品无SKU（sub_code: isv.business-failed:4134） | 商品无SKU |

## 响应示例

成功：

```json
{
  "data": {
    "pictures": {},
    "skus": {},
    "specs": [
      {
        "name": "机身颜色",
        "spec_items": [
          {
            "id": "1712481022018592",
            "name": "粉色"
          }
        ]
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
