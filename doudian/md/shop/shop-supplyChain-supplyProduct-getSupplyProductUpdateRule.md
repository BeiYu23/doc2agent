# 获取产品发布模板

> supplyChain.supplyProduct.getSupplyProductUpdateRule — 获取产品发布模板

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取产品发布模板 |
| 文档地址 | `/docs/doudian/shop/shop-supplyChain-supplyProduct-getSupplyProductUpdateRule` |
| 接口 ID | `doudian.shop.supplyChain.supplyProduct.getSupplyProductUpdateRule` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2117 |
| 更新日期 | `2022-06-27` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 是 | 类目id | `20219` |
| `product_id` | body | number | 否 | 品id，编辑的时候需要传被编辑的商品id，发布商品时如果已有产品id也需要传 | `23333` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProduct.getSupplyProductUpdateRule&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_list` | array | 品牌列表 | `` |
| `cate_property_list` | array | 属性规范列表 | `` |
| `quality_list` | array | 资质列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "brand_list": [
      {
        "brand_id": "1",
        "name_cn": "这是个示例",
        "name_en": "xxx"
      }
    ],
    "cate_property_list": [
      {
        "cid": "31918",
        "diy_type": "1",
        "is_required": "0",
        "multi_select_max": "5",
        "options": [
          {
            "name": "ON:THE BODY/安宝笛",
            "sequence": "2",
            "value": "1062254699",
            "value_id": "1"
          }
        ],
        "property_id": "14133",
        "property_name": "材质",
        "property_type": "1",
        "relation_id": "1",
        "sequence": "2",
        "status": "1",
        "type": "text"
      }
    ],
    "quality_list": [
      {
        "is_required": "true",
        "quality_key": "3457058945162709852",
        "quality_name": "质检报告",
        "text_list": "[ \"需为近一年由第三方权威质检机构出具的一份含有CMA或CNAS认证的质检报告。\", \"-检测报告里的商品名称、品牌、生产商名称等信息与商详发布的商品信息需一致\", \"-如报告无品牌名称，需提供含品牌名称、商品名称及生产单位的产品实拍图\", \"-涉及特殊材质的商品，需提供材质（面料）或成品质检报告，质检报告须包含材质成分（纺织品还需包含面料含量)、对应的商品货号或款号或商品名称。特殊材质包含但不限于蚕丝、真丝、羽绒、鸭绒、鹅绒、羊绒、羊毛、牛皮、羊皮、真皮、移膜革、猪皮等（包括皮草类）。\" ]"
      }
    ]
  },
  "err_no": 0,
  "message": "success",
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
