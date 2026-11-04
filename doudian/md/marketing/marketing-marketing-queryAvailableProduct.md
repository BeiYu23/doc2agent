# marketing.queryAvailableProduct

> 支持根据特定条件查询营销可用商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.marketing.marketing.queryAvailableProduct` |
| 中文名 | 支持根据特定条件查询营销可用商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/queryAvailableProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7776 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `end_time` | body | number | 是 | 玩法结束时间 | `1755267804` |
| `product_query_condition_option` | body | object | 否 | 商品查询条件选项 | `` |
| `  └ product_str_list` | body | array | 否 | 商品ID列表或者商品名称列表 | `3641483758168855009` |
| `  └ product_number` | body | string | 否 | 货品号，商家内部编号 | `2033HH` |
| `page_size` | body | number | 是 | 页大小。最多支持100。 | `20` |
| `activity_code` | body | string | 是 | 玩法编码。限时抢购：LimitTimeTimeBuy；限量抢购：LimitQuantityTimeBuy；普通降级促销：OrdinaryTimeBuy | `LimitTimeTimeBuy` |
| `start_time` | body | number | 是 | 玩法开始时间 | `1755267804` |
| `page` | body | number | 是 | 页号。 | `1` |
| `common_ctx_info` | body | object | 否 | 通用上下文 | `` |
| `  └ shop_info` | body | object | 否 | 店铺信息 | `` |
| `  └ isv_info` | body | object | 否 | 第三方应用信息 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/updateConsign?app_key=your_appkey_here&method=supplyChain.updateConsign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `query_available_product_res` | object | 可用品结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:510050002） | 联系技术排查 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:510000001） | 调整参数重新请求 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:510050002",
  "sub_msg": "系统异常"
}
```

## 备注
