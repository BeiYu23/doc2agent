# mini.product.wantProduct

> 商品收藏

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.mini.product.wantProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/product/wantProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4228 |
| 更新日期 | `2024-07-08` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品id | `111222` |
| `action` | body | mixed | 是 | 1-关注 2-取消关注 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=mini.product.wantProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `text` | string | 可在xxx中查看的文案 | `xxx` |
| `url` | string | 点击跳转链接 | `xxx` |
| `is_first` | boolean | 是否首次使用收藏功能 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 商品收藏失败，请检查参数重试（sub_code: isv.business-failed:605013001） | 检查参数，重试 |
| `50002` | 业务处理失败 / 10010:参数异常（sub_code: isv.business-failed:10010） | 检查参数，重试 |

## 响应示例

成功：

```json
{
  "data": {
    "is_first": "true",
    "text": "xxx",
    "url": "xxx"
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
  "sub_code": "isv.business-failed:605013001",
  "sub_msg": "商品收藏失败，请检查参数重试"
}
```

## 备注
