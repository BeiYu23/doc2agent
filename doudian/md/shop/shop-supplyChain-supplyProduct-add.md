# supplyChain.supplyProduct.add

> 创建产品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.supplyChain.supplyProduct.add` |
| 中文名 | 创建产品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/supplyProduct/add` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2128 |
| 更新日期 | `2022-06-28` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_product_id` | body | string | 否 | 推荐使用，外部商家编码，支持字符串 | `232334` |
| `category_leaf_id` | body | number | 是 | 叶子类目ID通过/supplier/getSupplierCategory接口获取 | `20000` |
| `name` | body | string | 是 | 商品名称，最多60个字符(30个汉字)，不能含emoj表情 | `xxx补水液` |
| `recommend_remark` | body | string | 否 | 商家推荐语，不能含emoj表情 | `这个产品很好啊` |
| `pic` | body | string | 是 | 商品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过1M。 | `img_url1\|img_url2\|img_url3` |
| `description` | body | string | 是 | 商品描述，目前只支持图片。多张图片用 \"\|\" 分开。不能用其他网站的文本粘贴，这样会出现css样式不兼容。 | `img_url1\|img_url2\|img_url3` |
| `assoc_ids` | body | string | 否 | 同供应商产品推荐：为空表示使用系统推荐；多个product_id使用“\|”分开 | `1\|2\|3` |
| `freight_id` | body | number | 是 | 运费模板id，预留字段。供销平台暂不支持 | `123` |
| `weight` | body | string | 是 | 重量 | `1000` |
| `weight_unit` | body | number | 是 | 重量单位，0-kg, 1-g | `1` |
| `remark` | body | string | 否 | 预留字段，供应商可见备注 | `备注` |
| `out_product_id` | body | number | 否 | 外部product_id | `123` |
| `quality_list` | body | array | 否 | 资质，可通过/suppyProduct/GetSupplyProductUpdateRule获取 | `` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_attachments` | body | array | 是 | 资质 | `` |
| `    └ media_type` | body | number | 是 | 1-图片，2-pdf | `1` |
| `    └ url` | body | string | 是 | 凭证url | `\"http://www.byted***.com/YYYY\"` |
| `spec_name` | body | string | 否 | 如果不填，则规格名为各级规格名用 \"-\" 自动生成 | `颜色-尺码` |
| `specs` | body | string | 是 | 通用规格，能被同类产品通用。多规格用^分隔，规格与规格值用\|分隔，多个规格值用,分隔。 | `颜色\|红色,黑色^尺码\|S,M` |
| `spec_prices` | body | string | 是 | sku详情，数量应该等于规格1规格2规格3，sku数量和规格组合数必须一致 sku不可售时，库存可设置为0。 | `[{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":11,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\"},{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":22,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\"},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":44,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\"},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":55,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\"}]` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `product_format_new` | body | string | 否 | 属性，通过/supplyProduct/getSupplyProductUpdateRule获取 格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]} name的类型是string，value和diy_type的类型是number | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}]}` |
| `spu_id` | body | number | 否 | spu_id | `14567` |
| `extra` | body | string | 否 | extra | `略` |
| `standard_brand_id` | body | number | 否 | 品牌id，通过/supplyProduct/getSupplyProductUpdateRule获取，无品牌id则传596120136 | `111` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图url | `http://aaaa` |
| `long_pic_url` | body | string | 否 | 3:4长图url | `http://aaaa` |
| `material_video_id` | body | string | 否 | 预留字段，主图视频。暂不支持 | `vaaaa` |
| `support_distributor_list` | body | array | 否 | 预留字段，分销商id列表。产品只特定供应商可发起合作 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/supplyProduct/add?app_key=your_appkey_here&method=supplyChain.supplyProduct.add&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | number | product_id | `11111` |
| `out_product_id` | number | out_product_id | `aaaaa` |
| `outer_product_id` | string | outer_product_id | `1111` |
| `create_time` | string | create_time | `2022-06-24 01:00:00` |
| `sku` | array | sku列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 商品创建失败: 系统错误（sub_code: isp.service-error:20000） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "create_time": "2022-06-24 01:00:00",
    "out_product_id": "aaaaa",
    "outer_product_id": "1111",
    "product_id": "11111",
    "sku": [
      {
        "code": "1",
        "out_sku_id": "1",
        "sku_id": "1",
        "spec_detail_id1": "1",
        "spec_detail_id2": "1",
        "spec_detail_id3": "1"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:20000",
  "sub_msg": "商品创建失败: 系统错误"
}
```

## 备注
