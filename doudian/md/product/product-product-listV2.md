# product.listV2

> 使用场景：批量查询商家抖店商品信息
1、支持使用商品状态，商品类型、商品创建时间和更新时间筛选商品
2、最大支持1次查询1万条，如返回商品数据大于1万条，请增加筛选条件。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.listV2` |
| 中文名 | 批量查询商家抖店商品信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/listV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/633 |
| 更新日期 | `2026-01-21` |

## 接口说明

- 文档书: 商品API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `status` | body | number | 否 | 商品在店铺中状态: 0-在线；1-下线；2-删除；详见商品状态机：https://op.jinritemai.com/docs/question-docs/92/2070 | `0` |
| `check_status` | body | number | 否 | 商品审核状态: 1-未提交；2-待审核；3-审核通过；4-审核未通过；5-封禁；7-审核通过待上架；详见商品状态机：https://op.jinritemai.com/docs/question-docs/92/2070 | `3` |
| `product_type` | body | number | 否 | 商品类型；0-普通；1-新客商品；3-虚拟；6-玉石闪购；7-云闪购 ；127-其他类型； | `0` |
| `start_time` | body | number | 否 | 商品创建开始时间，unix时间戳，单位：秒； | `1619161933` |
| `end_time` | body | number | 否 | 商品创建结束时间，unix时间戳，单位：秒； | `1619162000` |
| `update_start_time` | body | number | 否 | 商品更新开始时间，unix时间戳，单位：秒；注意：查询范围是update_start_time和update_end_time之间的数据，不包含入参时间。 | `1619161933` |
| `update_end_time` | body | number | 否 | 商品更新结束时间，unix时间戳，单位：秒；注意：查询范围是update_start_time和update_end_time之间的数据，不包含入参时间。 | `1619161933` |
| `page` | body | number | 是 | 页码，从1开始，最大为100；page* size最大不能超过1万条 | `1` |
| `size` | body | number | 是 | 页数，填写范围1~100；page* size最大不能超过1万条 | `10` |
| `store_id` | body | number | 否 | 小时达商家使用的门店id，即时零售单店版，无需使用 | `123456` |
| `name` | body | string | 否 | 商品标题，支持模糊匹配 | `标题` |
| `product_id` | body | array | 否 | 商品id，最大支持传入100个； | `3600137140018749665` |
| `use_cursor` | body | boolean | 否 | 是否使用游标，true 使用，false 不使用；使用游标能遍历全量商品，不会受到只能查询到10000个数据的影响。 特别说明：使用游标查询时，page字段失效，只会查询当前游标后面size条数据；根据获取查询数据为空来判断本次遍历结束；查询过程中数据发生变更，可能重复、遗漏数据；需要保证每次查询的筛选条件一致。 | `true` |
| `cursor_id` | body | string | 否 | 游标id，结合use_cursor使用（use_cursor=true）;首次查询时不需要传值，每次查询结果会返回cursor_id，下一次查询时复制给该字段。当查询返回数据为空时，结束遍历。 | `WzE2ODI1Nzc4MjksMTc2NDMxMDczMDU3MDg0M10=` |
| `can_combine_product` | body | boolean | 否 | 能否参加搭配 | `true` |
| `lookup_option` | body | object | 否 | 查询option | `` |
| `  └ need_name_affix` | body | boolean | 否 | 是否需要获取标题前后缀 | `true` |
| `  └ need_title_limit` | body | boolean | 否 | 是否需要获取商品标题长度限制规则 | `true` |
| `need_rectification_info` | body | boolean | 否 | 是否需要自动整改信息 | `false` |
| `query_options` | body | object | 否 | 查询定制参数 | `` |
| `  └ exist_category_misplaced` | body | boolean | 否 | 只查询类目错放的商品 | `false` |
| `  └ exist_audit_reject_suggest` | body | boolean | 否 | 只查询有驳回建议的商品 | `false` |
| `  └ need_audit_reject_suggest` | body | boolean | 否 | 需要返回审核驳回建议信息 | `false` |
| `need_check_out` | body | boolean | 否 | 是否需要核销 | `false` |
| `sku_codes` | body | array | 否 | sku商家编码，最大支持传入50个 | `aaabbcc` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 商品数据 | `` |
| `total` | number | 本次查询返回的商品总数 | `10000` |
| `page` | number | 当前页码 | `10` |
| `size` | number | 页数（每页数量） | `100` |
| `cursor_id` | string | 使用游标时，每次查询会返回该值，作为下次查询的入参使用。 | `WzE2ODI1Nzc4MjksMTc2NDMxMDczMDU3MDg0M10=` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 页数从1开始（sub_code: isv.parameter-invalid:2010004） | 请检查必传参数是否填写 |
| `20000` | 系统错误 / 判断库存版本失败（sub_code: isp.service-error:2010013） | 灰度时使用，现应无此报错 |
| `20000` | 系统错误 / 查询库存失败（sub_code: isp.service-error:2010001） | 请重试 |
| `20000` | 系统错误 / 读取商品失败（sub_code: isp.service-error:20053） | 请重试 |
| `50002` | 业务处理失败 / 获取类目信息失败（sub_code: isv.business-failed:2010201） | 请重试 |
| `50002` | 业务处理失败 / 触发商品操作限流（sub_code: isv.business-failed:2010401） | 请重试 |
| `50002` | 业务处理失败 / 2010203:获取商品信息失败（sub_code: isv.business-failed:2010203） | 请重试 |

## 响应示例

成功：

```json
{
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2010004",
  "sub_msg": "页数从1开始"
}
```

## 备注
