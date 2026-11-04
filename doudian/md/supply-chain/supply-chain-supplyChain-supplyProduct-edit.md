# supplyChain.supplyProduct.edit

> 编辑产品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.edit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/supplyProduct/edit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2552 |
| 更新日期 | `2023-04-12` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 是 | 产品id | `3506108675121111111` |
| `category_leaf_id` | body | number | 是 | 叶子类目ID通过getSupplyProductUpdateRule | `20000` |
| `name` | body | string | 是 | 商品名称，最多60个字符(30个汉字)，不能含emoj表情 | `xxx补水液` |
| `recommend_remark` | body | string | 否 | 商家推荐语，不能含emoj表情商品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过1M 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `这个商品很好啊` |
| `pic` | body | string | 是 | 产品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过1M 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url1\|img_url2\|img_url3` |
| `description` | body | string | 是 | 商品描述，目前只支持图片。多张图片用 \"\|\" 分开。不能用其他网站的文本粘贴，这样会出现css样式不兼容。 | `img_url1\|img_url2\|img_url3` |
| `weight` | body | string | 否 | 重量 | `1000` |
| `weight_unit` | body | number | 否 | 重量单位，0-kg, 1-g | `1` |
| `remark` | body | string | 否 | 商家可见备注 | `备注` |
| `quality_list` | body | array | 否 | 资质列表 | `` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_attachments` | body | array | 是 | 资质 | `` |
| `    └ media_type` | body | number | 是 | 1-图片，2-pdf | `1` |
| `    └ url` | body | string | 是 | 凭证url | `\"http://www.byted***.com/YYYY\"` |
| `spec_name` | body | string | 是 | 规格名为各级规格名用 \"-\" 分割 | `颜色-尺码` |
| `specs` | body | string | 是 | 通用规格，能被同类商品通用。多规格用^分隔，规格与规格值用\|分隔，多个规格值用,分隔。 | `颜色\|红色,黑色^尺码\|S,M` |
| `spec_prices` | body | string | 是 | sku详情，只支持全量编辑, 否则会视为删除,  对于非新增的sku,不支持同时编辑价格或库存, 编辑已有sku注意传递内外部id, 供销平台的id是数字 | `[{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"sku_id\":33333333333333,"outer_sku_id":"00000000000"},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"sku_id\":222222222222,"outer_sku_id":"11111111111"},{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"sku_id\":111111111111,"outer_sku_id":"3333333333"},{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"sku_id\":222222222222,"outer_sku_id":"44444444444"}]` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `product_format_new` | body | string | 是 | 类目属性 | `类目属性` |
| `spu_id` | body | number | 否 | spu_id | `14567` |
| `extends` | body | string | 否 | 扩展信息 | `{}` |
| `outer_product_id` | body | string | 否 | 外部product id | `11111111111111` |
| `standard_brand_id` | body | number | 否 | 品牌id，通过/supplyProduct/getSupplyProductUpdateRule获取，无品牌id则传596120136 | `111` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图url | `http://aaaa` |
| `long_pic_url` | body | string | 否 | 3:4长图url | `http://aaaa` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/supplyProduct/edit?app_key=your_appkey_here&method=supplyChain.supplyProduct.edit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | number | 供应链产品id | `7147950556525380000` |
| `outer_product_id` | string | 外部产品编码 | `232334` |
| `sku_list` | array | sku列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 编辑分销品错误（sub_code: isv.business-failed:3207） | 编辑分销品错误 |
| `50002` | 业务处理失败 / 分销品供货价不能是0（sub_code: isv.business-failed:3206） | 分销品供货价不能是0 |

## 响应示例

成功：

```json
{
  "data": {
    "outer_product_id": "232334",
    "product_id": "7147950556525380000",
    "sku_list": [
      {
        "outer_sku_id": "111eee2222",
        "sku_id": "7147944438030516000"
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
  "sub_code": "isv.business-failed:3207",
  "sub_msg": "编辑分销品错误"
}
```

## 备注
