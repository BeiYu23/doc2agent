# product.qualityDetail

> 商品信息质量分查询API

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.qualityDetail` |
| 中文名 | 商品信息质量分查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/qualityDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1830 |
| 更新日期 | `2024-05-24` |

## 接口说明

- 文档书: 商品API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 是 | 商品ID | `3502384918913228300` |
| `quality_score_version` | body | string | 否 | 质量分版本 | `middle_score` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/qualityDetail?app_key=your_appkey_here&method=product.qualityDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `field_problem` | array | 可优化问题项 | `` |
| `product_id` | mixed | 商品ID | `3469673915587121070` |
| `product_name` | string | 商品名字 | `奈克牌大皮鞋` |
| `quality_score` | object | 质量分 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2030001:读取商品失败（sub_code: isv.business-failed:2030001） | 系统繁忙，请重试 |
| `50002` | 业务处理失败 / 2030013:读取商品失败（sub_code: isv.business-failed:2030013） | 系统繁忙，请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "field_problem": [
      {
        "field_key": "product_name",
        "field_name": "标题",
        "problem_key": "501",
        "problem_name": "详情页图片较少",
        "problem_type": "1",
        "suggestion": "商品素材缺少，详情页的图片说明较少。促进商品购买的决策性信息过少，影响购买，建议丰富商品信息，上传不少于5张详情图片，将商品优势展示出来"
      }
    ],
    "product_id": "3469673915587121070",
    "product_name": "奈克牌大皮鞋",
    "quality_score": {
      "level": "lv3",
      "score": "100",
      "version": "middle_score"
    }
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
  "sub_code": "isv.business-failed:2030001",
  "sub_msg": "2030001:读取商品失败"
}
```

## 备注
