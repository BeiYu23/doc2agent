# supplyChain.supplyProductV2.addProduct

> 创建货品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.addProduct` |
| 中文名 | 创建货品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6679 |
| 更新日期 | `2025-04-23` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | mixed | 是 | 叶子类目 | `20000` |
| `weight_unit` | body | mixed | 否 | 重量单位，0-kg, 1-g | `0` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图 | `http://aaaa` |
| `quality_list` | body | array | 否 | 资质 | `` |
| `  └ quality_key` | body | string | 是 | 资质种类key | `111` |
| `  └ quality_name` | body | string | 是 | 资质种类名称 | `1111` |
| `  └ quality_attachments` | body | array | 否 | 资质附件 | `` |
| `    └ media_type` | body | mixed | 否 | 1-图片，2-pdf 3-网页url | `1` |
| `    └ url` | body | string | 否 | 资源url | `xxx` |
| `  └ quality_id` | body | mixed | 否 | 资质id 复用 | `1` |
| `  └ quality_content_name` | body | string | 否 | 资质名 | `xxx` |
| `ban_scheme_code` | body | string | 是 | 限售方案，如果不限售传空字符串，否则传入对应的限售方案code | `123` |
| `pic` | body | string | 否 | 商品轮播图，多张图片用 \"\|\" 分开 | `img_url1\|img_url2\|img_url3` |
| `extra` | body | string | 否 | 额外信息 | `111` |
| `long_pic_url` | body | string | 否 | 3:4长图 | `http://aaaa` |
| `standard_brand_id` | body | mixed | 否 | 品牌id，无品牌id则传596120136 | `596120136` |
| `after_sale_service` | body | string | 否 | 售后服务参数,key:value格式。supply_day_return_selector(7天无理由选项)：N天-政策代号，N只支持7和15，政策代号枚举https://bytedance.feishu.cn/docs/doccnF946oh1c98e7mo9DlYZtig 。 supply_red_ass_return（红屁屁无忧）：0不支持，1支持。supply_allergy_return（过敏无忧,仅跨境可选）：0不支持，1支持。 damaged_order_return（坏损包退）：0不支持，1支持。 support_allergy_returnV2（过敏包退，境内可选）：0不支持，1支持 | `"damaged_order_return": "1"` |
| `spec_info` | body | object | 否 | 规格信息的新字段，用来替代spec_name和specs | `` |
| `  └ spec_values` | body | array | 是 | 规格值 | `` |
| `    └ name` | body | string | 是 | 规格名称 | `颜色` |
| `    └ values` | body | array | 是 | 规格值 | `` |
| `      └ name` | body | string | 是 | 规格值名称 | `红色` |
| `      └ ext_id` | body | string | 否 | 额外id | `1` |
| `      └ remark` | body | string | 否 | 规格值备注 | `偏红` |
| `      └ cpv_path` | body | array | 否 | 规格值在销售属性中的路径 | `` |
| `        └ cpid` | body | mixed | 否 | cpid | `cpid` |
| `        └ cpvid` | body | mixed | 否 | cpvid | `cpvid` |
| `      └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `        └ template_id` | body | mixed | 否 | 度量衡模板id | `template_id` |
| `        └ values` | body | array | 否 | 度量衡内容 | `` |
| `          └ unit_name` | body | string | 否 | 度量衡单位名称 | `unit_name` |
| `          └ prefix` | body | string | 否 | 前缀 | `prefix` |
| `          └ suffix` | body | string | 否 | 后缀 | `suffix` |
| `          └ module_id` | body | mixed | 否 | 模块id | `module_id` |
| `          └ value` | body | string | 否 | 值内容 | `value` |
| `          └ unit_id` | body | mixed | 否 | 度量衡单位id | `unit_id` |
| `      └ value_id` | body | mixed | 否 | 标准销售属性值id | `value_id` |
| `    └ ext_id` | body | string | 否 | ext_id | `ext_id` |
| `    └ spec_type` | body | mixed | 否 | spec_type | `spec_type` |
| `    └ property_id` | body | mixed | 否 | 标准销售属性id | `1234` |
| `  └ ext_id` | body | string | 否 | ext_id | `ext_id` |
| `  └ spec_name` | body | string | 否 | spec_name | `spec_name` |
| `return_address_id` | body | mixed | 是 | 退货地址 | `1234` |
| `name` | body | string | 是 | 商品名称 | `xxxx` |
| `recommend_remark` | body | string | 否 | 商家推荐语 | `这个商品很好啊` |
| `after_sale_service_v2` | body | object | 否 | 售后承诺 | `` |
| `  └ is_large_product` | body | mixed | 否 | 是否是大件商品，1-是 | `0` |
| `  └ three_guarantees` | body | object | 否 | 三包服务配置 | `` |
| `    └ service_type` | body | mixed | 否 | 服务方式，fix extended | `service_type` |
| `    └ duration` | body | mixed | 否 | 时长 | `duration` |
| `outer_product_id` | body | string | 是 | 外部product_id | `xxxx` |
| `description` | body | string | 是 | 商品描述，目前只支持图片。多张图片用 \"\|\" 分开 | `img_url1\|img_url2\|img_url3` |
| `size_info_template_id` | body | mixed | 否 | 尺码表模板ID | `111` |
| `spec_prices_v2` | body | array | 否 | 新sku字段 | `` |
| `  └ stock_serial_no_list` | body | array | 否 | 库存实物序列号，如手机即为每个手机的IMEI | `["123","234"]` |
| `  └ supply_price` | body | mixed | 是 | 供货价，单位：分 | `10000` |
| `  └ sell_properties` | body | array | 否 | 销售属性 | `` |
| `    └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `      └ template_id` | body | mixed | 否 | 度量衡模板id | `template_id` |
| `      └ values` | body | array | 否 | 度量衡内容 | `` |
| `        └ module_id` | body | mixed | 否 | 模块id | `module_id` |
| `        └ value` | body | string | 否 | 值内容 | `value` |
| `        └ unit_id` | body | mixed | 否 | 度量衡单位id | `unit_id` |
| `        └ unit_name` | body | string | 否 | 度量衡单位名称 | `unit_name` |
| `        └ prefix` | body | string | 否 | 前缀 | `prefix` |
| `        └ suffix` | body | string | 否 | 后缀 | `suffix` |
| `    └ property_id` | body | mixed | 否 | property_id | `property_id` |
| `    └ property_name` | body | string | 否 | property_name | `property_name` |
| `    └ value_id` | body | mixed | 否 | value_id | `value_id` |
| `    └ value_spec_detail_id` | body | mixed | 否 | 规格值detailId，支持3级以上多规格，代替原specDetailId123 | `value_spec_detail_id` |
| `    └ cpv_path` | body | array | 否 | 销售属性值路径 | `` |
| `      └ cpid` | body | mixed | 否 | cpid | `cpid` |
| `      └ cpvid` | body | mixed | 否 | cpvid | `cpvid` |
| `    └ value_name` | body | string | 否 | value_name | `value_name` |
| `    └ remark` | body | string | 否 | "备注" | `remark` |
| `    └ measurement` | body | object | 否 | 度量衡信息 | `` |
| `      └ measure_unit` | body | string | 否 | 单位名字（g或克等） | `measure_unit` |
| `      └ measure_unit_id` | body | mixed | 否 | 单位id，与类目属性应该保持一致 | `measure_unit_id` |
| `      └ value` | body | string | 否 | 输入值 | `value` |
| `  └ stock_num` | body | mixed | 否 | 库存数量 | `1` |
| `  └ price` | body | mixed | 是 | 建议销售价格，单位分 | `100000` |
| `  └ sku_type` | body | mixed | 否 | 库存类型，默认（0-普通库存） | `sku_type` |
| `  └ cargo` | body | object | 否 | 绑定货品（如果传0 0 表示解绑） | `` |
| `    └ source_type` | body | mixed | 否 | source_type | `source_type` |
| `    └ cargo_id` | body | string | 否 | cargo_id | `cargo_id` |
| `  └ code` | body | string | 否 | 商家编码 | `code` |
| `  └ outer_sku_id` | body | string | 否 | 外部sku_id | `outer_sku_id` |
| `  └ barcodes` | body | array | 否 | 条形码 | `barcodes` |
| `main_image_three_to_four` | body | string | 否 | 商品主图3：4 | `img_url1\|img_url2\|img_url3` |
| `weight` | body | string | 否 | 重量 | `1000` |
| `product_format_new` | body | string | 否 | 属性，格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]} name的类型是string，value和diy_type的类型是number | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}]}` |
| `remark` | body | string | 否 | 商家可见备注 | `备注` |
| `delivery_delay_day` | body | mixed | 否 | 诺发货时间，支持传入9999 、1、 2 （分别表示当日发、次日发、48小时发），具体支持传入的参数范围/product/getProductUpdateRule | `7` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `short_product_name` | body | string | 否 | 导购短标题，短标题可用于物流打单及商品搜索场景，若未填写，则系统将智能生成最优短标题在商详购买页面展示，说明详见：https://school.jinritemai.YOUR_SECRET_KEY?from=shop_article | `合身的POLO` |
| `material_video_id` | body | string | 否 | 主图视频id | `xx` |
| `open_app_source` | body | mixed | 否 | open外部应用来源 | `大晟店长该字段传: int32(1) 其他不用传此字段` |
| `delay_rule` | body | object | 否 | 发货规则配置 | `` |
| `  └ config_type` | body | mixed | 否 | 配置类型1时间点,2时间范围 | `1` |
| `  └ enable` | body | boolean | 否 | 是否开启 | `true` |
| `  └ config_value` | body | mixed | 否 | 发货时间 | `1739116800` |
| `  └ end_time` | body | mixed | 否 | 商家配置的结束时间 | `1739030399` |
| `  └ start_time` | body | mixed | 否 | 商家配置的开始时间 | `1737561600` |
| `secondhand_phone_aggregation_mode` | body | boolean | 否 | 是否二手手机集货模式链路 | `true` |
| `freight_id` | body | mixed | 否 | 运费id | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProductV2.addProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `create_time` | string | 创建时间 | `12345` |
| `sku` | array | sku列表 | `` |
| `code` | mixed | code | `10000` |
| `msg` | string | msg | `xxx` |
| `success` | boolean | 是否成功 | `true` |
| `product_id` | mixed | 货品id | `111` |
| `virtual_product_id` | mixed | 商品id | `222` |
| `outer_product_id` | string | 外部货品id | `333` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "10000",
    "create_time": "12345",
    "msg": "xxx",
    "outer_product_id": "333",
    "product_id": "111",
    "sku": [
      {
        "outer_sku_id": "345",
        "sku_id": "123",
        "virtual_sku_id": "234"
      }
    ],
    "success": "true",
    "virtual_product_id": "222"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
