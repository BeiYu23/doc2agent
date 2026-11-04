# instantShopping.product.editv2

> 编辑商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-product.instantShopping.product.editv2` |
| 中文名 | 编辑商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1570/7448 |
| 更新日期 | `2026-09-09` |

## 接口说明

- 文档书: 商品管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品ID | `3506108675121111111` |
| `product_type` | body | mixed | 否 | 0-普通，3-虚拟，6玉石闪购，7云闪购 | `0` |
| `category_leaf_id` | body | mixed | 否 | 叶子类目ID通过/shop/getShopCategory接口获取 | `20000` |
| `name` | body | string | 否 | 商品名称，至少8个字符（4个汉字），最多60个字符(30个汉字)，不能含emoj表情 | `xxx补水液` |
| `recommend_remark` | body | string | 否 | 商家推荐语，不能含emoj表情 | `这个商品很好啊` |
| `pic` | body | string | 否 | 商品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过5M | `img_url1\|img_url2\|img_url3` |
| `description` | body | string | 否 | 商详图片，多张图片用 \| 分开。图片数量总和，不得超过50张。 | `img_url1\|img_url2\|img_url3` |
| `pay_type` | body | mixed | 否 | 已废弃，支付方式，0货到付款 1在线支付，2，货到付款+在线支付 | `1` |
| `delivery_method` | body | mixed | 否 | 海南免税生效。 0:离岛免税、1:邮寄、2:离岛自提+邮寄 | `7` |
| `cdf_category` | body | string | 否 | 海南免税：海关限购分类编码 | `1` |
| `reduce_type` | body | mixed | 否 | 1 减库存类型：1-拍下减库存 2-付款减库存 | `1` |
| `assoc_ids` | body | string | 否 | 【已废弃】同店商品推荐：为空表示使用系统推荐；多个product_id使用“\|”分开 | `1\|2\|3` |
| `freight_id` | body | mixed | 否 | 运费模板id，传0表示包邮，通过/freightTemplate/list接口获取 | `123` |
| `weight` | body | string | 否 | 重量。数据范围需要小于10000，如果超过，请更换的weight_unit | `1000` |
| `weight_unit` | body | mixed | 否 | 重量单位，0-kg, 1-g | `1` |
| `delivery_delay_day` | body | mixed | 否 | delivery_delay_day： 承诺发货时间，单位是天,不传则默认为2天。现货发货(presell_type=0)和阶梯发货模式(presell_type=2)时必填，支持传入9999 、1、 2 （分别表示当日发、次日发、48小时发），具体支持传入的参数范围/product/getProductUpdateRule | `7` |
| `presell_type` | body | mixed | 否 | 发货模式，0-现货发货，1-预售发货，2-阶梯发货，默认0 | `0` |
| `presell_delay` | body | mixed | 否 | 全款预售模式时的发货时间/阶梯模式下阶梯发货时间，具体支持传入的参数范围/product/getProductUpdateRule | `7` |
| `presell_end_time` | body | string | 否 | 预售结束时间，格式2020-02-21 18:54:27，最多支持设置距离当前30天 | `2020-02-21 18:54:27` |
| `supply_7day_return` | body | mixed | 否 | 【该字段将在2023年4月30日下线，请开发使用最新的after_sale_service字段传值；】是否支持7天无理由，0不支持，1支持，2支持（拆封后不支持） | `该字段将在2023年4月30日下线，请开发使用最新的after_sale_service字段传值；` |
| `mobile` | body | string | 否 | 客服电话号码 | `40012345` |
| `commit` | body | boolean | 是 | false仅保存，true保存+提审 | `true` |
| `remark` | body | string | 否 | 商家可见备注 | `备注` |
| `out_product_id` | body | mixed | 否 | 外部product_id。超市小时达场景不推荐使用 | `123` |
| `quality_list` | body | array | 否 | 资质信息，可通过/product/qualificationConfig获取 | `` |
| `  └ quality_attachments` | body | array | 是 | 资质 | `` |
| `    └ media_type` | body | mixed | 是 | 1-图片 | `1` |
| `    └ url` | body | string | 是 | 凭证url | `\"http://www.byted***.com/YYYY\"` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `spec_name` | body | string | 否 | 【废弃不再使用，请使用spec_info参数】如果不填，则规格名为各级规格名用 \"-\" 自动生成 | `颜色-尺码` |
| `specs` | body | string | 否 | 【废弃不再使用，请使用spec_info参数】店铺通用规格，能被同类商品通用。多规格用^分隔，规格与规格值用\|分隔，多个规格值用,分隔。如果创建或编辑现货+预售商品或新预售商品时，须包含发货时效，如：颜色\|黑色,白色,黄色^尺码\|S,M,L^发货时效\|5天内发货,15天内发货 | `颜色\|红色,黑色^尺码\|S,M` |
| `spec_prices` | body | string | 否 | 【字段废弃，请使用spec_prices_v2】sku详情，数量应该等于规格1规格2规格3，sku数量和规格组合数必须一致 sku不可售时，库存可设置为0。price单位为分。 delivery_infos为SKU物流信息，info_value为字符串类型（示例："12"），info_type填weight，info_unit支持mg,g,kg，超市小时达场景主品用普通库存，子品用区域库存（"sku_type": 1 // 区域库存，"stock_num_map": {"123": 99999 // 门店ID:库存数量}）。gold_process_charge表示商品加工费，只有计价金类目可填并必填。 sell_properties为sku规格信息，代替spec_detail_name1、spec_detail_name2、spec_detail_name3，支持填写超过三级规格，样式:[{"property_id":123,"property_name":"颜色","value_id":456,"value_name":"红色","remark":"偏深"},{"property_id":789,"property_name":"净含量","value_id":891,"value_name":"30ml","remark":null,"measurement":{"measure_unit":"ml","measure_unit_id":4,"value":"30"}}] 其中property_id规格项属性id,自定义时传0,property_name为规格项名称,value_id为规格值属性id自定义时传0,value_name为规格值名称,remark为规格值备注(选填),measurement为度量衡信息，当规格值为度量衡属性自定义值时传递。 | `[{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":11,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":22,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":44,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":55,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]}]` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `maximum_per_order` | body | mixed | 否 | 每个用户每次下单限购件数 | `2` |
| `limit_per_buyer` | body | mixed | 否 | 每个用户累计限购件数 | `3` |
| `minimum_per_order` | body | mixed | 否 | 每个用户每次下单至少购买的件数 | `2` |
| `product_format_new` | body | string | 否 | 通过/product/getCatePropertyV2获取 格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]}, name的类型是string，value和diy_type的类型是number  度量衡参照open度量衡对接文档填写 | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}],\"785\":[{\"measure_info\":{\"template_id\":147,\"values\":[{\"module_id\":396,\"prefix\":\"\",\"suffix\":\"\",\"value\":\"棉\"},{\"module_id\":397,\"prefix\":\"\",\"suffix\":\"\",\"unit_id\":15,\"unit_name\":\"%\",\"value\":\"60\"}]},\"value_id\":\"\",\"value_name\":\"棉60%\"},{\"measure_info\":{\"template_id\":147,\"values\":[{\"module_id\":396,\"prefix\":\"\",\"suffix\":\"\",\"value\":\"聚酯纤维（涤纶）\"},{\"module_id\":397,\"prefix\":\"\",\"suffix\":\"\",\"unit_id\":15,\"unit_name\":\"%\",\"value\":\"40\"}]},\"value_id\":\"\",\"value_name\":\"聚酯纤维（涤纶）40%\"}]}` |
| `spu_id` | body | mixed | 否 | spu id | `不透出` |
| `appoint_delivery_day` | body | mixed | 否 | 可预约发货天数 | `2` |
| `third_url` | body | string | 否 | third_url | `http://img.alicdn.com/xxxx` |
| `extra` | body | string | 否 | extra | `不透出` |
| `src` | body | string | 否 | src | `不透出` |
| `outer_product_id` | body | string | 否 | 外部product id。超市小时达场景不推荐使用 | `11111111111111` |
| `standard_brand_id` | body | mixed | 否 | standard_brand_id，通过/brand/list获取，无品牌id则传596120136 | `111` |
| `need_check_out` | body | boolean | 否 | 卡券类型需要传true | `true` |
| `poi_resource` | body | object | 否 | 卡券信息 | `` |
| `  └ coupon_return_methods` | body | array | 否 | 数组当前只支持一个元素且只可为 1或2，其中 1 表示随时退+过期自动退，2 表示不支持退 | `[1]` |
| `  └ poi_lib_id` | body | mixed | 否 | 门店库id | `7448856056001954098` |
| `  └ code_type` | body | mixed | 否 | 平台产生券码: 1 ; 合作方api实时传入的券码: 4 | `1` |
| `  └ notification` | body | string | 否 | 领取须知 | `领取` |
| `  └ count` | body | mixed | 否 | 券码总量，0/-1表示不限制，平台券时须\u003e0 | `1` |
| `  └ valid_start` | body | mixed | 否 | 卡券有效开始时间，秒单位时间戳 | `1639216083` |
| `  └ link` | body | string | 否 | 兑换链接 | `http://xxx.xxxx.xxx` |
| `  └ valid_days` | body | mixed | 否 | 有效时间段，从领取日开始计算，优先级高于ValidStart-ValidEnd | `1` |
| `  └ valid_end` | body | mixed | 否 | 卡券有效截止时间，秒单位时间戳 | `1639907283` |
| `  └ condition` | body | string | 否 | 券码使用条件 | `券码使用条件` |
| `  └ service_num` | body | string | 否 | 客服电话 | `13111111111` |
| `  └ couponSecondExchange` | body | mixed | 否 | 0-不支持二次兑换，1-支持二次兑换 | `0` |
| `  └ total_can_use_count` | body | mixed | 否 | 可核销总次数 | `1` |
| `force_use_quality_list` | body | boolean | 否 | 使用qualityList覆盖当前商品资质，qualityList传空代表清空 | `false` |
| `car_vin_code` | body | string | 否 | 汽车Vin码 | `VIN11111111111111` |
| `presell_config_level` | body | mixed | 否 | 0：全款预售，1：sku预售，2：现货+预售 ，3：新预售 | `2` |
| `need_recharge_mode` | body | boolean | 否 | 充值模式 | `false` |
| `account_template_id` | body | string | 否 | 多账号模板 | `1` |
| `presell_delivery_type` | body | mixed | 否 | 全款预售和sku预售时传递，其他不传： 0 预售结束后发货  1支付完成后发货 | `1` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图url(仅素材中心url有效) | `http://aaaa` |
| `long_pic_url` | body | string | 否 | 3:4长图url(仅素材中心url有效) | `http://aaaa` |
| `after_sale_service` | body | string | 否 | 售后服务参数,key:value格式  supply_day_return_selector(7天无理由选项)：N天-政策代号，N只支持7和15 supply_red_ass_return（红屁屁无忧）：0不支持，1支持 supply_allergy_return（过敏无忧,仅跨境可选）：0不支持，1支持 damaged_order_return（坏损包退）：0不支持，1支持 support_allergy_returnV2（过敏包退，境内可选）：0不支持，1支持 | `"damaged_order_return": "1"` |
| `sell_channel` | body | array | 否 | 售卖方式;0:全渠道手售卖,1:仅指定直播间售卖 | `[0]` |
| `start_sale_type` | body | mixed | 否 | 审核通过后上架售卖时间配置:0-立即上架售卖 1-放入仓库 | `0` |
| `delay_rule` | body | object | 否 | 特殊日期延迟发货规则 | `` |
| `  └ config_type` | body | mixed | 是 | 1 时间点；2 时间范围 | `1` |
| `  └ start_time` | body | mixed | 是 | 特殊日期延迟发货时间下单开始时间，时间戳，单位秒 | `1643040000` |
| `  └ enable` | body | boolean | 是 | 是否开启特殊日期延迟发货 | `true` |
| `  └ config_value` | body | mixed | 是 | 特殊日期延迟发货时间最晚发货时间，时间戳，单位秒：当config_type=1时，传时间戳，代表最晚x发货；当config_type=2时，传天数，代表延迟x天发货 | `1673539199` |
| `  └ end_time` | body | mixed | 是 | 特殊日期延迟发货时间下单结束时间，时间戳，单位秒 | `1672502400` |
| `material_video_id` | body | string | 否 | 主图视频ID，可以先通过https://op.jinritemai.com/docs/api-docs/69/1617接口上传视频，获取审核通过的视频素材ID进行传入 | `vaaaa` |
| `pickup_method` | body | string | 否 | 提取方式新字段，推荐使用。"0": 普通商品-使用物流发货, "1": 虚拟商品-无需物流与电子交易凭证, "2": 虚拟商品-使用电子交易凭证, "3": 虚拟商品-充值直连 | `0` |
| `size_info_template_id` | body | mixed | 否 | 尺码模板ID | `101` |
| `substitute_goods_url` | body | string | 否 | 外部商品url | `https://xxx.xxx.xxx` |
| `sale_channel_type` | body | string | 否 | 销售渠道类型，可选onlineOnly（纯电商，仅在线上售卖）或sameAsOffline（专柜同款，线上线下都有售卖），云零售商家（https://fxg.jinritemai.com/ffa/merchant-growth/cloud-retail）可以设置 | `sameAsOffline` |
| `name_prefix` | body | string | 否 | 通过/product/getRecommendName接口推荐的商品标题前缀（注意系统根据类目属性生成前缀字符串时，末尾有一个空格） | `钛钢木质耳饰` |
| `store_id` | body | mixed | 否 | 门店ID | `103121` |
| `main_product_id` | body | mixed | 否 | 主商品ID | `3121213` |
| `sale_limit_id` | body | mixed | 否 | 限售模板ID | `123` |
| `reference_price` | body | mixed | 否 | 商品参考价 | `12300` |
| `reference_price_certificate` | body | object | 否 | 参考价凭证相关信息 | `` |
| `  └ certificate_type` | body | mixed | 否 | 参考价凭证类型，通过/product/getProductUpdateRule获取可选类型 | `1` |
| `  └ certificate_urls` | body | array | 否 | 凭证图片，必须是商品素材中心URL，最多允许一张图片 | `["https://www.aaaa.com"]` |
| `main_image_three_to_four` | body | string | 否 | 商品主图3:4，多张图片用 \"\|\" 分开，最多5张，大小不超过5M。 | `img_url1\|img_url2\|img_url3` |
| `unit_price_info` | body | object | 否 | 价格规则信息 | `` |
| `  └ price_rule_type` | body | mixed | 是 | 价格规则类型： 1表示投资金 2表示首饰金 | `1` |
| `  └ process_charge` | body | mixed | 是 | 废弃字段，请写死传0 | `0` |
| `quality_inspection_info` | body | object | 否 | 前置质检相关（特定二手商家、特定二手类目使用） | `` |
| `  └ supported` | body | boolean | 否 | 是否支持前置质检 | `true` |
| `  └ certificate_code` | body | string | 否 | 质检证书编码 | `111` |
| `  └ agency` | body | string | 否 | 机构编码，请通过/inspection/QueryBtasAgencyList接口获取 | `123` |
| `  └ mode` | body | mixed | 否 | 1: 单库存模式，只允许售卖一个sku；2: 多库存模式，不限售卖次数 | `2` |
| `is_c2b_switch_on` | body | boolean | 否 | 是否支持c2b小程序（特定c2b定制商家使用，请使用/product/getProductUpdateRule接口获取是否支持） | `true` |
| `micro_app_id` | body | string | 否 | 支持c2b定制时的小程序id（特定c2b定制商家使用，请使用/product/getProductUpdateRule接口获取是否支持） | `abcde` |
| `is_auto_charge` | body | boolean | 否 | 是否修改为自动充值商品 | `false` |
| `short_product_name` | body | string | 否 | 导购短标题，短标题可用于物流打单及商品搜索场景，说明详见：https://school.jinritemai.YOUR_SECRET_KEY?from=shop_article | `好吃牛肉干` |
| `after_sale_service_v2` | body | object | 否 | 售后服务新结构（老的after_sale_service中的字段后续会慢慢迁移到这里） | `` |
| `  └ three_guarantees` | body | object | 否 | 三包服务配置 | `` |
| `    └ duration` | body | mixed | 否 | 售后天数 | `180` |
| `    └ service_type` | body | mixed | 否 | 服务类型 1-寄修 2-延保 | `1` |
| `  └ is_large_product` | body | mixed | 否 | 当前商品是否是大件商品 | `1-是` |
| `spec_prices_v2` | body | array | 否 | sku新参数，建议切到新参数，后续老参数spec_prices废弃 | `` |
| `  └ customs_report_info` | body | object | 否 | 海关申报要素 | `` |
| `    └ first_measure_unit` | body | string | 否 | 法定第一计量单位 | `"pulata"` |
| `    └ usage` | body | string | 否 | 用途 | `"ces1"` |
| `    └ unit` | body | string | 否 | 售卖单位 | `"yuan"` |
| `    └ second_measure_unit` | body | string | 否 | 法定第二计量单位 | `"fen"` |
| `    └ g_model` | body | string | 否 | 规格型号 | `1` |
| `    └ report_brand_name` | body | string | 否 | 品牌 | `"test"` |
| `    └ report_name` | body | string | 否 | 品名 | `"test"` |
| `    └ second_measure_qty` | body | string | 否 | 法定第二计量数量 | `"法定第二计量数量"` |
| `    └ hs_code` | body | string | 否 | 海关代码 | `"code"` |
| `    └ bar_code` | body | string | 否 | 条形码 | `xd` |
| `    └ first_measure_qty` | body | string | 否 | 法定第一计量数量 | `"法定第一计量数量"` |
| `  └ supply_price` | body | mixed | 否 | 供货价,单位：分，nil代表不修改，0代表清空 | `nil` |
| `  └ sku_id` | body | mixed | 否 | skuId,支持基于skuId修改sku信息 | `1` |
| `  └ gold_process_charge` | body | mixed | 否 | 黄金加工费，单位：分，nil代表不修改 | `1` |
| `  └ presell_delay` | body | mixed | 否 | SKU维度预售发货延迟时间 | `1` |
| `  └ spec_value_lib_id` | body | mixed | 否 | 商品规格值id：懂车帝场景传递 | `1` |
| `  └ stock_num` | body | mixed | 否 | 库存数量 | `1` |
| `  └ outer_sku_id` | body | string | 否 | 外部sku_id-string | `1` |
| `  └ price` | body | mixed | 否 | 价格 | `1` |
| `  └ cargo` | body | object | 否 | 货品信息，如果传0 0 表示解绑） | `` |
| `    └ source_type` | body | mixed | 否 | 货品类型 | `1` |
| `    └ cargo_id` | body | string | 否 | 货品id | `1` |
| `  └ sku_type` | body | mixed | 否 | 库存类型 0-普通库存，1-区域库存，10-阶梯库存 | `0` |
| `  └ multi_time_stocks` | body | array | 否 | 时效库存 | `` |
| `    └ time_type` | body | mixed | 否 | 时效值 | `5` |
| `    └ stock_num` | body | mixed | 否 | 库存数 | `500` |
| `    └ time_desc` | body | string | 否 | 时效描述 | `5天内发` |
| `  └ sell_properties` | body | array | 是 | sku规格信息：规格项规格值 | `` |
| `    └ value_name` | body | string | 否 | 规格值名称 | `红色` |
| `    └ property_name` | body | string | 否 | 规格名称 | `颜色` |
| `  └ delivery_infos` | body | array | 否 | SKU运输信息 | `` |
| `    └ info_type` | body | string | 否 | 信息类型 | `1` |
| `    └ info_value` | body | string | 否 | 信息值 | `"1"` |
| `    └ info_unit` | body | string | 否 | 信息计量单位 | `1` |
| `  └ sku_classification_type` | body | string | 否 | sku分类信息，对应枚举值 "main_sale_single_product" - 主售款（单品） "main_sale_multi_product" - "主售款（多件装）" "main_sale_combination" - 主售款（组合品） "non_main_sale" - 非主售款 "information_description" - 信息说明/防拍 | `main_sale_single_product` |
| `  └ tax_exemption_sku_info` | body | object | 否 | 海南免税：Sku 额外信息 | `` |
| `    └ volume` | body | mixed | 否 | 净含量 | `1` |
| `    └ is_suit` | body | mixed | 否 | 是否套装（0 否 1 是） | `1` |
| `    └ suit_num` | body | mixed | 否 | 套装数量 | `1` |
| `  └ stock_num_map` | body | string | 否 | 仓ID -> 库存数量 | `"FOURPLTEST": 10` |
| `  └ package_sku` | body | array | 否 | 组套包信息 | `` |
| `    └ combo_num` | body | mixed | 否 | 组套包子品数量 | `2` |
| `    └ sub_product_id` | body | mixed | 否 | 组套包子品商品id | `12` |
| `    └ short_name` | body | string | 否 | 组套名称 | `组套名称` |
| `    └ sub_sku_id` | body | mixed | 否 | 组套包子品skuId | `111` |
| `  └ supplier_id` | body | string | 否 | 供应商编码 | `1` |
| `  └ step_stock_num` | body | mixed | 否 | 阶梯库存数 | `1` |
| `  └ code` | body | string | 否 | 商家编码 | `"888"` |
| `  └ sku_status` | body | boolean | 否 | true：表示sku上架 false：表示sku下架 | `true` |
| `  └ barcodes` | body | array | 否 | 条码信息 | `["12"]` |
| `spec_info` | body | object | 否 | 规格模版详细信息 | `` |
| `  └ spec_values` | body | array | 否 | 规格项，如颜色、尺码 | `` |
| `    └ property_id` | body | mixed | 否 | 标准销售属性id | `1` |
| `    └ property_name` | body | string | 是 | 规格项名称，如颜色 | `颜色` |
| `    └ values` | body | array | 是 | 规格值 | `` |
| `      └ cpv_path` | body | array | 否 | 规格值的导航样式路径信息，如色系->色值 | `` |
| `        └ cpvid` | body | mixed | 是 | 如具体白色系的销售属性值id | `1` |
| `        └ cpid` | body | mixed | 是 | 如色系的销售属性id | `2` |
| `      └ value_id` | body | mixed | 否 | 标准销售属性值id | `1` |
| `      └ measure_info` | body | object | 否 | 度量衡结构化信息，如单果规格的规格值10-13g，包含两个模块： {         "measure_info": {           "template_id": 50,           "values": [             {               "module_id": 44,               "prefix": "",               "suffix": "-",               "value": "10"             },             {               "module_id": 45,               "prefix": "",               "suffix": "",               "value": "13",               "unit_id": 2,               "unit_name": "g"             }           ]         } | `` |
| `        └ values` | body | array | 否 | 度量衡模块信息，如示例中13克为一个模块 | `` |
| `          └ value` | body | string | 否 | 值内容，如13 | `规格值` |
| `          └ unit_name` | body | string | 否 | 单位名称，如g | `"单位名称"` |
| `          └ unit_id` | body | mixed | 否 | 单位id | `"单位id"` |
| `          └ prefix` | body | string | 否 | 前缀，示例中为空 | `“标题前缀”` |
| `          └ suffix` | body | string | 否 | 后缀，如- | `“标题后缀”` |
| `          └ module_id` | body | mixed | 否 | 模块id | `1` |
| `        └ template_id` | body | mixed | 否 | 度量衡模版id，根据/getProductUpdateRule中回填 | `1` |
| `      └ value_name` | body | string | 是 | 规格值名称 | `"升高"` |
| `      └ remark` | body | string | 否 | 规格值备注信息，如偏大 | `“test"` |
| `with_sku_type` | body | boolean | 否 | true:主动设置库存类型（仅对区域库存生效，普通库存、阶梯库存不受此字段影响） | `true` |
| `name_suffix` | body | string | 否 | 通过/product/getRecommendName接口推荐的商品标题后缀（注意系统根据类目属性生成后缀字符串时，前面可能有一个空格） | `36.9度` |
| `use_brand_name` | body | boolean | 否 | 是否勾选使用品牌名, 注意勾选时需要接入/product/getRecommendName接口 | `false` |
| `open_logistics_info` | body | object | 否 | 跨境物流信息 | `` |
| `  └ origin_country_id` | body | mixed | 否 | 原产国id | `6251999` |
| `  └ net_weight_qty` | body | string | 否 | 商品净重 | `1` |
| `  └ cross_warehouse_id` | body | string | 否 | 商家仓id | `FOURPLTEST` |
| `  └ source_country_id` | body | mixed | 否 | 货源国id | `2963597` |
| `  └ tax_payer` | body | mixed | 否 | 税金承担方（一般都填0，走商家承担）：0商家承担，1用户承担 | `0` |
| `  └ customs_clear_type` | body | mixed | 否 | 通关模式，1：BBC 2：BC 3：CC邮关 | `1` |
| `  └ brand_country_id` | body | mixed | 否 | 品牌所在地id | `6251999` |
| `custom_property` | body | object | 否 | 商品定制属性。适用于到家商品场景 | `` |
| `  └ customPropertyGroups` | body | array | 否 | 商品定制属性组 | `` |
| `    └ name` | body | string | 否 | 商品定制属性组名称 | `加工服务` |
| `    └ propertyDetail` | body | array | 否 | 商品定制属性明细 | `` |
| `      └ extra_info` | body | object | 否 | 属性扩展信息 | `` |
| `        └ process_time` | body | mixed | 否 | 属性维度的处理时长，单位：秒，不能超过24小时。 | `60` |
| `      └ name` | body | string | 否 | 商品定制属性明细名称 | `处理` |
| `is_evaluate_opened` | body | boolean | 否 | 测评模块是否打开 | `false` |
| `default_process_time` | body | object | 否 | 商品维度默认处理时长 | `` |
| `  └ value` | body | mixed | 否 | 商品维度默认处理时长，单位：秒，不能超过24小时。 | `60` |
| `food_label_image_url` | body | string | 否 | 食品标签图 | `https://p3-aio.ecombdimg.com/ecom-shop-material/png_m_da821f77ec1a287fb2820969b50733c3_sx_655174_www1080-1080~tplv-qzsgku4lz6-fxg-image:0:q75.avis` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.product.editv2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 子商品{*}包含时效SKU，暂不支持组合（sub_code: isv.business-failed:110320008） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格名称超过64个字符,请修改后重试（sub_code: isv.business-failed:110220116） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品类型不能编辑（sub_code: isv.business-failed:110102110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 组合商品类目与子商品类目不一致（sub_code: isv.business-failed:110320125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 未命中商品名称前缀推荐规则，name_prefix字段应该置空（sub_code: isv.business-failed:110101149） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3282 |
| `50002` | 业务处理失败 / 该商品已封禁（sub_code: isv.business-failed:2010043） | 不允许编辑 |
| `50002` | 业务处理失败 / {*}不支持组套（sub_code: isv.business-failed:110101129） | 请检查入参信息 |
| `50002` | 业务处理失败 / 主品信息不合法（sub_code: isv.business-failed:110102118） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品必须设置规格：{*}（sub_code: isv.business-failed:110310112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 海南免税商品不可选择部分7天无理由类型（sub_code: isv.business-failed:110330118） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}属性填写不符合规范:标品管控要求：{*},实际填写：{*}（sub_code: isv.business-failed:110215103） | 请检查入参信息 |
| `40002` | 缺少必选参数 / 资质不合法（sub_code: isv.missing-parameter:2010101） | 请上传包装标签图 |
| `50002` | 业务处理失败 / 分销品备案信息有误，备案清关方式错误，请重新备案（sub_code: isv.business-failed:110260148） | 请检查入参信息 |
| `50002` | 业务处理失败 / 海南会员购模式只支持邮寄（sub_code: isv.business-failed:110270126） | 请检查入参信息 |
| `50002` | 业务处理失败 / 抖音极速版商家不支持商品分组功能（sub_code: isv.business-failed:110101043） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010326:因为店铺受到处置，限制发品，更多请到商家后台奖惩中心查看（sub_code: isv.business-failed:2010326） | 检查参数后重试 |
| `40004` | 非法的参数 / 使用的品牌没有授权（sub_code: isv.parameter-invalid:2010319） | 检查参数后重试 |
| `20000` | 系统错误 / 保存商品失败（sub_code: isp.service-error:2010012） | 重试 |
| `50002` | 业务处理失败 / 110320130:跨境主商品不能绑定下架的跨境子商品（sub_code: isv.business-failed:110320130） | - |
| `50002` | 业务处理失败 / 最晚发货时间不得早于下单时间（sub_code: isv.business-failed:110270154） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}仅支持在{*}编辑（sub_code: isv.business-failed:110102132） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品类型为虚拟商品，提取方式暂不支持使用物流模版（sub_code: isv.business-failed:110270006） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110270127:仅普通商品可以设置阶梯（sub_code: isv.business-failed:110270127） | - |
| `50002` | 业务处理失败 / 当前类目不支持非卖赠品（sub_code: isv.business-failed:110210018） | 请检查入参信息 |
| `50002` | 业务处理失败 / 非跨境商品不支持选择红屁屁无忧（sub_code: isv.business-failed:110330107） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}不支持混合库存（sub_code: isv.business-failed:110240111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 定制类商品必须选择[支持七天无理由，定制类不支持]（sub_code: isv.business-failed:110330119） | 请检查入参信息 |
| `50002` | 业务处理失败 / 券码信息禁止修改（sub_code: isv.business-failed:110270141） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您上传的商品主图存在重复，请核对后重新上传（sub_code: isv.business-failed:110250123） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3217 |
| `50002` | 业务处理失败 / 跨境商品不支持单个商品设置多个仓（sub_code: isv.business-failed:110240116） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010347:门店未绑定运费模板（sub_code: isv.business-failed:2010347） | 检查参数后重试 |
| `50002` | 业务处理失败 / SKU 商家仓不一致（sub_code: isv.business-failed:110260153） | 请检查入参信息 |
| `50002` | 业务处理失败 / 券码有效期需在2038年之前（sub_code: isv.business-failed:110270174） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU 清关方式不一致（sub_code: isv.business-failed:110260152） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}，不可修改库存类型（sub_code: isv.business-failed:110240107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无权限创建商家产品（sub_code: isv.business-failed:110101136） | 请检查入参信息 |
| `50002` | 业务处理失败 / 多个 cargoSku 绑定了同一个货品（sub_code: isv.business-failed:110260125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101178:MainProductId不允许修改（sub_code: isv.business-failed:110101178） | - |
| `50002` | 业务处理失败 / 2010109:当前类目未开通主图3：4上传功能，请删除主图3：4（sub_code: isv.business-failed:2010109） | 检查参数后重试 |
| `50002` | 业务处理失败 / {*}最多选择{*}项（sub_code: isv.business-failed:110215121） | 请检查入参信息 |
| `20000` | 系统错误 / 获取类目配置失败（sub_code: isp.service-error:2010202） | 重试 |
| `50002` | 业务处理失败 / 110280003:当前价格或商品起购件数不符合平台要求（sub_code: isv.business-failed:110280003） | 检查参数后重试 |
| `40004` | 非法的参数 / 必须支持7天无理由退货（sub_code: isv.parameter-invalid:2010316） | 检查参数后重试 |
| `50002` | 业务处理失败 / 商家未开通在线支付，无法上架在线支付商品（sub_code: isv.business-failed:110280002） | 请检查入参信息 |
| `50002` | 业务处理失败 / 非跨境商品不支持选择过敏无忧（sub_code: isv.business-failed:110330115） | 请检查入参信息 |
| `50002` | 业务处理失败 / 加工费超出范围，应为0到{*}元之间（sub_code: isv.business-failed:110310113） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您的无忧服务未开启，不可绑定云仓货品，请解绑货品或者开启服务（sub_code: isv.business-failed:110260019） | 请检查入参信息 |
| `50002` | 业务处理失败 / 前缀不匹配（sub_code: isv.business-failed:110101116） | 具体请参考https://op.jinritemai.com/docs/question-docs/92/2942 |
| `50002` | 业务处理失败 / 每次限购件数不能超过累计限购件数（sub_code: isv.business-failed:110280111） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU货品对应的仓信息缺失（sub_code: isv.business-failed:110260144） | 请检查入参信息 |
| `50002` | 业务处理失败 / 标品品牌[{*}]与品牌参数[{*}]不一致（sub_code: isv.business-failed:110215133） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品规格含有emoji等特殊字符,请修改后重试（sub_code: isv.business-failed:110220130） | 请检查入参信息 |
| `50002` | 业务处理失败 / 组合商品不同规格中子商品成分不能完全相同（sub_code: isv.business-failed:110320110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商家不支持 {*} 权益（sub_code: isv.business-failed:110330120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 权益code {*} 不支持（sub_code: isv.business-failed:110330122） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010055:因服务器升级，商品价格展示可能异常，请修改价格后重试（sub_code: isv.business-failed:2010055） | 检查参数后重试 |
| `60000` | 触发限流，请稍后重试 / 2010067:更新商品太频繁，操作失败请重试（sub_code: isp.traffic-limited:2010067） | 稍后重试 |
| `50002` | 业务处理失败 / 结构化标题-{*}长度不匹配（sub_code: isv.business-failed:110101118） | 请检查入参信息 |
| `50002` | 业务处理失败 / 需平台审核后方能上架（sub_code: isv.business-failed:110371017） | 请检查入参信息 |
| `50002` | 业务处理失败 / 类目不支持设置坏损包退（sub_code: isv.business-failed:110330106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求:[{*}]必填（sub_code: isv.business-failed:110220138） | 请检查入参信息 |
| `50002` | 业务处理失败 / 结构化标题规则长度不匹配（sub_code: isv.business-failed:110101122） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110107003:当前价格或商品起购件数不符合平台要求（sub_code: isv.business-failed:110107003） | 检查参数后重试 |
| `50002` | 业务处理失败 / 该商品类型暂不支持供货价字段（sub_code: isv.business-failed:110310108） | 请检查入参信息 |
| `50002` | 业务处理失败 / 运营类目权限校验失败（sub_code: isv.business-failed:110102112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110250126:您上传的商品主图存在重复，请核对后重新上传（sub_code: isv.business-failed:110250126） | 请检查入参 |
| `50002` | 业务处理失败 / 110330002:该类目不支持该类型售后7无标签（sub_code: isv.business-failed:110330002） | 检查参数后重试 |
| `50002` | 业务处理失败 / 仓类型与商品清关方式不匹配（sub_code: isv.business-failed:110240019） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101180:商品存在预定的下架时间, 暂不支持在预定下架时间到达前编辑, 预定下架时间: 2023-10-28 00:00:00（sub_code: isv.business-failed:110101180） | - |
| `50002` | 业务处理失败 / 结构化标题-{*}code不匹配（sub_code: isv.business-failed:110101119） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品当前状态暂不支持切组合商品（sub_code: isv.business-failed:110320118） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 {*} 成分含量不能小于 {*}（sub_code: isv.business-failed:110215129） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持Open操作{*}，请前往电脑端进行管理（sub_code: isv.business-failed:110102128） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该类目不支持该提取方式（sub_code: isv.business-failed:110270156） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}单位名称{*}或单位id{*}不合法（sub_code: isv.business-failed:110220145） | 请检查入参信息 |
| `40004` | 非法的参数 / 商品编辑失败：图片上传错误（sub_code: isv.parameter-invalid:99） | 建议接入素材中心 |
| `50002` | 业务处理失败 / 当前系统升级期间暂不允许修改计价金类目商品（sub_code: isv.business-failed:110310128） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101168:质检报告最多支持上传40张资质图片（sub_code: isv.business-failed:110101168） | - |
| `40002` | 缺少必选参数 / 缺少参数（sub_code: isv.missing-parameter:2010003） | 重新进入页面进行补充 |
| `50002` | 业务处理失败 / 无法修改运费模版（sub_code: isv.business-failed:110371003） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改库存类型（sub_code: isv.business-failed:110371021） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该类目价格范围为{*} - {*}元，请规范标价行为（sub_code: isv.business-failed:110310109） | 请检查入参信息 |
| `50002` | 业务处理失败 / 手机充值商品只支持单规格（sub_code: isv.business-failed:110220136） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前货品无法被绑定（sub_code: isv.business-failed:110260110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 阶梯发货商品不支持设置现货发货时间（sub_code: isv.business-failed:110270012） | 请检查入参信息 |
| `50002` | 业务处理失败 / 本类目不可选择「不支持退」（sub_code: isv.business-failed:110270148） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格{*}不支持填写备注（sub_code: isv.business-failed:110220140） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010015:该商品为竞拍商品，不支持变更（sub_code: isv.business-failed:2010015） | 检查参数后重试 |
| `50002` | 业务处理失败 / 商品操作重复（sub_code: isv.business-failed:2010021） | 请勿重复操作 |
| `50002` | 业务处理失败 / 结构化标题-{*}值不匹配（sub_code: isv.business-failed:110101120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010339:[存在审批中素材，请等待审批]（sub_code: isv.business-failed:2010339） | 请等待审批 |
| `50002` | 业务处理失败 / {*}只支持虚拟商品（sub_code: isv.business-failed:110101110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 请填写正确的使用次数（sub_code: isv.business-failed:110270164） | 请检查入参信息 |
| `40004` | 非法的参数 / 类目校验（sub_code: isv.parameter-invalid:2010044） | 请重新选择类目进行商品发布 |
| `50002` | 业务处理失败 / 当前接口不支持{*}创建（sub_code: isv.business-failed:110102125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格设置必须与面值、地区、运营商3个属性保持一致，请检查规格（sub_code: isv.business-failed:110220110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 教育闭环履约商品发布之后不能修改规格信息，如需修改请新建一个sku（sub_code: isv.business-failed:110220126） | 请检查入参信息 |
| `50002` | 业务处理失败 / 自领取之日起有效天数不可超过365天（sub_code: isv.business-failed:110270163） | 请检查入参信息 |
| `50002` | 业务处理失败 / sku数量和规格组合数不匹配，请重新选择规格（sub_code: isv.business-failed:110220113） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2516 |
| `50002` | 业务处理失败 / 2010999:系统错误，请重试（sub_code: isv.business-failed:2010999） | 检查参数后重试 |
| `50002` | 业务处理失败 / 无法修改发货时间（sub_code: isv.business-failed:110371009） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}单位{*}不合法（sub_code: isv.business-failed:110220146） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}，暂不支持修改商品类型（sub_code: isv.business-failed:110101176） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改发货方式和时间（sub_code: isv.business-failed:110371007） | 请检查入参信息 |
| `50002` | 业务处理失败 / 请填写SkuId商品编码（sub_code: isv.business-failed:110220122） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前类目商品必须设置今日金价（sub_code: isv.business-failed:110310126） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3689 |
| `50002` | 业务处理失败 / 短标题必须在{*}~{*}个字（sub_code: isv.business-failed:110101131） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改规格图（sub_code: isv.business-failed:110371020） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格名称不能重复，请核对（sub_code: isv.business-failed:110220157） | 请检查入参信息 |
| `50002` | 业务处理失败 / 暂不支持普通、虚拟商品类型之间的切换（sub_code: isv.business-failed:110101101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101162:不存在该叶子分类:7246678116486725888（sub_code: isv.business-failed:110101162） | - |
| `50002` | 业务处理失败 / 110014001:系统繁忙，请稍后再试（sub_code: isv.business-failed:110014001） | 检查参数后重试 |
| `50002` | 业务处理失败 / 110210021:该商品对应的类目已处于禁发状态，需先修改商品对应类目为合适类目（sub_code: isv.business-failed:110210021） | 请检查入参 |
| `50002` | 业务处理失败 / 110102009:商品存在预定的下架时间, 暂不支持在预定下架时间到达前编辑, 预定下架时间: 2023-05-29 12:00:00（sub_code: isv.business-failed:110102009） | 检查参数后重试 |
| `50002` | 业务处理失败 / sku重量信息必填（sub_code: isv.business-failed:110270019） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110220014:当前类目/店铺不支持SKU分类信息填写（sub_code: isv.business-failed:110220014） | 检查参数后重试 |
| `50002` | 业务处理失败 / 自动充值商品对应的提取方式必须是充值直连（sub_code: isv.business-failed:110280105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品起售件数不能超过累计限购件数（sub_code: isv.business-failed:110280112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110220017:规格「尺码」对应的规格值「XXXXXXXXXS码」含有连续相同字母，请修改后重试；（sub_code: isv.business-failed:110220017） | - |
| `50002` | 业务处理失败 / 最多支持{*}组商品规格（sub_code: isv.business-failed:110220118） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该商品在审核中（sub_code: isv.business-failed:2010041） | 不允许编辑 |
| `50002` | 业务处理失败 / SKU 货源地不一致（sub_code: isv.business-failed:110260123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 手机充值卡业务类目属性合法性校验不通过，地区、面值、运营商有固定的选择范围（sub_code: isv.business-failed:110215107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前店铺不支持设置基础金价（sub_code: isv.business-failed:110310130） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}暂不支持切组合商品（sub_code: isv.business-failed:110320105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 核销商品必须为虚拟商品（sub_code: isv.business-failed:110270160） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性值重复（sub_code: isv.business-failed:110215120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 设置区域库存时，普通库存数须为0（sub_code: isv.business-failed:110240106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品从现货+预售模式切换，请移除发货时效规（sub_code: isv.business-failed:110220132） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该类目的商品暂不支持货到付款支付方式（sub_code: isv.business-failed:110280009） | 请检查入参信息 |
| `50002` | 业务处理失败 / 货品销售信息为空（sub_code: isv.business-failed:110102113） | 请检查入参信息 |
| `50002` | 业务处理失败 / 时效规格须按照时间排序（sub_code: isv.business-failed:110220133） | 请检查入参信息 |
| `50002` | 业务处理失败 / 创建改价任务失败，请一定重试（sub_code: isv.business-failed:110310131） | 请检查入参信息 |
| `50002` | 业务处理失败 / 基础金价设置不正确（sub_code: isv.business-failed:110310129） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110280024:每次至少购买数不能超过10（sub_code: isv.business-failed:110280024） | 请检查入参 |
| `50002` | 业务处理失败 / 不允许修改延迟发货规则（sub_code: isv.business-failed:110371023） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010061:请求权益信息失败（sub_code: isv.business-failed:2010061） | 稍后重试 |
| `50002` | 业务处理失败 / 商品参加活动中无法更改绑定关系（sub_code: isv.business-failed:110260106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 限购值最大可设置{*}（sub_code: isv.business-failed:110280114） | 请检查入参信息 |
| `40004` | 非法的参数 / 商品正在参加活动（sub_code: isv.parameter-invalid:2010045） | 暂不支持修改规格 |
| `50002` | 业务处理失败 / 当前类目限制发虚拟商品（sub_code: isv.business-failed:110101152） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您未订购无忧服务，商品不可启用无忧服务（sub_code: isv.business-failed:110101142） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}不支持修改提货方式（sub_code: isv.business-failed:110270162） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}时效规格不存在（sub_code: isv.business-failed:110220101） | 当前商品的发货模式需要传时效规格，请检查参数spec_info中是否存在时效规格 |
| `50002` | 业务处理失败 / 封禁状态不支持上架（sub_code: isv.business-failed:110101188） | 请检查入参信息 |
| `50002` | 业务处理失败 / 退改规则不可更改（sub_code: isv.business-failed:110270118） | 请检查入参信息 |
| `40004` | 非法的参数 / 库存错误（sub_code: isv.parameter-invalid:-20008） | 可到营销中心修改对应的营销活动库存，或直接修改当前商品现货库存数 |
| `50002` | 业务处理失败 / 分销商品不允许作为组套子商品（sub_code: isv.business-failed:110320104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110207001:不存在该尺码模板,请重新创建尺码模板（sub_code: isv.business-failed:110207001） | 请检查入参 |
| `50002` | 业务处理失败 / 2010341:阶梯库存模式不合法（sub_code: isv.business-failed:2010341） | 检查参数后重试 |
| `50002` | 业务处理失败 / 110101145:“商品标题”不可含有Tab符（sub_code: isv.business-failed:110101145） | - |
| `50002` | 业务处理失败 / 承诺发货时间不在合理范围内（sub_code: isv.business-failed:110270149） | 具体参考https://op.jinritemai.com/docs/question-docs/92/1680 |
| `50002` | 业务处理失败 / 组套子商品不允许修改货品类型（sub_code: isv.business-failed:110260103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 退货策略权限错误（sub_code: isv.business-failed:110216002） | 请检查入参信息 |
| `50002` | 业务处理失败 / 存在规格未绑定货品，不可启用无忧服务（sub_code: isv.business-failed:110260139） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格{*}样式已调整,请刷新页面重新填写（sub_code: isv.business-failed:110220143） | 请检查入参信息 |
| `50002` | 业务处理失败 / 分销品备案信息有误，备案原产国为空，请重新备案（sub_code: isv.business-failed:110260150） | 请检查入参信息 |
| `50002` | 业务处理失败 / 尺码表需包含所有规格中的尺码，请补充尺码（sub_code: isv.business-failed:110250121） | 请检查尺码模版中选择的尺码值selectedSize需要包含商品对应尺码规格所选的所有规格值，例如商品规格尺码大小有xl、xxl，那么尺码模版selectedSize也需要包含xl、xxl |
| `50002` | 业务处理失败 / 无法下架商品（sub_code: isv.business-failed:110371013） | 请检查入参信息 |
| `50002` | 业务处理失败 / 仓无效（sub_code: isv.business-failed:110240018） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该类目需要基于标品发布商品，根据关键属性在该类目未找到标品，请先新建标品或调整类目。（sub_code: isv.business-failed:110215110） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3075 |
| `50002` | 业务处理失败 / 无法删除商品（sub_code: isv.business-failed:110371018） | 请检查入参信息 |
| `50002` | 业务处理失败 / 子商品:{*},已关联{*}个商品（sub_code: isv.business-failed:110320112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 单张规格图大小≤5M内（sub_code: isv.business-failed:110220114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 延迟发货时间点不合法（sub_code: isv.business-failed:110270150） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品状态错误（sub_code: isv.business-failed:2010022） | 检查状态后重试 |
| `50002` | 业务处理失败 / 暂不支持发布计价金类目商品（sub_code: isv.business-failed:110102106） | 请检查入参信息 |
| `20000` | 系统错误（sub_code: isp.service-error:2010001） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 门店当前状态不允许发品（sub_code: isv.business-failed:110101030） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110320115:暂不支持开放平台切组合商品（sub_code: isv.business-failed:110320115） | - |
| `50002` | 业务处理失败 / 110250103:该类目商品需上传完整尺码表信息，目前缺失规格：身高，请补充！<a href='https://school.jinritemai.YOUR_SECRET_KEY' target='_blank'>规则介绍</a>（sub_code: isv.business-failed:110250103） | - |
| `50002` | 业务处理失败 / 参考价需大于等于最高售卖价且小于最高售卖价{*}倍（sub_code: isv.business-failed:110310107） | 请检查参考价参数reference_price和sku价格参数spec_price.price，具体请参考https://op.jinritemai.com/docs/question-docs/92/3299 |
| `50002` | 业务处理失败 / 当前商家不支持第三方发券方式（sub_code: isv.business-failed:110270107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 跨境商品请选择区域库存（sub_code: isv.business-failed:110240113） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215109:类目属性错误，原类目属性不存在（sub_code: isv.business-failed:110215109） | - |
| `50002` | 业务处理失败 / 属性值“{*}”不在“{*}”的最新可选范围，请删除后重新选择（sub_code: isv.business-failed:110215105） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2649 |
| `50002` | 业务处理失败 / 奖品供货价格必须在0.01￥到50000.00￥之间（sub_code: isv.business-failed:110310121） | 请检查入参信息 |
| `20000` | 系统错误 / 查询商家资质失败（sub_code: isp.service-error:2010207） | 查询商家资质失败，请重试 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}信息缺失,请刷新页面重新填写（sub_code: isv.business-failed:110220144） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU 请选择正确的计量单位（sub_code: isv.business-failed:110260121） | 请检查入参信息 |
| `50002` | 业务处理失败 / 运营没有配置类目权限，暂不允许操作（sub_code: isv.business-failed:110102103） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU 供应商不一致（sub_code: isv.business-failed:110260120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215010:类目属性「货号」存在属性值「423265757jhjyuuuuuuuuuu」含有连续相同字母，请修改后重试；（sub_code: isv.business-failed:110215010） | 请检查入参 |
| `50002` | 业务处理失败 / 非拍卖店铺，商品类型不合法（sub_code: isv.business-failed:110101117） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持部分修改{*}（sub_code: isv.business-failed:110102122） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215012:类目属性「型号」长度过长，请修改后重试；（sub_code: isv.business-failed:110215012） | 请检查入参 |
| `50002` | 业务处理失败 / 无法修改规格价格（sub_code: isv.business-failed:110371002） | 请检查入参信息 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:4） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 分销品备案信息有误，备案货源地为空，请重新备案（sub_code: isv.business-failed:110260151） | 请检查入参信息 |
| `50002` | 业务处理失败 / 前缀匹配失败，当前未能自动填充，请商家至抖店PC端/APP端后台编辑商品标题前缀（sub_code: isv.business-failed:110101111） | - |
| `50002` | 业务处理失败 / 商品正在参加活动，请先取消再进行转换。活动名称: {*}（sub_code: isv.business-failed:110320119） | 请检查入参信息 |
| `50002` | 业务处理失败 / 阶梯库存数量不能小于0（sub_code: isv.business-failed:110240104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110280019:当前类目每次至少购买数最多只能设置为1，请同时关注最小购买数变化对sku价格的影响（sub_code: isv.business-failed:110280019） | 请检查入参 |
| `50002` | 业务处理失败 / 组套子商品（{*}）为一段奶粉商品，主商品类目必须为一段奶粉（sub_code: isv.business-failed:110320106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 重量数值支持范围：0.0001 ~ 9999.999，请重新设置（sub_code: isv.business-failed:110270168） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110111009:[商品存在预定的下架时间, 暂不支持在预定下架时间到达前编辑, 预定下架时间: 2023-03-01 19:59:59]（sub_code: isv.business-failed:110111009） | 请等待下架时间 |
| `50002` | 业务处理失败 / 门店库门店数量为0（sub_code: isv.business-failed:110270111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 至少保证一个组合套餐中的子商品数量大于等于2，请返回修改。（sub_code: isv.business-failed:110320111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 请勿使用外部图片，请使用素材中心（sub_code: isv.business-failed:110207004） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2365 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}必须填写小数（sub_code: isv.business-failed:110220149） | 请检查入参信息 |
| `50002` | 业务处理失败 / 售卖价需在商品规格最低价{*}和最高价{*}范围内（sub_code: isv.business-failed:110310116） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品审核中，不可更新（sub_code: isv.business-failed:110102002） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3274 |
| `50002` | 业务处理失败 / 无法修改商品描述（sub_code: isv.business-failed:110371012） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品价格小于{*}元，无法使用预售交易；请调整发货模式或重新设置SKU价格（sub_code: isv.business-failed:110310105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改商品标题（sub_code: isv.business-failed:110371011） | 请检查入参信息 |
| `50002` | 业务处理失败 / 业务身份与清关方式不一致（sub_code: isv.business-failed:110270172） | 请检查入参信息 |
| `50002` | 业务处理失败 / 条形码不合法（sub_code: isv.business-failed:110220121） | 请检查入参信息 |
| `50002` | 业务处理失败 / 物流信息类型不合法（sub_code: isv.business-failed:110270136） | 请检查参数delivery_infos. info_type，目前只支持info_type="weight" |
| `50002` | 业务处理失败 / 非竞拍店铺，商品类型不合法（sub_code: isv.business-failed:110101140） | 请检查入参信息 |
| `50002` | 业务处理失败 / 绑定了货品的商品不支持OPEN编辑（sub_code: isv.business-failed:110260138） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3677 |
| `50002` | 业务处理失败 / 本类目不支持选择红屁屁无忧服务（sub_code: isv.business-failed:110330108） | 请检查入参信息 |
| `50002` | 业务处理失败 / 『{*}』商品暂不支持切组合商品（sub_code: isv.business-failed:110320121） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持混合库存商品，请检查sku库存类型（sub_code: isv.business-failed:110240118） | 请检查入参 |
| `50002` | 业务处理失败 / 标称金重过大，范围在0.01到{*}之间（sub_code: isv.business-failed:110310102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求:支持填写[{*}],实际填写[{*}]（sub_code: isv.business-failed:110220137） | 规格项需要符合sku标准化限制，请检查规格参数，可以根据/product/getProductUpdateRule中product_spec_rule获取当前类目的规格限制，product_spec_rule. required_spec_details则为必选的规格 |
| `50002` | 业务处理失败 / 券码可使用次数大于1时，每单限购1件（sub_code: isv.business-failed:110270108） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改商品信息（sub_code: isv.business-failed:110371016） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}只支持普通商品（sub_code: isv.business-failed:110101109） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101049:前缀不匹配（sub_code: isv.business-failed:110101049） | 检查参数后重试 |
| `40002` | 缺少必选参数 / 缺少属性（sub_code: isv.missing-parameter:2010321） | 检查参数后重试 |
| `50002` | 业务处理失败 / 当前商品仅支持在百应后台编辑（sub_code: isv.business-failed:110102129） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU 原产地不一致（sub_code: isv.business-failed:110260122） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}仅支持在线支付（sub_code: isv.business-failed:110280101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 图片长宽比非1:1（sub_code: isv.business-failed:110250127） | 具体参考https://op.jinritemai.com/docs/question-docs/92/1682 |
| `50002` | 业务处理失败 / 请填写物流信息（sub_code: isv.business-failed:110270133） | 请检查入参信息 |
| `50002` | 业务处理失败 / 定金找货价格必须是整数（sub_code: isv.business-failed:110310014） | 请检查入参信息 |
| `50002` | 业务处理失败 / 参数错误，请选择正确的[商品类型]类目属性（sub_code: isv.business-failed:110101153） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110250122:请上传1~5张商品主图（sub_code: isv.business-failed:110250122） | 请检查入参 |
| `50002` | 业务处理失败 / 主商品是区域库存时，子商品不能是非区域库存商品（sub_code: isv.business-failed:110240108） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU数量超过{*}上限，请删除任意规格属性项后添加（sub_code: isv.business-failed:110220112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法直接通过该接口创建或编辑{*}（sub_code: isv.business-failed:110102120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前类型商品，暂不支持修改类目（sub_code: isv.business-failed:110210103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您关联的货品不是云仓自流转发货货品，请联系客服排查（sub_code: isv.business-failed:110260141） | 请检查入参信息 |
| `50002` | 业务处理失败 / 苹果门店只支持区域库存（sub_code: isv.business-failed:110240020） | 请检查入参信息 |
| `50002` | 业务处理失败 / 卡券有效期范围限制（sub_code: isv.business-failed:110270170） | 请检查入参信息 |
| `50002` | 业务处理失败 / 教育闭环履约商品，必须绑定关联课程，填写库存，不能使用默认规格（sub_code: isv.business-failed:110220003） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215002:类目属性[?️]中含有emoji等特殊字符，请检查后重试（sub_code: isv.business-failed:110215002） | 检查参数后重试 |
| `50002` | 业务处理失败 / 设置商品库存，现货库存数必须大于阶梯库存数，请修改（sub_code: isv.business-failed:110240105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110270145:商品正在参加平台活动，不可修改为全款预售模式（sub_code: isv.business-failed:110270145） | - |
| `50002` | 业务处理失败 / {*}不能有库存（sub_code: isv.business-failed:110240101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,[{*}]中[{*}]中已有同义的规格值，为避免消费者误解，请选择库内已有值（sub_code: isv.business-failed:110220106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 子商品{*}配置在『切组合商品』白名单中，不允许配置为子商品（sub_code: isv.business-failed:110320135） | 请检查入参信息 |
| `50002` | 业务处理失败 / 退货策略不存在（sub_code: isv.business-failed:110216001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 前置质检单库存模式:仅支持普通库存（sub_code: isv.business-failed:110240112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 奖品商品售卖价必须为0元（sub_code: isv.business-failed:110310103） | 请检查入参信息 |
| `40004` | 非法的参数 / 品牌不合法（sub_code: isv.parameter-invalid:2010104） | 检查参数后重试 |
| `50002` | 业务处理失败 / 货品已经关联sku信息({*})，不能重复关联（sub_code: isv.business-failed:110260116） | 请检查入参信息 |
| `50002` | 业务处理失败 / 店铺或类目不支持分账（sub_code: isv.business-failed:110270005） | 请检查入参信息 |
| `50002` | 业务处理失败 / open侧暂不允许设置{*}（sub_code: isv.business-failed:110102123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 奖品商品仅支持下单减库存（sub_code: isv.business-failed:110280109） | 请检查入参信息 |
| `50002` | 业务处理失败 / 货品销售信息已被推送为MPU，不允许编辑（sub_code: isv.business-failed:110102114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110260002:您为榴莲定向分销商，必须通过分销平台采购榴莲货源，请绑定分销货品（sub_code: isv.business-failed:110260002） | 检查参数后重试 |
| `50002` | 业务处理失败 / 本类目必须选择过敏无忧服务（sub_code: isv.business-failed:110330116） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}只能来自营销侧发布（sub_code: isv.business-failed:110102130） | 请检查入参信息 |
| `50002` | 业务处理失败 / 自动充值商品不允许修改为非自动充值商品（sub_code: isv.business-failed:110280102） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}仅支持虚拟、普通商品（sub_code: isv.business-failed:110101103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 每个类目有对应所支持的尺码模版子类型，当前尺码模板子类型不支持当前类目（sub_code: isv.business-failed:110250118） | 尺码模板子类型template_sub_type有[clothing(服装)、undies(内衣)、shoes(鞋靴类)、children_clothing(童装)]，可以根据接口/product/getProductUpdateRule	 中返回的component_template_rule .support_template_sub_type获取当前类目的模版子类型 |
| `50002` | 业务处理失败 / 品牌与货品不一致，请选择货品关联的品牌:{*}（sub_code: isv.business-failed:110260115） | 请检查入参信息 |
| `50002` | 业务处理失败 / 主商品{*}，不允许绑定子商品（sub_code: isv.business-failed:110102119） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品价格必选含税（sub_code: isv.business-failed:110280116） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}中{*}数值须不高/低于:{*}（sub_code: isv.business-failed:110220151） | 请检查入参信息 |
| `20000` | 系统错误 / 获取类目信息失败（sub_code: isp.service-error:2010201） | 重试 |
| `50002` | 业务处理失败 / 当前商品因为设置了商品维度的活动库存，暂不支持创建渠道商品。（sub_code: isv.business-failed:110240021） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,允许填写:[{*}],实际填写:[{*}]（sub_code: isv.business-failed:110220139） | 请检查入参信息 |
| `50002` | 业务处理失败 / 券码生成方式和可核销次数禁止修改（sub_code: isv.business-failed:110270115） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求:第一层规格要求填写[{*}]（sub_code: isv.business-failed:110220142） | 请检查入参信息 |
| `50002` | 业务处理失败 / 奖品不支持阶梯库存（sub_code: isv.business-failed:110240015） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*} measure_info字段为空或不合法（sub_code: isv.business-failed:110220161） | 请检查参数spec_info.spec_values values.measure_info是否有传正确的值 |
| `50002` | 业务处理失败 / 类目属性为空，请检查（sub_code: isv.business-failed:110215117） | 请检查入参信息 |
| `50002` | 业务处理失败 / 奖品参考价必须在3.00￥到50000.00￥之间（sub_code: isv.business-failed:110310104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 一个条形码({*})不应该对应两个商家编码({*})({*})（sub_code: isv.business-failed:110220111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改sku信息（sub_code: isv.business-failed:110371024） | 请检查入参信息 |
| `50002` | 业务处理失败 / 封禁状态不支持下架（sub_code: isv.business-failed:110101189） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格值不能超过{*}个（sub_code: isv.business-failed:110220119） | 请检查入参信息 |
| `50002` | 业务处理失败 / 分销品备案信息有误，备案服务商仓为空，请重新备案（sub_code: isv.business-failed:110260149） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}不支持自动充值（sub_code: isv.business-failed:110280104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 过时更新，无需再同步（sub_code: isv.business-failed:110101102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2147483647:存在审批中素材，请等待审批（sub_code: isv.business-failed:2147483647） | 稍后重试 |
| `50002` | 业务处理失败 / 子商品{*}是{*}，不支持组合商品（sub_code: isv.business-failed:110320107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 主商品信息不能为空（sub_code: isv.business-failed:110101174） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性“{*}”不在当前类目的最新可选范围，请删除后重新选择（sub_code: isv.business-failed:110215122） | 请检查入参信息 |
| `40004` | 非法的参数 / 业务处理失败（sub_code: isv.parameter-invalid:7） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 海关申报要素：品名、规格型号、用途等不可含有#号符（sub_code: isv.business-failed:110260107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110310010:当前商品正在参与活动 抖音618好物节商品报名，商品sku价格不得低于活动到手价格￥120.00元，请修改后重新提交。（sub_code: isv.business-failed:110310010） | 检查参数后重试 |
| `20000` | 系统错误 / 加载信息失败（sub_code: isp.service-error:20011） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 组套商品Sku其子商品货品类型必须一致（sub_code: isv.business-failed:110320134） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}仅支持包邮（sub_code: isv.business-failed:110270121） | 请检查入参信息 |
| `50002` | 业务处理失败 / 酒类商品净含量必填且必须大于 0(sku code = {*})（sub_code: isv.business-failed:110220120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 跨境商品不可选择部分7天无理由类型（sub_code: isv.business-failed:110330117） | 请检查入参信息 |
| `50002` | 业务处理失败 / 请填写重量（sub_code: isv.business-failed:110270166） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3943 |
| `50002` | 业务处理失败 / {*}只能使用一次（sub_code: isv.business-failed:110270165） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010203:获取商品信息失败（sub_code: isv.business-failed:2010203） | 检查参数后重试 |
| `50002` | 业务处理失败 / 类目不支持大件商品（sub_code: isv.business-failed:110330109） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110270138:仅普通商品可以设置预售（sub_code: isv.business-failed:110270138） | - |
| `50002` | 业务处理失败 / 本类目不支持选择过敏无忧服务（sub_code: isv.business-failed:110330114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改售卖渠道（sub_code: isv.business-failed:110371010） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改商品白底图（sub_code: isv.business-failed:110371014） | 请检查入参信息 |
| `50002` | 业务处理失败 / AppSource异常（sub_code: isv.business-failed:110102131） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前类目或者商家不支持设置自动充值（sub_code: isv.business-failed:110280103） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}属性未填写（sub_code: isv.business-failed:110215124） | 请检查入参信息 |
| `50002` | 业务处理失败 / 券码生成方式和可核销次数禁止修改（sub_code: isv.business-failed:110270114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品属性值存在无效或不合理内容，请正确填写（sub_code: isv.business-failed:110370101） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3216 |
| `50002` | 业务处理失败 / 为了提高商品转化，划线价需高于商品规格最高价{*}（sub_code: isv.business-failed:110310117） | 请检查入参信息 |
| `50002` | 业务处理失败 / 暂不支持该发货模式（sub_code: isv.business-failed:110270180） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2984 |
| `50002` | 业务处理失败 / 该类目必须为虚拟商品（sub_code: isv.business-failed:110101108） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110250128:主图3：4比例要求3:4（sub_code: isv.business-failed:110250128） | 请检查入参 |
| `50002` | 业务处理失败 / 110101164:奖品已绑定活动，名称和类目禁止编辑（sub_code: isv.business-failed:110101164） | - |
| `50002` | 业务处理失败 / 2010352:商品存在预定的下架时间, 暂不支持在预定下架时间到达前编辑, 预定下架时间: 2023-01-04 23:59:59（sub_code: isv.business-failed:2010352） | 检查参数后重试 |
| `50002` | 业务处理失败 / 规格「*」对应的规格值存在非法字符，请修改后重试；（sub_code: isv.business-failed:110220019） | 请检查入参 |
| `50002` | 业务处理失败 / 预售发货信息校验未通过（sub_code: isv.business-failed:110270152） | 请检查入参信息 |
| `50002` | 业务处理失败 / 非卖品只能通过营销中心操作（sub_code: isv.business-failed:110102115） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}必须填写{*}位小数数值（sub_code: isv.business-failed:110220150） | 请检查入参信息 |
| `50002` | 业务处理失败 / 绑定货品参数错误: 一个商品只可绑定一种类型货品（sub_code: isv.business-failed:110260007） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格值的备注:{*} 长度不能大于{*},请修改后重试（sub_code: isv.business-failed:110220153） | 请检查入参信息 |
| `50002` | 业务处理失败 / 子商品不能是组合商品本身（sub_code: isv.business-failed:110320136） | 请检查入参信息 |
| `50002` | 业务处理失败 / 勾选套装后，套装数量不能为空且数值需大于 0(sku code = {*})（sub_code: isv.business-failed:110220107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该商家只能创建商家产品（sub_code: isv.business-failed:110101134） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110250124:第1张版权页图中包含非法链接地址（如外部跳转链接、从外部直接复制过来的图片链接等），请修改（sub_code: isv.business-failed:110250124） | - |
| `50002` | 业务处理失败 / 无忧组合商品的子品必须都是无忧商品（sub_code: isv.business-failed:110260020） | 请检查入参信息 |
| `50002` | 业务处理失败 / 请填写提货方式（sub_code: isv.business-failed:110270169） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}的网页url最多{*}个字符（sub_code: isv.business-failed:110290105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 最多支持上传{*}张{*}图片（sub_code: isv.business-failed:110290102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品默认支持坏损包退（sub_code: isv.business-failed:110330104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010058:商品不存在（sub_code: isv.business-failed:2010058） | 检查参数后重试 |
| `50002` | 业务处理失败 / {*}仅允许创建一个SKU，请设置单个SKU（sub_code: isv.business-failed:110220105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010107:当前价格或商品起购件数不符合平台要求（sub_code: isv.business-failed:2010107） | 检查参数后重试 |
| `50002` | 业务处理失败 / 子商品{*}的sku状态不可用（sub_code: isv.business-failed:110320117） | 请检查入参信息 |
| `50002` | 业务处理失败 / 延迟发货时间配置不符合平台规则（sub_code: isv.business-failed:110270106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 存在sku未绑定货品（sub_code: isv.business-failed:110260101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 时效SKU预售模式末级规格须为时效规格（sub_code: isv.business-failed:110220135） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您绑定的货品id：{*}未质检通过，不可启用无忧服务（sub_code: isv.business-failed:110260140） | 请检查入参信息 |
| `50002` | 业务处理失败 / 定制类商品，只能在对应的店铺以及类目下发品（sub_code: isv.business-failed:110101156） | 请参考当前商品发布规则:https://op.jinritemai.com/docs/api-docs/14/1614 判断是否支持创建定制类商品 |
| `50002` | 业务处理失败 / 110215106:属性 标称金重(约) 填写与计量单位信息不匹配，属性值填写范围[0.2g-1000g]（sub_code: isv.business-failed:110215106） | 请检查入参 |
| `50002` | 业务处理失败 / 教育闭环履约商品只支持无需物流配送及电子交易凭证（sub_code: isv.business-failed:110270155） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101146:“短标题”不可含有Tab符（sub_code: isv.business-failed:110101146） | - |
| `50002` | 业务处理失败 / 手机充值商品规格和类目属性必须一一对应（sub_code: isv.business-failed:110220103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格图片和规格值数量不匹配（sub_code: isv.business-failed:110220129） | 请检查参数spec_pic中图片的数量和spec_info中第一层规格项的值数量是否一致，具体参考https://op.jinritemai.com/docs/question-docs/92/2198 |
| `50002` | 业务处理失败 / 奥莱商家必须设置参考价与凭证，且凭证类型为吊牌价（sub_code: isv.business-failed:110310125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持该支付方式（sub_code: isv.business-failed:110280106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 门店id没有认领过不允许导入（sub_code: isv.business-failed:110270029） | 请检查入参信息 |
| `50002` | 业务处理失败 / 门店暂未开通财经帐号，无法添加至分账门店库（sub_code: isv.business-failed:110270030） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101151:“推荐语”不可含有emoji表情等特殊符号（sub_code: isv.business-failed:110101151） | - |
| `50002` | 业务处理失败 / 价格不匹配，请等正在运行的改价任务结束后再次尝试改价（sub_code: isv.business-failed:110310106） | 请检查入参信息 |
| `50002` | 业务处理失败 / 非拍卖店铺，商品类型不合法（sub_code: isv.business-failed:110101144） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215009:类目属性注册证号仅包含特殊字符，请修改并输入有效信息；（sub_code: isv.business-failed:110215009） | 请检查入参 |
| `50002` | 业务处理失败 / 素材中心url不合法（sub_code: isv.business-failed:110207008） | 具体参考https://op.jinritemai.com/docs/question-docs/92/1716 |
| `50002` | 业务处理失败 / 非竞拍店铺，商品类型不合法（sub_code: isv.business-failed:110101148） | 请检查入参信息 |
| `40004` | 非法的参数 / 发布诊断失败（sub_code: isv.parameter-invalid:2010501） | 检查参数后重试 |
| `40004` | 非法的参数 / 资质类属性必填拒绝（sub_code: isv.parameter-invalid:2010020） | 重新输入正确编号 |
| `50002` | 业务处理失败 / 本类目不支持选择过敏包退服务（sub_code: isv.business-failed:110330111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品已配置预约发货，暂不支持配置延迟发货（sub_code: isv.business-failed:110270153） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该店铺只支持云仓模式（sub_code: isv.business-failed:110260011） | 请检查入参信息 |
| `50002` | 业务处理失败 / 非货品销售信息无法修改成货品销售信息（sub_code: isv.business-failed:110101138） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品类型为实物商品，提取方式需使用物流模版（sub_code: isv.business-failed:110270157） | 请检查入参信息 |
| `50002` | 业务处理失败 / APP端暂不支持参考价，请前往电脑端进行操作（sub_code: isv.business-failed:110310124） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改商品主图（sub_code: isv.business-failed:110371015） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格项顺序不符合要求[{*}]（sub_code: isv.business-failed:110220141） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该售卖终端不支持（sub_code: isv.business-failed:110280115） | 请检查入参信息 |
| `50002` | 业务处理失败 / 类目组合关系错误（sub_code: isv.business-failed:110320116） | 请检查入参信息 |
| `50002` | 业务处理失败 / 渠道商品处于上架状态，下架后才可删除（sub_code: isv.business-failed:110101190） | 请检查入参信息 |
| `50002` | 业务处理失败 / 标品管控:类目属性参数必填（sub_code: isv.business-failed:110215123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品正在参加平台活动，暂不支持切组合商品（sub_code: isv.business-failed:110371102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 合作商品不支持指定店铺（sub_code: isv.business-failed:110270109） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010310:不存在该规格信息（sub_code: isv.business-failed:2010310） | 检查参数后重试 |
| `50002` | 业务处理失败 / 无法修改库存类型（sub_code: isv.business-failed:110371005） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110260016:该商品未绑定备案（sub_code: isv.business-failed:110260016） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010063:当前店铺在架商品量已达上限，暂无法创建商品，详细规则可查看商品数限额实施细则（sub_code: isv.business-failed:2010063） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010053:所选类目经营资质已失效，您可以选择保存草稿，待资质审核通过后再提交（sub_code: isv.business-failed:2010053） | 检查参数后重试 |
| `50002` | 业务处理失败 / 110270123:跨境商品不允许切换发货模式（sub_code: isv.business-failed:110270123） | - |
| `50002` | 业务处理失败 / 该商品正在参加搭配，请前往<a href='{*}' target='_blank'>搭配页</a>删除数据后，再进行组套切换，搭配ID：{*}（sub_code: isv.business-failed:110320120） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前类目商品不支持设置今日金价（sub_code: isv.business-failed:110310127） | 请检查入参信息 |
| `50002` | 业务处理失败 / 组套商品Sku其子商品不支持部分为货品（sub_code: isv.business-failed:110320101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 本类目必须选择过敏包退服务（sub_code: isv.business-failed:110330113） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改物流信息（sub_code: isv.business-failed:110371006） | 请检查入参信息 |
| `50002` | 业务处理失败 / 供销商品已停用（sub_code: isv.business-failed:110101001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 存在可售库存不为0的商品（删除草稿可查看实时库存），请到货品库存页手动调拨为0后再试（sub_code: isv.business-failed:110240017） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前类目不支持定金找货（sub_code: isv.business-failed:110280110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您未开启无忧服务，组套子商品中存在云仓发货商品id：{*}，请修改子商品或开启服务（sub_code: isv.business-failed:110260142） | 请检查入参信息 |
| `50002` | 业务处理失败 / 组合商品发货模式、发货时间必须与所有子品一致（sub_code: isv.business-failed:110320123） | 请检查入参信息 |
| `50002` | 业务处理失败 / cargoSku 货品信息缺失（sub_code: isv.business-failed:110260145） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持创建实物(需要物流)商品（sub_code: isv.business-failed:110270159） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前类目不支持奖品（sub_code: isv.business-failed:110210016） | 请检查入参信息 |
| `50002` | 业务处理失败 / 预售商品不支持设置发货时间（sub_code: isv.business-failed:110270009） | 请检查入参信息 |
| `50002` | 业务处理失败 / 定制类商品发货时间仅支持48小时以上（sub_code: isv.business-failed:110270128） | 请检查入参信息 |
| `50002` | 业务处理失败 / 根据属性的valueId从属性库查到了属性值，但是查到的属性值名和传入的属性值名不匹配（sub_code: isv.business-failed:110215119） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}必须填写整数（sub_code: isv.business-failed:110220148） | 请检查入参信息 |
| `50002` | 业务处理失败 / 货品价格必须大于0，请先设置货品价格（sub_code: isv.business-failed:110310013） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该参考价凭证类型不支持（sub_code: isv.business-failed:110310120） | 可以根据/product/getProductUpdateRule接口中返回的reference_price_rule获取当前类目可以选的参考价凭证类型 |
| `50002` | 业务处理失败 / {*}对应的规格值不能重复，请核对（sub_code: isv.business-failed:110220156） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110270117:该商品已报名限时特卖，不可修改预售信息（sub_code: isv.business-failed:110270117） | 请检查入参 |
| `50002` | 业务处理失败 / 重量支持范围：0.000001kg ~ 9999.999999kg，请重新设置（sub_code: isv.business-failed:110270167） | 请检查入参信息 |
| `50002` | 业务处理失败 / 券码信息禁止修改（sub_code: isv.business-failed:110270140） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前计算得出的价格过高，暂时不支持（sub_code: isv.business-failed:110310114） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}不能设置多级规格（sub_code: isv.business-failed:110220102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改规格信息（sub_code: isv.business-failed:110371001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110200024:发布当前类目商品，还需缴纳20.00元保证金，点击“<a href='/ffa/content/shop_deposit' target="_blank">立即充值</a>”补全对应保证金后方可发布商品，详见<a href='https://school.jinritemai.com/doudian/web/article/101830?from=shop_table&btm_ppre=a4977.b4369.c0.d0&btm_pre=a4977.b6444.c0.d0&btm_sh（sub_code: isv.business-failed:110200024） | 请检查入参 |
| `50002` | 业务处理失败 / 库存类型含有区域库存，数据异常，请使用OpenApi进行库存编辑（sub_code: isv.business-failed:110240115） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}不能设置为虚拟商品（sub_code: isv.business-failed:110101104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 手机充值业务三个必填类目属性（地区、面值、运营商）需要进行填写（sub_code: isv.business-failed:110215114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110270139:商品关联未结束的限时特卖活动，仅支持现货发货模式和阶梯发货模式（sub_code: isv.business-failed:110270139） | 请检查入参 |
| `50002` | 业务处理失败 / 划线价需高于售卖价{*}（sub_code: isv.business-failed:110310115） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010060:商家不支持 假一赔十 权益（sub_code: isv.business-failed:2010060） | 检查参数后重试 |
| `50002` | 业务处理失败 / 暂不支持修改规格（sub_code: isv.business-failed:110220128） | 请检查入参信息 |
| `50002` | 业务处理失败 / 子商品库存类型不完全是区域库存（sub_code: isv.business-failed:110320102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 卡券有效期结束时间限制（sub_code: isv.business-failed:110270171） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该商品已删除（sub_code: isv.business-failed:2010042） | 不允许编辑 |
| `50002` | 业务处理失败 / 省钱卡必须选择售后退改规则（sub_code: isv.business-failed:110270143） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格图片长宽比非1:1（sub_code: isv.business-failed:110220109） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3074 |
| `50002` | 业务处理失败 / 商品起售件数不能超过每次限购件数（sub_code: isv.business-failed:110280113） | 请检查入参信息 |
| `50002` | 业务处理失败 / outProductId或者outerProductId已经存在（sub_code: isv.business-failed:110101114） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3356 |
| `50002` | 业务处理失败 / 前置质检单库存模式:库存{*}（sub_code: isv.business-failed:110240103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 {*} 填写信息不正确（sub_code: isv.business-failed:110215127） | 请检查入参信息 |
| `50002` | 业务处理失败 / 时效SKU现货+预售模式只能选择一种现货时（sub_code: isv.business-failed:110220134） | 请检查入参信息 |
| `50002` | 业务处理失败 / 主商品是非区域库存时，子商品不能是区域库存商品（sub_code: isv.business-failed:110240109） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110220013：SKU分类值填写错误，请使用正确分类（sub_code: isv.business-failed:110220013） | 检查参数后重试 |
| `50002` | 业务处理失败 / 110220018:规格「颜色分类」对应的规格值「黑色999999999」含有连续相同的数字，请修改后重试；（sub_code: isv.business-failed:110220018） | 请检查入参 |
| `50002` | 业务处理失败 / 请修改“售后服务“，该类目已不再支持该售后政策（sub_code: isv.business-failed:110330102） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2748 |
| `50002` | 业务处理失败 / 110215135:属性 生产日期 仅支持时间戳格式输入，例如：2006-01-02（sub_code: isv.business-failed:110215135） | - |
| `50002` | 业务处理失败 / 无法修改商品价格（sub_code: isv.business-failed:110371019） | 请检查入参信息 |
| `50002` | 业务处理失败 / [*]非素材中心url（sub_code: isv.business-failed:110502009） | 请检查入参 |
| `50002` | 业务处理失败 / 不支持部分修改{*}（sub_code: isv.business-failed:110102121） | 请检查入参信息 |
| `50002` | 业务处理失败 / 阶梯发货模式切换，不允许缺省sku参数（sub_code: isv.business-failed:110220127） | 请检查入参信息 |
| `60000` | 触发限流，请稍后重试 / 编辑商品失败：接口限流（sub_code: isp.traffic-limited:2010401） | 稍后重试 |
| `20000` | 系统错误 / 读取失败（sub_code: isp.service-error:2010013） | 重试 |
| `50002` | 业务处理失败 / 平台会员商品暂不支持修改类目（sub_code: isv.business-failed:110210023） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 {*} 填写信息不正确（sub_code: isv.business-failed:110215128） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格名称含有emoji等特殊字符,请修改后重试（sub_code: isv.business-failed:110220158） | 请检查入参信息 |
| `40004` | 非法的参数 / 品牌受限（sub_code: isv.parameter-invalid:2010317） | 检查参数后重试 |
| `20000` | 系统错误 / 查询品牌库失败（sub_code: isp.service-error:2010206） | 重试 |
| `50002` | 业务处理失败 / {*}组套子品不允许修改商货绑定关系（sub_code: isv.business-failed:110260136） | 请检查入参信息 |
| `50002` | 业务处理失败 / 短标题不能为空（sub_code: isv.business-failed:110101133） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010318:当前商品选择的品牌信息已过期，请更新品牌资质信息，或更换商品品牌后，再提交商品发布。（sub_code: isv.business-failed:2010318） | 请检查入参 |
| `50002` | 业务处理失败 / 组合商品发货模式、发货时间必须与所有子品一致（sub_code: isv.business-failed:110320124） | 请检查入参信息 |
| `50002` | 业务处理失败 / 以下商品类型(闪购、拍卖、竞拍、组套)暂不支持配置参考价（sub_code: isv.business-failed:110310122） | 请检查入参信息 |
| `50002` | 业务处理失败 / 组合商品无法直接上线（sub_code: isv.business-failed:110320001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 奖品SKU价格必须为0（sub_code: isv.business-failed:110310006） | 请检查入参信息 |
| `50002` | 业务处理失败 / 非商家类型无法修改成商家产品类型（sub_code: isv.business-failed:110101139） | 请检查入参信息 |
| `50002` | 业务处理失败 / 未查询到保税仓/海关仓信息，请检查（sub_code: isv.business-failed:110240117） | 请检查入参信息 |
| `50002` | 业务处理失败 / 子商品{*}无备案信息，不支持组合商品（sub_code: isv.business-failed:110320114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该商品中货品未设置采购价，请先联系对应小二设置采购价（sub_code: isv.business-failed:110260114） | 请检查入参信息 |
| `50002` | 业务处理失败 / 加油包类商品只能在指定店铺下发布（sub_code: isv.business-failed:110101132） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品是组合商品的子商品，不支持切组合商品（sub_code: isv.business-failed:110320122） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品正在参加平台活动，暂不支持切组合商品（sub_code: isv.business-failed:110371101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110230002:当前商品大于三级规格，请使用sell_properties参数（sub_code: isv.business-failed:110230002） | 检查参数后重试 |
| `50002` | 业务处理失败 / 定金找货时间必须是{*}-{*}天（sub_code: isv.business-failed:110280016） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商家编码存在重复（sub_code: isv.business-failed:110220124） | 请检查入参信息 |
| `50002` | 业务处理失败 / 设置参考价时须提供相关凭证（sub_code: isv.business-failed:110310119） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}含有emoji等特殊字符,请修改后重试（sub_code: isv.business-failed:110220152） | 请检查入参信息 |
| `50002` | 业务处理失败 / 跨境、海免商品不支持设置坏损包退（sub_code: isv.business-failed:110330105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 实物母蟹单只蟹重和实物公蟹单只蟹重只可输入数字且最多可保留一位小数（sub_code: isv.business-failed:110215115） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU 品牌所在地不一致（sub_code: isv.business-failed:110260124） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品大于三级规格，请使用sell_properties参数（sub_code: isv.business-failed:110220117） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}只允许通过营销中心创建（sub_code: isv.business-failed:110102134） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品与门店库解绑，分账比例需要清零（sub_code: isv.business-failed:110270031） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010348:门店未绑定绑定限售模板（sub_code: isv.business-failed:2010348） | 检查参数后重试 |
| `50002` | 业务处理失败 / 当前店铺类型不支持选择过敏包退服务（sub_code: isv.business-failed:110330112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110126002:当前商品设置达人库存，暂不支持修改规格（sub_code: isv.business-failed:110126002） | 检查参数后重试 |
| `50002` | 业务处理失败 / 省钱卡售后退改规则必须为随时退或过期退（sub_code: isv.business-failed:110270144） | 请检查入参信息 |
| `50002` | 业务处理失败 / 省钱卡类商品只能在指定店铺下发布（sub_code: isv.business-failed:110101135） | 请检查入参信息 |
| `50002` | 业务处理失败 / 阶梯库存模式不合法（sub_code: isv.business-failed:110240110） | 请检查入参信息 |
| `40004` | 非法的参数 / 店铺需要绑定（sub_code: isv.parameter-invalid:2010050） | 完成账号绑定 |
| `50002` | 业务处理失败 / {*}含有emoji等特殊字符,请修改后重试（sub_code: isv.business-failed:110220154） | 请检查入参信息 |
| `50002` | 业务处理失败 / 组套子商品不允许解绑货品（sub_code: isv.business-failed:110260108） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}仅支持在{*}编辑（sub_code: isv.business-failed:110102133） | 请检查入参信息 |
| `40004` | 非法的参数 / 品牌必填（sub_code: isv.parameter-invalid:2010320） | 请重新选择品牌 |
| `50002` | 业务处理失败 / 手机充值类目商品暂不支持物流和核销（sub_code: isv.business-failed:110270158） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}规格名称超过64个字符,请修改后重试（sub_code: isv.business-failed:110220155） | 请检查入参信息 |
| `50002` | 业务处理失败 / 最多支持配置1个{*}的网页url（sub_code: isv.business-failed:110290103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 {*} 成分含量和不能超过 {*}（sub_code: isv.business-failed:110215130） | 请检查入参信息 |
| `50002` | 业务处理失败 / sku价格值范围限制（sub_code: isv.business-failed:110310118） | 具体参考https://op.jinritemai.com/docs/question-docs/92/1727 |
| `50002` | 业务处理失败 / 必须要有outerSkuId（sub_code: isv.business-failed:110220125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持移动端操作{*}，请前往电脑端进行管理（sub_code: isv.business-failed:110102127） | 请检查入参信息 |
| `50002` | 业务处理失败 / 发货时间配置不满足要求（sub_code: isv.business-failed:110270179） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2412 |
| `50002` | 业务处理失败 / 延迟发货时间配置错误，开始时间应该小于结束时间（sub_code: isv.business-failed:110270105） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 {*} 的属性值数量与属性类型不匹配，时间戳类型的属性需要有2个属性值，分别代表开始时间和结束时间（sub_code: isv.business-failed:110215131） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2178 |
| `50002` | 业务处理失败 / {*}为必填属性，且可选择的属性值不包括{*}，请重新进入页面补充（sub_code: isv.business-failed:110215116） | 具体参考https://op.jinritemai.com/docs/question-docs/92/1679 |
| `50002` | 业务处理失败 / 未找到货品备案信息，请重新备案（sub_code: isv.business-failed:110260146） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法直接通过该接口创建或编辑{*}（sub_code: isv.business-failed:110102124） | 请检查入参信息 |
| `50002` | 业务处理失败 / sku不能重复关联货品信息，货品id={*}（sub_code: isv.business-failed:110260112） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品最大购买件数为{*}，请修改（sub_code: isv.business-failed:110280108） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}还不支持配网页url（sub_code: isv.business-failed:110290104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 {*} 填写信息不正确（sub_code: isv.business-failed:110215126） | 请检查入参信息 |
| `50002` | 业务处理失败 / 类目属性必填校验，部分必填属性未填写（sub_code: isv.business-failed:110215111） | [xxx证书编号]等目前属于资质属性，在一定条件下需要填写该属性，目前还未提供相关规则接口，请先填写相关属性，具体参考https://op.jinritemai.com/docs/question-docs/92/590 |
| `50002` | 业务处理失败 / 标称金重单位格式不正确，请检查：{*}（sub_code: isv.business-failed:110310137） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3942 |
| `50002` | 业务处理失败 / 110101147:请补充商品标题（sub_code: isv.business-failed:110101147） | - |
| `50002` | 业务处理失败 / {*}必须设置参考价与凭证（sub_code: isv.business-failed:110310123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 货品类目需要和商品类目保持一致（sub_code: isv.business-failed:110260013） | 请检查入参信息 |
| `50002` | 业务处理失败 / 价格校验拦截（sub_code: isv.business-failed:110205003） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3291 |
| `50002` | 业务处理失败 / 在线支付不需要选择验证方式（sub_code: isv.business-failed:110280007） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商家产品类型不可切换（sub_code: isv.business-failed:110101137） | 请检查入参信息 |
| `20000` | 系统错误 / 请求超时（sub_code: isp.service-error:2010002） | 重试 |
| `50002` | 业务处理失败 / 清关方式不支持切换（sub_code: isv.business-failed:110270022） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}不允许绑定多货品（sub_code: isv.business-failed:110320109） | 请检查入参信息 |
| `50002` | 业务处理失败 / Sku数据异常（sub_code: isv.business-failed:110220131） | 请检查入参信息 |
| `50002` | 业务处理失败 / 2010329:当前店铺类型下，不支持在该类目发布此品牌商品。您可查看对应“行业管理规范”的入驻方式。请跳转https://zjsms.com/NE7whg4/（sub_code: isv.business-failed:2010329） | 检查参数后重试 |
| `50002` | 业务处理失败 / 110220016:规格颜色对应的规格值.仅包含特殊字符，请修改并输入有效信息；（sub_code: isv.business-failed:110220016） | 请检查入参 |
| `50002` | 业务处理失败 / 110215125:当前类型店铺，货号不能为空（sub_code: isv.business-failed:110215125） | - |
| `50002` | 业务处理失败 / 门店库不支持分账（sub_code: isv.business-failed:110270132） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品至少需要一个sku（sub_code: isv.business-failed:110220104） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215011:类目属性「条形码」存在属性值「0000000000」含有连续相同的数字，请修改后重试；（sub_code: isv.business-failed:110215011） | 请检查入参 |
| `40004` | 非法的参数 / 内容未做修改（sub_code: isv.parameter-invalid:2010102） | 请修改后提交审核 |
| `50002` | 业务处理失败 / 奖品不绑定货品不支持区域库存（sub_code: isv.business-failed:110240014） | 请检查入参信息 |
| `50002` | 业务处理失败 / 清关方式填写有误, 只支持{*}（sub_code: isv.business-failed:110270125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 无法修改发货方式（sub_code: isv.business-failed:110371008） | 请检查入参信息 |
| `50002` | 业务处理失败 / Sku编码不合法（sub_code: isv.business-failed:110220123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不能同时支持拍卖和竞拍类型（sub_code: isv.business-failed:110101010） | 请检查入参信息 |
| `50002` | 业务处理失败 / 库存数量支持范围：0-{*}（sub_code: isv.business-failed:110240102） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3861 |
| `50002` | 业务处理失败 / 110250008:尺码模板不支持当前类目（sub_code: isv.business-failed:110250008） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010340:当前商品使用的品牌未关联当前类目，请切换品牌或者前往商家资质中心补全品牌资质信息，之后再上架商品。（sub_code: isv.business-failed:2010340） | 检查参数后重试 |
| `50002` | 业务处理失败 / 素材信息校验未通过（sub_code: isv.business-failed:110250015） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前接口不支持发布编辑{*}（sub_code: isv.business-failed:110102126） | 请检查入参信息 |
| `50002` | 业务处理失败 / 权益 {*} 尚未签约，请到权益中心签约（sub_code: isv.business-failed:110330121） | 请检查入参信息 |
| `50002` | 业务处理失败 / {*}暂不支持设置参考价（sub_code: isv.business-failed:110310012） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前商品不允许配置延迟发货时间（sub_code: isv.business-failed:110270013） | 请检查入参信息 |
| `50002` | 业务处理失败 / 结构化标题-{*}不能为空（sub_code: isv.business-failed:110101123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 预约发货时间范围0-{*},请重新填写（sub_code: isv.business-failed:110270151） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前sku不支持绑定货品（sub_code: isv.business-failed:110260137） | 请检查入参信息 |
| `50002` | 业务处理失败 / 不支持的坏损包退类型（sub_code: isv.business-failed:110330103） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性值不存在， propertyId:{*}（当前属性为枚举可输入属性，但是diy_type为0）（sub_code: isv.business-failed:110215118） | 具体参考https://op.jinritemai.com/docs/question-docs/92/3693；https://op.jinritemai.com/docs/question-docs/92/3990 |
| `50002` | 业务处理失败 / 生活娱乐充值只支持虚拟商品（sub_code: isv.business-failed:110270161） | 请检查入参信息 |
| `50002` | 业务处理失败 / 存在审批中素材，请等待审批（sub_code: isv.business-failed:110250136） | 当前还有素材在审批中，无法进行商品编辑，请耐心等待。可以根据/product/detail中返回的product_audit_info .material_audit_status获取素材审批状态，具体参考https://op.jinritemai.com/docs/question-docs/92/3969 |
| `50002` | 业务处理失败 / 110220012：至少包含一个主售款sku（sub_code: isv.business-failed:110220012） | 检查参数后重试 |
| `50002` | 业务处理失败 / 商家未开通货到付款，无法上架货到付款商品（sub_code: isv.business-failed:110280107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 需求资质的非卖品商品详情必须为空（sub_code: isv.business-failed:110250116） | 请检查入参信息 |
| `40004` | 非法的参数 / 无访问权限（sub_code: isv.parameter-invalid:2010005） | 核对后重试 |
| `50002` | 业务处理失败 / 非白名单商家，不能选择店铺是否展示（sub_code: isv.business-failed:110101107） | 请检查入参信息 |
| `50002` | 业务处理失败 / 当前组合商品中子商品“{*}”目前处于{*}状态，暂不支持该组合商品上架（sub_code: isv.business-failed:110320108） | 请检查入参信息 |
| `50002` | 业务处理失败 / 省钱卡必须选择第三方平台生成的方式（sub_code: isv.business-failed:110270142） | 请检查入参信息 |
| `50002` | 业务处理失败 / 货品不在所选仓内，请重新绑定货品后重试（sub_code: isv.business-failed:110260135） | 请检查入参信息 |
| `50002` | 业务处理失败 / 规格填写不符合要求,规格值{*}中的{*}需要从{*}中选择（sub_code: isv.business-failed:110220147） | 请检查入参信息 |
| `50002` | 业务处理失败 / outerProductId和outProductId传参有误（sub_code: isv.business-failed:110101115） | 具体参考https://op.jinritemai.com/docs/question-docs/92/983 |
| `50002` | 业务处理失败 / 类目不支持多账号充值（sub_code: isv.business-failed:110270131） | 具体参考https://op.jinritemai.com/docs/question-docs/92/2458 |
| `50002` | 业务处理失败 / 当前商品类型不能进行部分编辑（sub_code: isv.business-failed:110102111） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品标题最长不能超过[*]个汉字（[*]个字符）,商品标题最短不能低于[*]个汉字（[*]个字符）（sub_code: isv.business-failed:110101150） | 请检查入参信息 |
| `50002` | 业务处理失败 / 结构化标题名称不匹配（sub_code: isv.business-failed:110101121） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110310110:当前商品正在参与活动 抢先购家店 20230915 13:22，商品sku价格不得低于活动到手价格￥159.80元，请修改后重新提交。（sub_code: isv.business-failed:110310110） | 请检查入参 |
| `40004` | 非法的参数 / 编辑商品失败（sub_code: isv.parameter-invalid:2010011） | 请检查参数后重试 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:2010004） | 请检查参数后重试 |
| `50002` | 业务处理失败 / {*}暂不支持切组合商品（sub_code: isv.business-failed:110320113） | 请检查入参信息 |
| `50002` | 业务处理失败 / 您发布的商品不在平台公示的生命周期内，具体可参见&nbsp;<a href='https://school.jinritemai.com/doudian/web/article/109548' target='_blank'>【生鲜】行业管理规范-抖音电商学习中心 (jinritemai.com)</a>（sub_code: isv.business-failed:110201004） | 请检查入参信息 |
| `50002` | 业务处理失败 / 运费模板不存在（sub_code: isv.business-failed:110270110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 店铺内条码唯一性校验（sub_code: isv.business-failed:110220160） | 请检查当前的sku条码参数是否被其他商品使用 |
| `50002` | 业务处理失败 / 图片链接错误:{*}（sub_code: isv.business-failed:110207005） | 请检查入参信息 |
| `50002` | 业务处理失败 / 分销商品价格低于分销产品sku价格，分销商品价格：{*}元，分销产品价格：{*}元（sub_code: isv.business-failed:110310136） | 请检查入参信息 |
| `50002` | 业务处理失败 / 图片上传失败: url带参数（sub_code: isv.business-failed:110207007） | 请检查入参信息 |
| `50002` | 业务处理失败 / “尺码数据”不可含有非法字符（sub_code: isv.business-failed:110250111） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU重量单位不合法（sub_code: isv.business-failed:110270137） | 请检查入参信息 |
| `50002` | 业务处理失败 / 表格内的尺码和选中尺码列表不匹配（sub_code: isv.business-failed:110250110） | 请检查入参信息 |
| `50002` | 业务处理失败 / 类目属性「充绒量」存在非法字符，请修改后重试；（sub_code: isv.business-failed:110215013） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性 净含量 计量单位信息不存在，请刷新后重试（sub_code: isv.business-failed:110215132） | 请检查入参信息 |
| `50002` | 业务处理失败 / 类目属性[货号]中含有emoji等特殊字符，请检查后重试（sub_code: isv.business-failed:110215102） | 请检查入参信息 |
| `50002` | 业务处理失败 / 未查询到该类目（sub_code: isv.business-failed:110201001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品存在预定的上架时间, 暂不支持提前上架, 预定上架时间: 2024-01-13 00:00:00（sub_code: isv.business-failed:110101179） | 请检查入参信息 |
| `50002` | 业务处理失败 / SKU状态设置错误（sub_code: isv.business-failed:110220162） | 请检查入参信息 |
| `50002` | 业务处理失败 / 商品编辑失败, 图片上传失败: too many urls: 50（sub_code: isv.business-failed:110207006） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该商品为竞拍商品，请前往电脑端商家后台进行操作（sub_code: isv.business-failed:2010014） | 请检查入参信息 |
| `50002` | 业务处理失败 / 该商品不支持配置三包服务承诺（sub_code: isv.business-failed:110330123） | 请检查入参信息 |
| `50002` | 业务处理失败 / 三包服务售后天数不合法（sub_code: isv.business-failed:110330126） | 请检查入参信息 |
| `50002` | 业务处理失败 / 三包服务类型不合法（sub_code: isv.business-failed:110330125） | 请检查入参信息 |
| `50002` | 业务处理失败 / 请上传包装标签图（sub_code: isv.business-failed:110290001） | 请检查入参信息 |
| `50002` | 业务处理失败 / StoreId不允许修改（sub_code: isv.business-failed:110101177） | 请检查入参信息 |
| `50002` | 业务处理失败 / 类目与账号模版无法匹配（sub_code: isv.business-failed:110270113） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性填写不符合要求,2024-03-12,2024-03-13必须与measure_info匹配, 请至抖店商品编辑页面刷新页面重试（sub_code: isv.business-failed:110220164） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性填写不符合要求,面料材质属性值含量之和要求为100%, 请至抖店商品编辑页面刷新页面重试（sub_code: isv.business-failed:110220165） | 请检查入参信息 |
| `50002` | 业务处理失败 / 前缀匹配失败：使用品牌名时必须传前缀字段（sub_code: isv.business-failed:110101201） | 请检查入参信息 |
| `50002` | 业务处理失败 / 门店未绑定区域仓（sub_code: isv.business-failed:2010346） | 请检查入参信息 |
| `50002` | 业务处理失败 / 属性填写不符合要求,面料材质属性值含量必须全填写或全不填写，且材质不能重复, 请至抖店商品编辑页面刷新页面重试（sub_code: isv.business-failed:110220166） | 请检查入参信息 |
| `50002` | 业务处理失败 / 前缀匹配失败：请检查品牌前缀是否必填或者是否有误（sub_code: isv.business-failed:110101200） | 请检查入参信息 |
| `50002` | 业务处理失败 / 发布当前刀具类商品，需要签署《刀具合规经营承诺函》，前往https://fxg.jinritemai.com/ffa/w/contract/manage完成承诺书阅读并签署后方可发布商品。（sub_code: isv.business-failed:110200118） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110215137:属性“面料材质“的填写格式已升级，属性值“聚酯纤维“不符合填写格式要求，请点击属性输入框重新填写（sub_code: isv.business-failed:110215137） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101214:商品被处置下架且未修改商品信息，请先修改商品再重新提交上架（sub_code: isv.business-failed:110101214） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101215:新现货+预售发货模式商品，不允许切换成旧阶梯发货模式（sub_code: isv.business-failed:110101215） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110405001:该商品商详页描述（含标题、主图和商品详情）与属性栏选择的材质不一致，请修改。规则详见https://school.jinritemai.com/doudian/web/question/50（sub_code: isv.business-failed:110405001） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110250142:尺码信息中体重(斤)不能小于4（sub_code: isv.business-failed:110250142） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110360101:品牌不存在或者未审核通过，id:713581463（sub_code: isv.business-failed:110360101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101222:商品标题中缺少【规格】（sub_code: isv.business-failed:110101222） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110210101:类目必填（sub_code: isv.business-failed:110210101） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110502037:主品非售卖中状态，请先上架主品（sub_code: isv.business-failed:110502037） | 110502037:主品非售卖中状态，请先上架主品 |
| `50002` | 业务处理失败 / 110270020:sku重量不能大于99999.999g（sub_code: isv.business-failed:110270020） | 110270020:sku重量不能大于99999.999g |
| `50002` | 业务处理失败 / 110101219:“价格”超出系统最小值限制（sub_code: isv.business-failed:110101219） | 110101219:“价格”超出系统最小值限制 |
| `50002` | 业务处理失败 / 110250159:存在审批中素材(主图视频)，请等待审批（sub_code: isv.business-failed:110250159） | 110250159:存在审批中素材(主图视频)，请等待审批 |
| `50002` | 业务处理失败 / 110103015:外部商品ID重复（sub_code: isv.business-failed:110103015） | 110103015:外部商品ID重复 |
| `50002` | 业务处理失败 / 110220188:属性:面料材质填写不符合要求,其他100%部分必填模块信息缺失,请至抖店商品编辑页面刷新页面重试（sub_code: isv.business-failed:110220188） | 110220188:属性:面料材质填写不符合要求,其他100%部分必填模块信息缺失,请至抖店商品编辑页面刷新页面重试 |
| `50002` | 业务处理失败 / 110250113:标题注释不能超过50个字（sub_code: isv.business-failed:110250113） | 110250113:标题注释不能超过50个字 |
| `50002` | 业务处理失败 / 110101213:“价格”最大值超出系统限制（sub_code: isv.business-failed:110101213） | 110101213:“价格”最大值超出系统限制 |
| `50002` | 业务处理失败 / 110211010:st: -20009, msg: 商品：3717291843369697299 （白色-均码）正在参加平台活动（双十一返场市集活动-官方立减&一件直降商品报名 ），无法修改库存信息（sub_code: isv.business-failed:110211010） | 110211010:st: -20009, msg: 商品：3717291843369697299 （白色-均码）正在参加平台活动（双十一返场市集活动-官方立减&一件直降商品报名 ），无法修改库存信息 |
| `50002` | 业务处理失败 / 110210104:展会拍卖类目仅能发布拍卖商品 不支持使用该类目（sub_code: isv.business-failed:110210104） | 110210104:展会拍卖类目仅能发布拍卖商品 不支持使用该类目 |
| `50002` | 业务处理失败 / 110220191:营养成分表计量单位必填,请至抖店商品编辑页面刷新页面重试（sub_code: isv.business-failed:110220191） | 110220191:营养成分表计量单位必填,请至抖店商品编辑页面刷新页面重试 |
| `50002` | 业务处理失败 / 110250108:模板行数超过上限（sub_code: isv.business-failed:110250108） | 110250108:模板行数超过上限 |
| `50002` | 业务处理失败 / 110104130:当前类型商品暂不支持定制属性（sub_code: isv.business-failed:110104130） | 110104130:当前类型商品暂不支持定制属性 |
| `50002` | 业务处理失败 / 2010306:阶梯发货模式商品不能设置区域库存（sub_code: isv.business-failed:2010306） | 2010306:阶梯发货模式商品不能设置区域库存 |
| `50002` | 业务处理失败 / 110330124:该商品必须配置三包服务承诺（sub_code: isv.business-failed:110330124） | 110330124:该商品必须配置三包服务承诺 |
| `50002` | 业务处理失败 / 110101259:该商品尚未上传食品属性标签图，请使用ISV上传后重试（sub_code: isv.business-failed:110101259） | 110101259:该商品尚未上传食品属性标签图，请使用ISV上传后重试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:110320008",
  "sub_msg": "子商品{*}包含时效SKU，暂不支持组合"
}
```

## 备注
