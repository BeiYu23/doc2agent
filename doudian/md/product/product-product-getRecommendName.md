# product.getRecommendName

> 根据商品信息推荐商品标题相关信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.getRecommendName` |
| 中文名 | 根据商品信息推荐商品标题相关信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getRecommendName` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2428 |
| 更新日期 | `2024-02-29` |

## 接口说明

- 文档书: 商品API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `scene` | body | array | 是 | 暂时仅开放一种场景：1. product_name_prefix，表示基于 命中的商品类目属性 推荐 商品标题前缀 | `["product_name_prefix"]` |
| `category_leaf_id` | body | mixed | 是 | 商品叶子类目id，请先使用【/product/getProductUpdateRule】接口查询类目id查看recommend_name_rule. satisfy_prefix是否=true | `26150` |
| `first_cid` | body | mixed | 是 | 一级类目id，scene为product_name_prefix时必传，没有时传0 | `20080` |
| `first_cid_name` | body | string | 是 | 一级类目名，scene为product_name_prefix时必传 | `时尚饰品` |
| `second_cid` | body | mixed | 是 | 二级类目id，scene为product_name_prefix时必传，没有时传0 | `20998` |
| `second_cid_name` | body | string | 是 | 二级类目名，scene为product_name_prefix时必传 | `耳饰` |
| `third_cid` | body | mixed | 是 | 三级类目id，scene为product_name_prefix时必传，没有时传0 | `26150` |
| `third_cid_name` | body | string | 是 | 三级类目名，scene为product_name_prefix时必传 | `耳钉` |
| `select_property` | body | string | 是 | 商品类目属性，参考"select_property":{"1687":[{"value":0,"name":"填入品牌名"}],"3320":[{"value":18972,"name":"99新"}]} | `{"1687":[{"value":0,"name":"填入品牌名"}],"3320":[{"value":18972,"name":"99新"}]}` |
| `  └ value` | body | mixed | 是 | 属性id | `27182` |
| `  └ name` | body | string | 是 | 属性名称 | `钛钢` |
| `use_brand_name` | body | boolean | 否 | 是否勾选使用品牌名 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `recommend_name` | array | 商品标题推荐结果，当返回值为空时，使用【/product/getProductUpdateRule】接口查询类目id查看recommend_name_rule.satisfy_prefix是否=true | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:2010001） | 重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2010004） | 检查参数 |
| `40004` | 非法的参数 / 不存在有效的标题推荐类场景（sub_code: isv.parameter-invalid:2010342） | 检查scene参数 |
| `50002` | 业务处理失败 / 110101049:没有品牌使用权限，不能加到标题前缀中（sub_code: isv.business-failed:110101049） | 110101049:没有品牌使用权限，不能加到标题前缀中 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:2010001",
  "sub_msg": "系统错误"
}
```

## 备注
