# shop.productDiagnose

> 本店商品维度诊断

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.shop.productDiagnose` |
| 中文名 | 本店商品维度诊断 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/productDiagnose` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/8370 |
| 更新日期 | `2026-06-29` |

## 接口说明

- 文档书: 店铺API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `entity_list` | body | array | 否 | 实体信息，业务方需要诊断的实体列表，这里要传商品id | `` |
| `  └ entity_id` | body | string | 否 | 实体id | `123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/productDiagnose?app_key=your_appkey_here&method=shop.productDiagnose&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 实体诊断结果列表 | `` |
| `st` | mixed | 状态码，0: 成功 | `0` |
| `msg` | string | 出错提示消息 | `success` |

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
        "entity_id": "123456",
        "entity_problem_list": [
          {
            "problem_code": "product_resale_diagnose",
            "problem_index_map": {},
            "problem_name": "商品复购影响"
          }
        ],
        "entity_type": "4"
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
