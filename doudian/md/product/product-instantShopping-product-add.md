# 即时零售商家商品发布

> instantShopping.product.add — 即时零售商家商品发布接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 即时零售商家商品发布 |
| 文档地址 | `/docs/doudian/product/product-instantShopping-product-add` |
| 接口 ID | `doudian.product.instantShopping.product.add` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/6525 |
| 更新日期 | `2026-09-14` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_product_id` | body | string | 是 | 商家编码字段，外部自定义字段，不支持填写后再次编辑，通常在对外开放打通场景中使用，建议通过此字段维护唯一映射关系，请在传入时保证唯一性 | `25381` |
| `product_type` | body | mixed | 否 | 枚举说明 0-普通，3-虚拟，6玉石闪购，7云闪购 | `0` |
| `category_leaf_id` | body | mixed | 是 | 叶子类目ID，通过/shop/getShopCategory接口获取 | `20000` |
| `name` | body | string | 是 | 商品名称，最多60个字符(30个汉字)，不能含emoj表情 | `xxx补水液` |
| `pic` | body | string | 是 | 商品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过5M。 | `img_url1\|img_url2\|img_url3` |
| `description` | body | string | 否 | 商品描述，目前只支持图片。多张图片用 \"\|\" 分开。不能用其他网站的文本粘贴，这样会出现css样式不兼容。总图片数量不得超过50张。 | `img_url1\|img_url2\|img_url3` |
| `pay_type` | body | mixed | 否 | 支付方式，0货到付款 1在线支付，2，货到付款+在线支付 | `1` |
| `reduce_type` | body | mixed | 是 | 1 减库存类型：1-拍下减库存 2-付款减库存 | `1` |
| `freight_id` | body | mixed | 否 | 运费模板id，传0表示包邮，通过/freightTemplate/list接口获取 | `123` |
| `delivery_delay_day` | body | mixed | 否 | delivery_delay_day： 承诺发货时间，单位是天,不传则默认为2天。现货发货(presell_type=0)和阶梯发货模式(presell_type=2)时必填，支持传入9999 、1、 2 （分别表示当日发、次日发、48小时发），具体支持传入的参数范围/product/getProductUpdateRule | `2` |
| `presell_type` | body | mixed | 否 | 发货模式，0-现货发货，1-预售发货，2-阶梯发货，默认0 | `0` |
| `presell_delay` | body | mixed | 否 | 全款预售模式时的发货时间/阶梯模式下阶梯发货时间，具体支持传入的参数范围/product/getProductUpdateRule。 | `7` |
| `presell_end_time` | body | string | 否 | 预售结束时间，格式2020-02-21 18:54:27，最多支持设置距离当前30天 | `2020-02-21 18:54:27` |
| `quality_list` | body | array | 否 | 资质，可通过/product/qualificationConfig获取 | `` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_attachments` | body | array | 是 | 资质 | `` |
| `    └ url` | body | string | 是 | 凭证url | `\"http://www.byted***.com/YYYY\"` |
| `    └ media_type` | body | mixed | 是 | 1-图片 | `1` |
| `  └ quality_id` | body | mixed | 否 | 资质id | `1234` |
| `  └ quality_content_name` | body | string | 否 | 资质名 | `版权页资质` |
| `maximum_per_order` | body | mixed | 否 | 每个用户每次下单限购件数 | `200` |
| `limit_per_buyer` | body | mixed | 否 | 每个用户累计限购件数 | `1` |
| `minimum_per_order` | body | mixed | 否 | 每个用户每次下单至少购买的件数 | `2` |
| `product_format_new` | body | string | 否 | 属性，通过/product/getCatePropertyV2获取 格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]} name的类型是string，value和diy_type的类型是number | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}]}` |
| `spu_id` | body | mixed | 否 | 1111 | `14567` |
| `appoint_delivery_day` | body | mixed | 否 | 可预约发货天数 | `0` |
| `standard_brand_id` | body | mixed | 否 | 品牌id，通过/brand/list获取，无品牌id则传596120136 | `无品牌：596120136` |
| `presell_config_level` | body | mixed | 否 | 0：全款预售，1：sku预售，2：现货+预售 ，3：新预售 | `0` |
| `presell_delivery_type` | body | mixed | 否 | 全款预售和sku预售时传递，其他不传： 0 预售结束后发货 1支付完成后发货 | `1` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图url(仅素材中心url有效)，白底图比例要求1:1 | `http://aaaa` |
| `long_pic_url` | body | string | 否 | 3:4长图url(仅素材中心url有效) | `http://aaaa` |
| `after_sale_service` | body | string | 否 | 推荐传入，售后服务参数,key:value格式。supply_day_return_selector(7天无理由选项)：N天-政策代号，N只支持7和15，政策代号枚举https://bytedance.feishu.cn/docs/doccnF946oh1c98e7mo9DlYZtig。 | `supply_day_return_selector:7-1` |
| `sell_channel` | body | array | 否 | 售卖方式;0:全渠道手售卖,1:仅指定直播间售卖 | `0` |
| `start_sale_type` | body | mixed | 否 | 审核通过后上架售卖时间配置:0-立即上架售卖 1-放入仓库 | `0` |
| `size_info_template_id` | body | mixed | 否 | 尺码模板ID | `101` |
| `pickup_method` | body | string | 否 | "0": 普通商品-使用物流发货, | `0` |
| `material_video_id` | body | string | 否 | 主图视频ID，可以先通过https://op.jinritemai.com/docs/api-docs/69/1617接口上传视频，获取审核通过的视频素材ID进行传入 任务需要验证 | `vaaaa` |
| `name_prefix` | body | string | 否 | 通过/product/getRecommendName接口推荐的商品标题前缀（注意系统根据类目属性生成前缀字符串时，末尾有一个空格） | `钛钢木质耳饰` |
| `sale_limit_id` | body | mixed | 否 | 限售模板ID | `123` |
| `reference_price` | body | mixed | 否 | 参考价，单位分，需大于商品价格并小于商品价格的10倍 | `12300` |
| `reference_price_certificate` | body | object | 否 | 参考价凭证信息 | `` |
| `  └ certificate_type` | body | mixed | 是 | 通过/product/getProductUpdateRule获取可选的参考价格类型 | `1` |
| `  └ certificate_urls` | body | array | 是 | 图片url需要使用商品素材中心的url并且只能有一张 | `["http://www.aaa.com"]` |
| `spec_info` | body | object | 是 | 规格详细信息 | `` |
| `  └ spec_values` | body | array | 是 | 规格内容 | `` |
| `    └ values` | body | array | 是 | 规格值 | `` |
| `      └ remark` | body | string | 否 | 备注 | `偏深` |
| `      └ value_id` | body | mixed | 否 | 规格值标准属性值id | `2341` |
| `      └ name` | body | string | 是 | 规格值名称 | `白色` |
| `      └ measure_info` | body | object | 否 | 度量衡结构化信息 | `` |
| `        └ template_id` | body | mixed | 否 | 模版id | `12345` |
| `        └ values` | body | array | 否 | 模块内容 | `` |
| `          └ unit_name` | body | string | 否 | 度量衡单位名称 | `g` |
| `          └ module_id` | body | mixed | 否 | 模块id | `354` |
| `          └ unit_id` | body | mixed | 否 | 度量衡单位id | `2` |
| `          └ suffix` | body | string | 否 | 度量衡后缀 | `"-"` |
| `          └ prefix` | body | string | 否 | 度量衡值前缀 | `""` |
| `          └ value` | body | string | 否 | 度量衡值 | `10` |
| `      └ cpv_path` | body | array | 否 | 规格值导航路径 | `` |
| `        └ cpvid` | body | mixed | 是 | 属性值id | `234` |
| `        └ cpid` | body | mixed | 是 | 属性id | `1234` |
| `    └ property_id` | body | mixed | 否 | 规格项标准属性id | `1234` |
| `    └ name` | body | string | 是 | 规格名称 | `颜色` |
| `main_image_three_to_four` | body | string | 否 | 商品主图3:4，多张图片用 \"\|\" 分开，最多5张，大小不超过5M。 | `img_url1\|img_url2\|img_url3` |
| `short_product_name` | body | string | 否 | 导购短标题，短标题可用于物流打单及商品搜索场景，若未填写，则系统将智能生成最优短标题在商详购买页面展示，说明详见：https://school.jinritemai.YOUR_SECRET_KEY?from=shop_article | `新品牛肉干` |
| `spec_prices_v2` | body | array | 是 | sku参数 | `` |
| `  └ sell_properties` | body | array | 是 | 规格信息 | `` |
| `    └ value_name` | body | string | 是 | 规格值名称 | `白色` |
| `    └ property_name` | body | string | 是 | 规格项名称 | `颜色` |
| `  └ supplier_id` | body | string | 否 | 供应商编码 | `ab` |
| `  └ stock_num` | body | mixed | 否 | 库存数量。跨境必须走区域库存，stock_num设置0。 | `101110` |
| `  └ code` | body | string | 否 | 商家sku编码 | `XXX` |
| `  └ barcodes` | body | array | 否 | 条形码 | `[]` |
| `  └ stock_num_map` | body | string | 否 | 仓ID -> 库存数量。跨境业务大部分都是必传，格式为：Map<商家仓id,> | `111:22` |
| `  └ supply_price` | body | mixed | 否 | 供货价,单位：分，nil代表不修改，0代表清空 | `13` |
| `  └ delivery_infos` | body | array | 是 | SKU运输信息 | `` |
| `    └ info_type` | body | string | 是 | 信息类型 | `1` |
| `    └ info_value` | body | string | 是 | 信息值 | `10` |
| `    └ info_unit` | body | string | 是 | 信息计量单位 | `g` |
| `  └ step_stock_num` | body | mixed | 否 | 阶梯库存数量 | `1` |
| `  └ outer_sku_id` | body | string | 否 | 外部skuid | `sad` |
| `  └ sku_status` | body | boolean | 否 | true：表示sku上架 false：表示sku下架 | `true` |
| `  └ presell_delay` | body | mixed | 否 | 预售天数 | `5` |
| `  └ price` | body | mixed | 是 | 价格 | `100` |
| `  └ sku_classification_type` | body | string | 否 | sku分类信息，对应枚举值 "main_sale_single_product" - 主售款（单品） "main_sale_multi_product" - "主售款（多件装）" "main_sale_combination" - 主售款（组合品） "non_main_sale" - 非主售款 "information_description" - 信息说明/防拍 | `main_sale_single_product` |
| `  └ sku_type` | body | mixed | 否 | 库存类型 0-普通库存，1-区域库存，10-阶梯库存 | `0` |
| `with_sku_type` | body | boolean | 否 | true:主动设置库存类型（仅对区域库存生效，普通库存、阶梯库存不受此字段影响） | `true` |
| `name_suffix` | body | string | 否 | 通过/product/getRecommendName接口推荐的商品标题后缀（注意系统根据类目属性生成后缀字符串时，前面可能有一个空格） | `36.9度` |
| `use_brand_name` | body | boolean | 否 | 是否勾选使用品牌名, 注意勾选时需要接入/product/getRecommendName接口 | `false` |
| `commit` | body | boolean | 否 | false仅保存，true保存+提审 | `true` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `food_label_image_url` | body | string | 否 | 食品标签图 | `https://p3-aio.ecombdimg.com/obj/ecom-shop-material/png_m_f5c653b76b44651364c3ca89e5328b20_sx_1243369_www1262-1262` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.product.add&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | mixed | product_id | `product_id` |
| `outer_product_id` | string | outer_product_id | `outer_product_id` |
| `create_time` | string | create_time | `create_time` |
| `sku` | array | 1 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / outProductId或者outerProductId已经存在（sub_code: isv.business-failed:110101114） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3356 |
| `50002` | 业务处理失败 / 2010320:商品创建失败: 品牌必填，请重新选择品牌（sub_code: isv.business-failed:2010320） | 请检查品牌字段是否填写 |
| `50002` | 业务处理失败 / 110270136:商品创建失败: 物流信息类型不合法（sub_code: isv.business-failed:110270136） | 请检查入参信息 |
| `50002` | 业务处理失败 / 4:product_format_new格式不正确（sub_code: isv.business-failed:4） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010004:商品创建失败: 规格项名称参数有误（sub_code: isv.business-failed:2010004） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010005:商品创建失败: 该商品的类目【咖啡/麦片/冲饮/饮料/果味/风味饮料】无资质授权,请前往【店铺-店铺信息设置-店铺资质-行业资质】中申请授权（sub_code: isv.business-failed:2010005） | 请前往【店铺-店铺信息设置-店铺资质-行业资质】中申请授权 |
| `50002` | 业务处理失败 / 110270179:商品创建失败: 校验预售发货信息失败发货时间配置不满足要求（sub_code: isv.business-failed:110270179） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110201001:商品创建失败: 未查询到该类目（sub_code: isv.business-failed:110201001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110502009:白底图#white_back_ground_pic_url非素材中心url（sub_code: isv.business-failed:110502009） | 请上传图片到素材中心后再进行发品 |
| `50002` | 业务处理失败 / 110280111:商品创建失败: 每次限购件数不能超过累计限购件数（sub_code: isv.business-failed:110280111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101187:商品创建失败: 未命中商品名称后缀推荐规则，标题后缀(name_suffix)应该置空（sub_code: isv.business-failed:110101187） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110310107:商品创建失败: 参考价需大于等于最高售卖价且小于最高售卖价10倍（sub_code: isv.business-failed:110310107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110250127:商品创建失败: 图片长宽比非1:1（sub_code: isv.business-failed:110250127） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215111:商品创建失败: 类目属性填写不完整，请补充：材质（sub_code: isv.business-failed:110215111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110220160:商品创建失败: 条码：1001011在商品ID：[3694584246200041885]中已存在,不可重复发布（sub_code: isv.business-failed:110220160） | 条码在相同店铺具有唯一性，请更改条码后再发品 |
| `50002` | 业务处理失败 / 2010001:商品创建失败: 外部商品ID重复（sub_code: isv.business-failed:2010001） | 已存在相同outerProductId的商品，勿重复发品 |
| `50002` | 业务处理失败 / 110270019:商品创建失败: sku重量信息必填（sub_code: isv.business-failed:110270019） | sku重量信息是必填字段，请维护对应信息 |
| `50002` | 业务处理失败 / 110220113:商品创建失败: sku数量和规格组合数不匹配，请重新选择规格（sub_code: isv.business-failed:110220113） | 110220113:商品创建失败: sku数量和规格组合数不匹配，请重新选择规格 |
| `50002` | 业务处理失败 / 110220019:商品创建失败: 规格「规格详情」对应的规格值存在非法字符，请修改后重试；（sub_code: isv.business-failed:110220019） | 110220019:商品创建失败: 规格「规格详情」对应的规格值存在非法字符，请修改后重试； |
| `50002` | 业务处理失败 / 110101150:商品创建失败: 商品标题最长不能超过50个汉字（100个字符）（sub_code: isv.business-failed:110101150） | 110101150:商品创建失败: 商品标题最长不能超过50个汉字（100个字符） |
| `50002` | 业务处理失败 / 110220016:商品创建失败: 规格规格对应的规格值--仅包含特殊字符，请修改并输入有效信息；（sub_code: isv.business-failed:110220016） | 110220016:商品创建失败: 规格规格对应的规格值--仅包含特殊字符，请修改并输入有效信息； |
| `50002` | 业务处理失败 / 110310118:商品创建失败: 售卖价需大于等于0.01元（sub_code: isv.business-failed:110310118） | 110310118:商品创建失败: 售卖价需大于等于0.01元 |
| `50002` | 业务处理失败 / 110101145:商品创建失败: “商品标题”不可含有非法字符（sub_code: isv.business-failed:110101145） | 110101145:商品创建失败: “商品标题”不可含有非法字符 |
| `50002` | 业务处理失败 / 110360101:商品创建失败: 品牌不存在或者未审核通过，id:1289434984（sub_code: isv.business-failed:110360101） | 110360101:商品创建失败: 品牌不存在或者未审核通过，id:1289434984 |
| `50002` | 业务处理失败 / 4100001:外部商品ID在店铺下需唯一，请勿重复创建（sub_code: isv.business-failed:4100001） | 4100001:外部商品ID在店铺下需唯一，请勿重复创建 |
| `50002` | 业务处理失败 / 110270020:商品创建失败: sku重量不能大于99999.999g（sub_code: isv.business-failed:110270020） | 110270020:商品创建失败: sku重量不能大于99999.999g |
| `50002` | 业务处理失败 / 110330102:商品创建失败: 请修改“售后服务“，该类目已不再支持该售后政策（sub_code: isv.business-failed:110330102） | 110330102:商品创建失败: 请修改“售后服务“，该类目已不再支持该售后政策 |
| `50002` | 业务处理失败 / 2010316:商品创建失败: 该类目需要支持7天无理由退货（sub_code: isv.business-failed:2010316） | 2010316:商品创建失败: 该类目需要支持7天无理由退货 |
| `50002` | 业务处理失败 / 110210021:商品创建失败: 该商品对应的类目已处于禁发状态，需先修改商品对应类目为合适类目（sub_code: isv.business-failed:110210021） | 110210021:商品创建失败: 该商品对应的类目已处于禁发状态，需先修改商品对应类目为合适类目 |
| `50002` | 业务处理失败 / 110103015:商品创建失败: 外部商品ID重复（sub_code: isv.business-failed:110103015） | 110103015:商品创建失败: 外部商品ID重复 |
| `50002` | 业务处理失败 / 5000001:业务错误（sub_code: isv.business-failed:5000001） | 5000001:业务错误 |
| `50002` | 业务处理失败 / 2010003:类目属性填写不完整，请补充：产地与包装（sub_code: isv.business-failed:2010003） | 2010003:类目属性填写不完整，请补充：产地与包装 |
| `50002` | 业务处理失败 / 110220231:“商品规格”中的[[规格]]填写方式已调整，当前不支持自定义录入，请从下拉列表中选择标准属性值进行填写（sub_code: isv.business-failed:110220231） | 110220231:“商品规格”中的[[规格]]填写方式已调整，当前不支持自定义录入，请从下拉列表中选择标准属性值进行填写 |
| `50002` | 业务处理失败 / 110405002:保证金余额不足，请前往保证金中心充值（sub_code: isv.business-failed:110405002） | 110405002:保证金余额不足，请前往保证金中心充值 |
| `50002` | 业务处理失败 / 110215105:属性值不存在， propertyId:5975、propertyName:产地与包装（sub_code: isv.business-failed:110215105） | 110215105:属性值不存在， propertyId:5975、propertyName:产地与包装 |
| `50002` | 业务处理失败 / 2010020:CCC证书编号：该编号无效，请按商品对应的3C证书填写编号（sub_code: isv.business-failed:2010020） | 2010020:CCC证书编号：该编号无效，请按商品对应的3C证书填写编号 |
| `50002` | 业务处理失败 / 110360108:品牌资质规则查询失败（sub_code: isv.business-failed:110360108） | 110360108:品牌资质规则查询失败 |
| `50002` | 业务处理失败 / 110250169:该类目要求上传尺码组件信息，请补充后提交（sub_code: isv.business-failed:110250169） | 110250169:该类目要求上传尺码组件信息，请补充后提交 |
| `50002` | 业务处理失败 / 110215137:属性“面料材质“的填写格式已升级，属性值“亚麻“不符合填写格式要求，请点击属性输入框重新填写（sub_code: isv.business-failed:110215137） | 110215137:属性“面料材质“的填写格式已升级，属性值“亚麻“不符合填写格式要求，请点击属性输入框重新填写 |
| `50002` | 业务处理失败 / 110250142:【XXXS 体重(斤) 60】需低于更高码数【XXS】（sub_code: isv.business-failed:110250142） | 110250142:【XXXS 体重(斤) 60】需低于更高码数【XXS】 |
| `50002` | 业务处理失败 / 110220214:其他材质含量需<=15%，请修改（sub_code: isv.business-failed:110220214） | 110220214:其他材质含量需<=15%，请修改 |
| `50002` | 业务处理失败 / 110101259:该商品尚未上传食品属性标签图，请使用ISV上传后重试（sub_code: isv.business-failed:110101259） | 110101259:该商品尚未上传食品属性标签图，请使用ISV上传后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "create_time": "create_time",
    "outer_product_id": "outer_product_id",
    "product_id": "product_id",
    "sku": [
      {
        "code": "1",
        "outer_sku_id": "1",
        "sku_id": "3",
        "spec_detail_ids": "1"
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
  "sub_code": "isv.business-failed:110101114",
  "sub_msg": "outProductId或者outerProductId已经存在"
}
```

## 备注
