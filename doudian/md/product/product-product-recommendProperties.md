# product.recommendProperties

> 商品属性推荐

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.recommendProperties` |
| 中文名 | 商品属性推荐 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/recommendProperties` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/6866 |
| 更新日期 | `2024-11-28` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 是 | 叶子类目ID | `20172` |
| `material_ids` | body | array | 否 | 素材ID列表，用于属性预测。material_ids与img_urls选传其中一个即可。 | `["72986162310573755150419"]` |
| `img_urls` | body | array | 否 | 图片URL列表，用于属性预测。material_ids与img_urls选传其中一个即可。 | `["https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_GhxlaZ_72986162310573755150419_6fcc92a698215567a8963cb1861e1945_sx_818278_www2143-2143"]` |
| `name` | body | string | 否 | 商品标题 | `商品标题` |
| `product_format` | body | string | 否 | 商家自填属性；传入可以触发对自填属性值的判准 | `` |
| `  └ value` | body | mixed | 否 | 属性值id | `1024` |
| `  └ name` | body | string | 否 | 属性值名称 | `短款` |
| `  └ diy_type` | body | mixed | 否 | 是否为商家自定义属性值，1为是，0为不是 | `0` |
| `  └ measure_info` | body | object | 否 | 度量衡信息，对本接口暂时不需要传 | `` |
| `    └ template_id` | body | mixed | 否 | 度量衡模板id | `1` |
| `    └ values` | body | array | 否 | 度量衡内容 | `` |
| `      └ extra` | body | string | 否 | 自定义度量衡扩展信息 | `{"":""}` |
| `      └ module_id` | body | mixed | 否 | 模块id | `1` |
| `      └ value` | body | string | 否 | 值内容 | `值内容` |
| `      └ unit_id` | body | mixed | 否 | 度量衡单位id | `1` |
| `      └ unit_name` | body | string | 否 | 度量衡单位名称 | `度量衡单位名称` |
| `      └ prefix` | body | string | 否 | 前缀 | `前缀` |
| `      └ suffix` | body | string | 否 | 后缀 | `后缀` |
| `      └ value_required` | body | boolean | 否 | 是否必填 | `false` |
| `    └ extra` | body | string | 否 | 自定义度量衡扩展信息 | `{"":""}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/recommendProperties?app_key=your_appkey_here&method=product.recommendProperties&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `properties` | array | 推荐的属性列表 | `` |
| `check_result` | string | 属性判准结果；如果存在判准结果，且is_right为false，可以在properties找到对应建议结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010004:素材ID和图片URL至少要传一个（sub_code: isv.business-failed:2010004） | 2010004:素材ID和图片URL至少要传一个 |
| `50002` | 业务处理失败 / 2010001:图片预测类目属性异常（sub_code: isv.business-failed:2010001） | 2010001:图片预测类目属性异常 |

## 响应示例

成功：

```json
{
  "data": {
    "check_result": {},
    "properties": [
      {
        "property_id": "241",
        "property_name": "厚度",
        "property_values": [
          {
            "value_id": "195685",
            "value_name": "厚款"
          }
        ],
        "recommend_source": "SimilarProductRecommend"
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
  "sub_msg": "2010004:素材ID和图片URL至少要传一个"
}
```

## 备注
