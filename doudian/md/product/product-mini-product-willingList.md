# mini.product.willingList

> 商品收藏列表查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.mini.product.willingList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/product/willingList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4234 |
| 更新日期 | `2023-08-10` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=mini.product.willingList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 查询收藏列表失败，请检查参数重试（sub_code: isv.business-failed:605013003） | 检查参数重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "name": "xxx",
        "pic": "xxx",
        "product_id": "123"
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
  "sub_code": "isv.business-failed:605013003",
  "sub_msg": "查询收藏列表失败，请检查参数重试"
}
```

## 备注
