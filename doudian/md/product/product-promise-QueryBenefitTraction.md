# 查询店铺维度利益点和库存推荐

> promise.QueryBenefitTraction — 查询店铺维度利益点和库存推荐

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询店铺维度利益点和库存推荐 |
| 文档地址 | `/docs/doudian/product/product-promise-QueryBenefitTraction` |
| 接口 ID | `doudian.product.promise.QueryBenefitTraction` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/promise/QueryBenefitTraction` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8154 |
| 更新日期 | `2026-03-25` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `need_aggregation_benefit_by_shop` | body | boolean | 否 | true=店铺维度聚合利益点 | `true` |
| `need_query_sales_volume_last14_days` | body | boolean | 否 | true=返回近 14 天预售订单量 | `true` |
| `need_stock_increment_suggestion` | body | boolean | 否 | true=返回商品和 SKU 维度库存建议增量 | `true` |
| `need_sort_by_product_recommendation` | body | boolean | 否 | true=按商品库存建议值倒排 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/promise/QueryBenefitTraction?app_key=your_appkey_here&method=promise.QueryBenefitTraction&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `merchant_ship_rate48h` | string | 商家 48h 发货占比 | `0.49` |
| `traction_info_by_fulfillment_mode_map` | string | key为发货模式。 enum FulfillmentMode {     IN_STOCK_PRE_SALE     = 1,  // (新)现货+预售     FULL_PAYMENT_PRE_SALE = 2  // 全款预售     ALL=3 // [(新)现货+预售]+[全款预售] } | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `60000` | 触发限流，请稍后重试 / 下游强依赖全部限流失败（sub_code: isp.traffic-limited:1001001） | 请稍等重试 |
| `20001` | 内部服务超时 / 下游强依赖全部超时失败（sub_code: isp.service-timeout-error:1001002） | 请稍等重试 |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:1001003） | 请检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "merchant_ship_rate48h": "0.49",
    "traction_info_by_fulfillment_mode_map": {}
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
  "code": 60000,
  "msg": "触发限流，请稍后重试",
  "sub_code": "isp.traffic-limited:1001001",
  "sub_msg": "下游强依赖全部限流失败"
}
```

## 备注
