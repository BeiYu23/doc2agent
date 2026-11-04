# 获取人群生产包列表

> sms.listAudienceProduce — 获取人群生产包列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取人群生产包列表 |
| 文档地址 | `/docs/doudian/sms/sms-sms-listAudienceProduce` |
| 接口 ID | `doudian.sms.sms.listAudienceProduce` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/listAudienceProduce` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7787 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_index` | body | number | 是 | 页码，从1开始 | `1` |
| `page_size` | body | number | 是 | 页大小，最大100 | `10` |
| `produce_id` | body | string | 否 | 生产包id | `1231` |
| `audience_id` | body | string | 否 | 人群包id | `23123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/qualityDetail?app_key=your_appkey_here&method=product.qualityDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 总数 | `13` |
| `produce_list` | array | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
