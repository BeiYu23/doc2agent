# 商品维度订单量诊断

> shop.prodOrderCntDiagnose — 商品维度订单量诊断

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商品维度订单量诊断 |
| 文档地址 | `/docs/doudian/product/product-shop-prodOrderCntDiagnose` |
| 接口 ID | `doudian.product.shop.prodOrderCntDiagnose` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/prodOrderCntDiagnose` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8371 |
| 更新日期 | `2026-07-03` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `entity_list` | body | array | 否 | 实体信息，业务方需要诊断的实体列表，最多1个 | `` |
| `  └ entity_id` | body | string | 否 | 实体id | `123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/prodOrderCntDiagnose?app_key=your_appkey_here&method=shop.prodOrderCntDiagnose&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
        "entity_id": "3457624212251013171",
        "entity_problem_list": [
          {
            "diagnose_result": {
              "diagnose_index_map": {},
              "improve_factors": [
                {
                  "factor_code": "ship_to_arrive_lte_14d_pay_to_arrive_lgt_dur_1d",
                  "factor_name": "商品物流时长"
                }
              ],
              "suggest_list": [
                {
                  "backtest_accuracy": "0.9",
                  "diagnose_suggest": "减少物流时常",
                  "diagnose_target": {
                    "target_name": "商品流量"
                  },
                  "impact_ratio": "9.84%",
                  "impact_value": "76.15%->85.99%",
                  "rule_code": "DiagnoseRule177668223744729170",
                  "rule_detail": "商品物流时长<52.79小时\\n重要属性填写数量>=2个\\n支持运费险\\n关联内容达人数量>=17个",
                  "sample_coverage": "100"
                }
              ],
              "total_impact_ratio": "11.14%"
            },
            "problem_code": "xgboost_order_count",
            "problem_name": "XGBoost 订单量"
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
