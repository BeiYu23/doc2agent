# supplyChain.supplyProduct.add

> 创建产品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.add` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/supplyProduct/add` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2542 |
| 更新日期 | `2023-05-11` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
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
| `weight` | body | string | 是 | 重量 | `1000` |
| `weight_unit` | body | number | 是 | 重量单位，0-kg, 1-g | `1` |
| `remark` | body | string | 否 | 预留字段，供应商可见备注 | `备注` |
| `quality_list` | body | array | 否 | 资质，可通过/suppyProduct/GetSupplyProductUpdateRule获取 | `` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_attachments` | body | array | 是 | 资质 | `` |
| `    └ media_type` | body | number | 是 | 1-图片，2-pdf | `1` |
| `    └ url` | body | string | 是 | 凭证url | `\"http://www.byted***.com/YYYY\"` |
| `spec_name` | body | string | 否 | 如果不填，则规格名为各级规格名用 \"-\" 自动生成 | `颜色-尺码` |
| `specs` | body | string | 是 | 通用规格，能被同类产品通用。多规格用^分隔，规格与规格值用\|分隔，多个规格值用,分隔。 | `颜色\|红色,黑色^尺码\|S,M` |
| `spec_prices` | body | string | 是 | sku详情，数量应该等于规格1规格2规格3，sku数量和规格组合数必须一致， sku库存数量必须大于0。suggest_retail_price表示建议零售价不能低于supply_price.stockNum因为历史原因格式是驼峰注意，incremental目前只支持传true,sync_stock_List在只有全国仓模式下也是个数组 | `[{	\"spec_detail_name1\":\"红色\",	\"spec_detail_name2\":\"S\",	\"spec_detail_name3\":\"\",	\"sync_stock_List\":[{		\"out_warehouseId\":\"w11111\",		\"incremental\":true,		\"idempotentId\":\"d11111\",		\"stockNum\":1	}],	\"supply_price\":100,\"suggest_retail_price\":110,\"outer_sku_id\":\"\"},{	\"spec_detail_name1\":\"红色\",	\"spec_detail_name2\":\"M\",	\"spec_detail_name3\":\"\",	\"sync_stock_List\":[{		\"out_warehouseId\":\"w11111\",		\"incremental\":true,		\"idempotentId\":\"d11111\",		\"stockNum\":1	}],	\"supply_price\":100,\"suggest_retail_price\":110,\"outer_sku_id\":\"\"},{	\"spec_detail_name1\":\"黑色\",	\"spec_detail_name2\":\"S\",	\"spec_detail_name3\":\"\",	\"sync_stock_List\":[{		\"out_warehouseId\":\"w11111\",		\"incremental\":true,		\"idempotentId\":\"d11111\",		\"stockNum\":1	}],	\"supply_price\":100,\"suggest_retail_price\":110,\"outer_sku_id\":\"\"},{	\"spec_detail_name1\":\"黑色\",	\"spec_detail_name2\":\"M\",	\"spec_detail_name3\":\"\",	\"sync_stock_List\":[{		\"out_warehouseId\":\"w11111\",		\"incremental\":true,		\"idempotentId\":\"d11111\",		\"stockNum\":1	}],\"supply_price\":100,\"suggest_retail_price\":110,\"outer_sku_id\":\"\"}]` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `product_format_new` | body | string | 是 | 属性，通过/supplyProduct/getSupplyProductUpdateRule获取 格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]} name的类型是string，value和diy_type的类型是number | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}]}` |
| `extends` | body | string | 否 | 扩展信息 | `{}` |
| `white_back_ground_pic_url` | body | string | 否 | 素材中心url | `白底图` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/supplyProduct/add?app_key=your_appkey_here&method=supplyChain.supplyProduct.add&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | number | product_id | `11111` |
| `outer_product_id` | string | outer_product_id | `1111` |
| `create_time` | number | create_time | `1657800575` |
| `sku_list` | array | sku列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1020:参数异常，请检查后重试\|缺失必填的类目属性:上市年份季节;（sub_code: isv.business-failed:1020） | 检查后重试 |
| `50002` | 业务处理失败 / 3200:创建分销品错误\|外部货品编码 5017835326802 已被另一个spu级货品 7200578387159843107 使用, 请检查后重试（sub_code: isv.business-failed:3200） | 检查后重试 |
| `50002` | 业务处理失败 / 3206:规格图与主规格不匹配（sub_code: isv.business-failed:3206） | 检查后重试 |
| `50002` | 业务处理失败 / 3000:查询供应商错误请重试（sub_code: isv.business-failed:3000） | 重试 |
| `50002` | 业务处理失败 / 4003:查询仓信息错误（sub_code: isv.business-failed:4003） | 检查后重试 |
| `50002` | 业务处理失败 / 3202:获取产品发布规则失败（sub_code: isv.business-failed:3202） | 重试 |
| `50002` | 业务处理失败 / 3203:获取SPU规则失败（sub_code: isv.business-failed:3203） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "create_time": "1657800575",
    "outer_product_id": "1111",
    "product_id": "11111",
    "sku_list": [
      {
        "outer_sku_id": "123456",
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
  "sub_code": "isv.business-failed:1020",
  "sub_msg": "1020:参数异常，请检查后重试|缺失必填的类目属性:上市年份季节;"
}
```

## 备注
