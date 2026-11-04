# 批量查询商品搜索优化项

> compass.batchSearchProductDiagnosis — 批量查询商品搜索优化项

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量查询商品搜索优化项 |
| 文档地址 | `/docs/doudian/product/product-compass-batchSearchProductDiagnosis` |
| 接口 ID | `doudian.product.compass.batchSearchProductDiagnosis` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/compass/batchSearchProductDiagnosis` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7947 |
| 更新日期 | `2025-12-19` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id_list` | body | array | 是 | 商品列表 单次最多传20个 | `[1,2,3]` |
| `factor_list` | body | array | 否 | 只看指定优化项，不传则返回所有可优化项 | `1：主图视频   2：34主图   3：报名活动（报名大促、超值购、秒杀）   4：设置运费险   5：信息质量不达标   6：详实评价   7：价格   8：销量   9：上架   10：库存` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/compass/batchSearchProductDiagnosis?app_key=your_appkey_here&method=compass.batchSearchProductDiagnosis&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_diagnosis_result` | array | 诊断结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "product_diagnosis_result": [
      {
        "diagnosis_list": [
          {
            "diagnosis_item": "sale_001",
            "diagnosis_item_text": "待优化项描述",
            "improvement_advices": [
              {
                "advice": "优化信息质量分",
                "product_factor_rise": "0.24823810710678254"
              }
            ]
          }
        ],
        "max_estimate_promote_rate": "0.2768340470954546",
        "product_id": "1"
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
