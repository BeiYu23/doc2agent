# 店铺维度诊断

> shop.shopDiagnosis — 店铺维度诊断

| 元信息 | 值 |
| --- | --- |
| 中文名 | 店铺维度诊断 |
| 文档地址 | `/docs/doudian/product/product-shop-shopDiagnosis` |
| 接口 ID | `doudian.product.shop.shopDiagnosis` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/shopDiagnosis` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8369 |
| 更新日期 | `2026-06-25` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/shopDiagnosis?app_key=your_appkey_here&method=shop.shopDiagnosis&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `st` | mixed | 状态码，0: 成功 | `0` |
| `msg` | string | 出错提示消息 | `success` |
| `data` | array | 实体诊断结果列表 | `` |

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
        "action_map": {},
        "entity_id": "shopID",
        "entity_problem_list": [
          {
            "func_code": "xxx",
            "problem_code": "ship_alarm",
            "problem_index_map": {},
            "problem_name": "预警问题"
          }
        ],
        "entity_type": "1"
      }
    ],
    "msg": "success",
    "st": "0"
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
