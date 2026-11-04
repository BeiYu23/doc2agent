# productClue.distributableCluelist

> 批量获取可分发在架线索列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.productClue.distributableCluelist` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/productClue/distributableCluelist` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7748 |
| 更新日期 | `2026-03-16` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_size` | body | mixed | 是 | 每页数量 | `50` |
| `current` | body | mixed | 是 | 当前页 | `1` |
| `query` | body | object | 否 | 查询条件 | `` |
| `  └ content_types` | body | array | 否 | 优势体裁类型，仅支持video/live/product_card | `[product_card,video]` |
| `  └ keyword` | body | string | 否 | 关键字 | `古风连衣裙` |
| `  └ profit_ids` | body | array | 否 | 权益ID，或关系 | `[1,2,3]` |
| `  └ price_lowest` | body | mixed | 否 | 最低价-分 | `1200` |
| `  └ sort_type` | body | string | 否 | 排序规则，仅支持pay_amt_desc/pay_amt_rate_desc/demand_supply_rate_desc | `pay_amt_desc` |
| `  └ price_highest` | body | mixed | 否 | 最高价-分 | `2400` |
| `  └ online_time_type` | body | string | 否 | 上新时间类型，仅支持1d/7d/30d | `1d` |
| `  └ brand_ids` | body | array | 否 | 品牌ID | `[1,2]` |
| `  └ category_id` | body | mixed | 否 | 类目ID | `20023` |
| `  └ label_ids` | body | array | 否 | 标签ID，或关系 | `[1,2,3]` |
| `  └ clue_brand_exists` | body | boolean | 否 | 线索是否存在品牌 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/productClue/distributableCluelist?app_key=your_appkey_here&method=productClue.distributableCluelist&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 商机列表信息 | `` |
| `total` | mixed | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 503:分页获取数据超出限制（sub_code: isv.business-failed:503） | 请联系管理员 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "category_id": "4",
        "category_name": "叶子类目",
        "clue_id": "1111",
        "first_cid": "1",
        "first_name": "一级类目",
        "fourth_cid": "4",
        "fourth_name": "四级类目",
        "name": "测试商机",
        "pay_amt_rate": "98.12%",
        "product_pic_url": "https://www.bejson.com/",
        "profit_ids": "[1,3]",
        "search_pv_cnt_range": "1万-5万",
        "second_cid": "2",
        "second_name": "二级类目",
        "third_cid": "3",
        "third_name": "三级类目"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.business-failed:503",
  "sub_msg": "503:分页获取数据超出限制"
}
```

## 备注
