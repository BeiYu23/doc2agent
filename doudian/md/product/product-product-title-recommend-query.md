# product.title.recommend.query

> 商品标题优化工具

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.title.recommend.query` |
| 中文名 | 商品标题优化工具 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/title/recommend/query` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2163 |
| 更新日期 | `2022-07-12` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `merchant_id` | body | string | 是 | 服务商 ID | `3914684281657388` |
| `title` | body | string | 否 | 标题（仅参考） | `夏季连衣裙` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=product.title.recommend.query&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `recommend_query_list` | array | 推荐词列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "recommend_query_list": [
      {
        "date": "2022-07-12",
        "leaf_category_id": "1123",
        "query": "夏季连衣裙",
        "search_host_degree": "1"
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
