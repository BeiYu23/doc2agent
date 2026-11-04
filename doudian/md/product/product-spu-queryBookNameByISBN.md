# spu.queryBookNameByISBN

> 根据ISBN查询书名

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.spu.queryBookNameByISBN` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/spu/queryBookNameByISBN` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2373 |
| 更新日期 | `2026-02-28` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | mixed | 否 | 类目ID | `23362` |
| `isbn` | body | string | 是 | ISBN编号 | `9787555289227` |
| `page_no` | body | mixed | 是 | 当前页数。默认从0开始 | `0` |
| `page_size` | body | mixed | 是 | 页大小。范围1-100 | `10` |
| `channel` | body | mixed | 否 | 获取数据的类目版本。0:门捷列夫类目；1:标准类目 | `1/0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/spu/queryBookNameByISBN?app_key=your_appkey_here&method=spu.queryBookNameByISBN&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 查询到的数据 | `` |
| `total` | mixed | 总数 | `12` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "book_name": "小王子",
        "category_leaf_id": "23362",
        "spu_id": "7130665982338597159"
      }
    ],
    "total": "12"
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
