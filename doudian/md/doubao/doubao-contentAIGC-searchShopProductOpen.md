# contentAIGC.searchShopProductOpen

> 查询店铺商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.doubao.contentAIGC.searchShopProductOpen` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/contentAIGC/searchShopProductOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1627/8670 |
| 更新日期 | `2026-10-19` |

## 接口说明

- 文档书: 豆包工作（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_name` | body | string | 否 | 商品名称或名称片段，可选；仅搜索当前授权店铺。 | `T恤` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/contentAIGC/searchShopProductOpen?app_key=your_appkey_here&method=contentAIGC.searchShopProductOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `products` | array | 名称模糊匹配结果，成功时必返，最多 4 条；没有匹配商品返回空列表。 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务暂时不可用，请稍后重试（sub_code: isp.service-error:1000000） | 请稍后重试；若持续失败，请联系技术支持并提供 LogID。 |
| `40004` | 非法的参数 / 请求参数错误（sub_code: isv.parameter-invalid:1000001） | 请检查参数类型及取值后重试。 |
| `50002` | 业务处理失败 / 当前子账号没有短视频运营权限（sub_code: isv.business-failed:60408003） | 请联系主账号授予短视频运营权限。 |
| `20000` | 系统错误 / 账号权限查询失败，请稍后重试（sub_code: isp.service-error:60488128） | 请稍后重试；若持续失败，请联系技术支持并提供 LogID。 |

## 响应示例

成功：

```json
{
  "data": {
    "products": [
      {
        "product_id": "3841532282984857600",
        "product_name": "纯棉短袖T恤"
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
  "sub_code": "isp.service-error:1000000",
  "sub_msg": "服务暂时不可用，请稍后重试"
}
```

## 备注
