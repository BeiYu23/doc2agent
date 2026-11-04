# supplyCenter.cargo.edit

> 精选货源平台编辑货品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.cargo.edit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/cargo/edit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5329 |
| 更新日期 | `2023-11-07` |

## 接口说明

- 文档书: 精选货源API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 是 | 商品ID | `1324134322` |
| `category_leaf_id` | body | number | 否 | 叶子类目ID，不支持教育、虚拟、黄金玉石类目 | `123` |
| `name` | body | string | 否 | 商品名称，最多60个字符(30个汉字)，不能含emoj表情 | `xxx补水液保湿` |
| `short_product_name` | body | string | 否 | 导购短标题，短标题可用于物流打单及商品搜索场景，若未填写，则系统将智能生成最优短标题在商详购买页面展示，说明详见：https://school.jinritemai.YOUR_SECRET_KEY?from=shop_article | `补水液` |
| `outer_product_id` | body | string | 否 | 外部product_id | `12345` |
| `mobile` | body | string | 否 | 货源客服电话号码 | `40012345` |
| `substitute_goods_url` | body | string | 否 | 货源平台商品地址 | `https://xx.xxx` |
| `outer_platform` | body | string | 否 | 货源平台类型，1：1688精选，2：17网，3：91家纺网 | `1` |
| `supplier_id` | body | string | 否 | 供应商ID，会被用于采购单拆单 | `1234` |
| `supplier_phone` | body | string | 否 | 供应商手机号，相同供应商ID以最新一次上传为准 | `40010000` |
| `supplier_company_name` | body | string | 否 | 供应商公司名称，相同供应商ID以最新一次上传为准 | `xxx公司` |
| `supplier_license_no` | body | string | 否 | 供应商营业执照，相同供应商ID以最新一次上传为准 | `9xxxxxxxxxM` |
| `product_format_new` | body | string | 否 | 属性，通过/product/getCatePropertyV2获取 格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]} name的类型是string，value和diy_type的类型是number | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}]}` |
| `spu_id` | body | number | 否 | spu_id | `123` |
| `freight_type` | body | string | 否 | 1-包邮，2-非偏远地区包邮，3-不包邮 | `3` |
| `freight_remark` | body | string | 否 | 不包邮时需填写价格区间 | `1-5元` |
| `outer_sell_num` | body | number | 否 | 外部销量 | `20000` |
| `outer_sort_factor` | body | number | 否 | 排序因子，展示货品时，按该值倒排序；不填时，默认赋值为outer_sell_num | `20000` |
| `recommend_remark` | body | string | 否 | 商家推荐语，不能含emoj表情 | `这件商品真好用` |
| `pic` | body | string | 否 | 商品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过1M。 | `img_url1\|img_url2\|img_url3` |
| `description` | body | string | 否 | 商品描述，目前只支持图片。多张图片用 \"\|\" 分开。不能用其他网站的文本粘贴，这样会出现css样式不兼容。总图片数量不得超过50张。 | `img_url1\|img_url2\|img_url3` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图 | `http://aaaa` |
| `long_pic_url` | body | string | 否 | 3:4长图 | `http://aaaa` |
| `material_video_id` | body | string | 否 | 主图视频id | `vaaa` |
| `main_image_three_to_four` | body | string | 否 | 商品主图3:4，多张图片用 \"\|\" 分开，最多5张，大小不超过1M。 | `img_url1\|img_url2\|img_url3` |
| `spec_name` | body | string | 否 | V1版本。如果不填，则规格名为各级规格名用 \"-\" 自动生成 | `颜色-尺码` |
| `specs` | body | string | 否 | V1版本。编辑时不可新增/删除子规格项，可编辑值。店铺通用规格，能被同类商品通用。多规格用^分隔，规格与规格值用\|分隔，多个规格值用,分隔。如果创建或编辑现货+预售商品或新预售商品时，须包含发货时效，如：颜色\|黑色,白色,黄色^尺码\|S,M,L^发货时效\|5天内发货,15天内发货 | `颜色\|红色,黑色^尺码\|S,M` |
| `spec_prices` | body | string | 否 | V1版本。sku详情，数量应该等于规格1规格2规格3，sku数量和规格组合数必须一致 sku不可售时，库存可设置为0。price单位为分。 delivery_infos为SKU物流信息，info_value为字符串类型（示例："12"），info_type填weight，info_unit支持mg,g,kg，超市小时达场景主品用普通库存，子品用区域库存（"sku_type": 1 // 区域库存，"stock_num_map": {"123": 99999 // 门店ID:库存数量}）; “gold_process_charge”为黄金加工费，只有计价金类目可填并且必填。 sell_properties为sku规格信息，代替spec_detail_name1、spec_detail_name2、spec_detail_name3，支持填写超过三级规格，样式:[{"property_id":123,"property_name":"颜色","value_id":456,"value_name":"红色","remark":"偏深"},{"property_id":789,"property_name":"净含量","value_id":891,"value_name":"30ml","remark":null,"measurement":{"measure_unit":"ml","measure_unit_id":4,"value":"30"}}] 其中property_id规格项属性id,自定义时传0,property_name为规格项名称,value_id为规格值属性id自定义时传0,value_name为规格值名称,remark为规格值备注(选填),measurement为度量衡信息，当规格值为度量衡属性自定义值时传递。 | `[{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":11,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":22,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":44,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":55,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]}]` |
| `spec_info` | body | object | 否 | V2版本。编辑时不可新增/删除子规格项，可编辑值。规格信息的新字段，用来替代spec_name和specs | `` |
| `  └ spec_name` | body | string | 否 | 如果不填，则规格名为 各级规格（spec_values.name） 用 \"-\" 自动生成 | `颜色-尺码` |
| `  └ spec_values` | body | array | 否 | 规格，有多个 | `` |
| `    └ property_name` | body | string | 是 | 销售属性名称，与规格名称相同。 | `颜色` |
| `    └ values` | body | array | 否 | 销售属性值，与规格值相同。 | `` |
| `      └ value_name` | body | string | 是 | 销售属性值 | `黄色` |
| `      └ remark` | body | string | 否 | 销售属性值备注 | `偏深` |
| `      └ value_id` | body | number | 否 | 标准销售属性值id | `123` |
| `      └ cpv_path` | body | array | 否 | 规格值在销售属性中的路径 | `` |
| `        └ cpid` | body | number | 否 | 属性id | `123` |
| `        └ cpvid` | body | number | 否 | 属性值id | `123` |
| `      └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `        └ template_id` | body | number | 否 | 度量衡模版id | `123` |
| `        └ values` | body | array | 否 | 度量衡内容 | `` |
| `          └ module_id` | body | number | 否 | 模版id | `354` |
| `          └ value` | body | string | 否 | 值内容 | `10` |
| `          └ unit_id` | body | number | 否 | 度量衡单位id | `2` |
| `          └ unit_name` | body | string | 否 | 度量衡单位名称 | `g` |
| `          └ prefix` | body | string | 否 | 前缀 | `""` |
| `          └ suffix` | body | string | 否 | 后缀 | `"-"` |
| `    └ property_id` | body | number | 否 | 标准销售属性id | `123` |
| `spec_prices_v2` | body | array | 否 | V2版本。新sku参数，代替spec_prices | `` |
| `  └ sell_properties` | body | array | 否 | 销售属性（逐步替代specDetailId1、2、3，过渡期互相兼容，大于三级规格时只能用sellProperty）。 | `` |
| `    └ property_name` | body | string | 否 | 销售属性名称 | `颜色` |
| `    └ value_name` | body | string | 否 | 销售属性值 | `黄色` |
| `  └ stock_num` | body | number | 否 | 库存 | `100` |
| `  └ price` | body | number | 否 | 价格 | `100` |
| `  └ code` | body | string | 否 | sku code | `xxx` |
| `  └ outer_sku_id` | body | string | 否 | 外部Sku id | `1234` |
| `  └ delivery_infos` | body | array | 否 | SKU物流信息 | `` |
| `    └ info_type` | body | string | 否 | 信息类型，目前只有 weight 一种 | `weight` |
| `    └ info_value` | body | string | 否 | 信息值 | `10` |
| `    └ info_unit` | body | string | 否 | 信息计量单位，info_type=weight时，可取 mg/g/kg | `g` |
| `  └ sku_classification_type` | body | string | 否 | SKU分类信息 | `main_sale_single_product` |
| `  └ sku_id` | body | number | 否 | skuId,支持基于skuId修改sku信息 | `1234` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `weight` | body | string | 否 | 重量数值 | `10` |
| `weight_unit` | body | number | 否 | 重量单位，0-kg, 1-g | `g` |
| `quality_list` | body | array | 否 | 在发布商品的时候需要填写商品资质，可以通过这个接口获取当前类目下需要填写的资质列表。https://op.jinritemai.com/docs/api-docs/14/1382 | `` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_attachments` | body | array | 是 | 资质附件，仅支持图片、pdf | `` |
| `    └ media_type` | body | number | 是 | 附件类型，1-图片，2-pdf | `1` |
| `    └ url` | body | string | 是 | 附件url | `http://www.byted***.com/YYYY` |
| `force_use_quality_list` | body | boolean | 否 | 强制使用qualityList做全覆盖操作，qualityList传空代表清空 | `false` |
| `standard_brand_id` | body | number | 否 | 品牌id，通过/brand/list获取，无品牌id则传596120136 | `123` |
| `reference_price` | body | number | 否 | 参考价，单位分，需大于商品价格并小于商品价格的10倍 | `1000` |
| `reference_price_certificate` | body | object | 否 | 参考价凭证 | `` |
| `  └ certificate_type` | body | number | 否 | 通过/product/getProductUpdateRule获取可选的参考价格类型 | `1` |
| `  └ certificate_urls` | body | array | 否 | 凭证url，仅能有一张 | `["http://www.aaa.com"]` |
| `size_info_template_id` | body | number | 否 | 尺寸模板id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.cargo.edit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照编辑商品接口（sub_code: isv.parameter-invalid:40004） | https://op.jinritemai.com/docs/api-docs/14/250 |
| `40004` | 非法的参数 / 参照编辑商品接口（sub_code: isv.parameter-invalid:40002） | https://op.jinritemai.com/docs/api-docs/14/250 |
| `50002` | 业务处理失败 / 参照编辑商品接口（sub_code: isv.business-failed:50002） | https://op.jinritemai.com/docs/api-docs/14/250 |

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
  "sub_code": "isv.parameter-invalid:40004",
  "sub_msg": "参照编辑商品接口"
}
```

## 备注
