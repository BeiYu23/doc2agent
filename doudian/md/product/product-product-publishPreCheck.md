# product.publishPreCheck

> 商品发布前置校验接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.publishPreCheck` |
| 中文名 | 商品发布前置校验 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/publishPreCheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/6503 |
| 更新日期 | `2026-08-21` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `check_types` | body | array | 是 | 校验类型，需要进行哪些校验，可以支持部分校验。 店铺发品门槛校验：shop_publish_product_access，不需要传其他字段；店铺使用类目权限校验：shop_use_category_access，需要传category_id字段；商品标题校验product_title_illegal_check，需要传title、title_prefix、title_suffix 水洗标校验product_wash_tag_pic_check，需要传category_id、category_property_pics | `["shop_publish_product_access","shop_use_category_access","shop_out_product_id_unique"]` |
| `category_id` | body | mixed | 否 | 叶子类目id | `20219` |
| `out_product_id` | body | string | 否 | 外部商品编码，对应商品outer_product_id字段 | `123456678` |
| `title` | body | string | 否 | 完整的标题，需要包含前后缀 | `标题前缀我是个标题标题后缀` |
| `title_prefix` | body | string | 否 | 标题前缀 | `标题前缀` |
| `title_suffix` | body | string | 否 | 标题后缀 | `标题后缀` |
| `category_property_pics` | body | string | 否 | 属性图（水洗标）, 参考格式{"785":{"urls":["https://xxxxxxx"]}} | `` |
| `  └ urls` | body | array | 否 | 属性图url，仅支持传递一张图 | `["https://xxxxxxxxxx"]` |
| `brand_id` | body | mixed | 否 | 品牌id | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/publishPreCheck?app_key=your_appkey_here&method=product.publishPreCheck&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `common_check_results` | array | 校验 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010004:校验类目使用权限需要类目id参数（sub_code: isv.business-failed:2010004） | 2010004:校验类目使用权限需要类目id参数 |
| `50002` | 业务处理失败 / 2010001:系统异常,请重试（sub_code: isv.business-failed:2010001） | 2010001:系统异常,请重试 |
| `50002` | 业务处理失败 / 110210112:商品类目不符合平台规则，请重新选择商品类目（sub_code: isv.business-failed:110210112） | 110210112:商品类目不符合平台规则，请重新选择商品类目 |

## 响应示例

成功：

```json
{
  "data": {
    "common_check_results": [
      {
        "check_result_code": "0",
        "check_result_msg": "success",
        "check_type": "shop_publish_product_access"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2010004",
  "sub_msg": "2010004:校验类目使用权限需要类目id参数"
}
```

## 备注
