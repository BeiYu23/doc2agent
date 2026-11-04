# 商品维度查询利益点和库存建议

> promise.QueryBenefitTractionByProductId — 商品维度查询利益点和库存建议

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商品维度查询利益点和库存建议 |
| 文档地址 | `/docs/doudian/product/product-promise-QueryBenefitTractionByProductId` |
| 接口 ID | `doudian.product.promise.QueryBenefitTractionByProductId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/promise/QueryBenefitTractionByProductId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8153 |
| 更新日期 | `2026-03-23` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 是 | 商品 ID | `10021410013` |
| `need_stock_increment_suggestion` | body | boolean | 否 | true=返回商品和 SKU 维度库存建议增量 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/promise/QueryBenefitTractionByProductId?app_key=your_appkey_here&method=promise.QueryBenefitTractionByProductId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `traction_info_by_fulfillment_mode_map` | string | 商品维度利益点 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20001` | 内部服务超时 / 流程强依赖下游全部超时（sub_code: isp.service-timeout-error:1001001） | 请稍后重试 |
| `60000` | 触发限流，请稍后重试 / 流程强依赖下游全部限流（sub_code: isp.traffic-limited:1001002） | 请稍后重试 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:1001003） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
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
  "code": 20001,
  "msg": "内部服务超时",
  "sub_code": "isp.service-timeout-error:1001001",
  "sub_msg": "流程强依赖下游全部超时"
}
```

## 备注
