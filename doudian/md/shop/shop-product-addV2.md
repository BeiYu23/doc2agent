# product.addV2

> 发布商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.product.addV2` |
| 中文名 | 发布商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/addV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2081 |
| 更新日期 | `2022-07-20` |

## 接口说明

- 文档书: 店铺API（版本 V17.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_product_id` | body | string | 否 | 推荐使用，外部商家编码，支持字符串 | `232334` |
| `product_type` | body | number | 是 | 0-普通，3-虚拟，6玉石闪购，7云闪购 | `0` |
| `category_leaf_id` | body | number | 是 | 叶子类目ID通过/shop/getShopCategory接口获取 | `20000` |
| `product_format` | body | string | 否 | （已废弃，用新字段product_format_new）属性名称\|属性值 之间用\|分隔, 多组之间用^分开 | `货号\|8888^上市年份季节\|2018年秋季` |
| `name` | body | string | 是 | 商品名称，最多60个字符(30个汉字)，不能含emoj表情 | `xxx补水液` |
| `recommend_remark` | body | string | 否 | 商家推荐语，不能含emoj表情 | `这个商品很好啊` |
| `pic` | body | string | 是 | 商品轮播图，多张图片用 \"\|\" 分开，第一张图为主图，最多5张，至少600x600，大小不超过1M。 | `img_url1\|img_url2\|img_url3` |
| `description` | body | string | 是 | 商品描述，目前只支持图片。多张图片用 \"\|\" 分开。不能用其他网站的文本粘贴，这样会出现css样式不兼容。 | `img_url1\|img_url2\|img_url3` |
| `pay_type` | body | number | 否 | 支付方式，0货到付款 1在线支付，2，货到付款+在线支付 | `1` |
| `delivery_method` | body | string | 否 | 海南免税生效。 0:离岛免税、1:邮寄、2:离岛自提+邮寄 | `7` |
| `cdf_category` | body | string | 否 | 海南免税：海关限购分类编码 | `1` |
| `reduce_type` | body | number | 是 | 1 减库存类型：1-拍下减库存 2-付款减库存 | `1` |
| `assoc_ids` | body | string | 否 | 同店商品推荐：为空表示使用系统推荐；多个product_id使用“\|”分开 | `1\|2\|3` |
| `freight_id` | body | number | 是 | 运费模板id，传0表示包邮，通过/freightTemplate/list接口获取 | `123` |
| `weight` | body | string | 否 | 重量 | `1000` |
| `weight_unit` | body | number | 否 | 重量单位，0-kg, 1-g | `1` |
| `delivery_delay_day` | body | number | 否 | delivery_delay_day： 承诺发货时间，单位是天,不传则默认为2天。现货发货(presell_type=0)和阶梯发货模式(presell_type=2)时必填，支持传入9999 、1、 2 （分别表示当日发、次日发、48小时发），具体支持传入的参数范围/product/getProductUpdateRule | `7` |
| `presell_type` | body | number | 否 | 发货模式，0-现货发货，1-预售发货，2-阶梯发货，默认0 | `0` |
| `presell_delay` | body | number | 否 | 全款预售模式时的发货时间/阶梯模式下阶梯发货时间，具体支持传入的参数范围/product/getProductUpdateRule。 | `7` |
| `presell_end_time` | body | string | 否 | 预售结束时间，格式2020-02-21 18:54:27，最多支持设置距离当前30天 | `2020-02-21 18:54:27` |
| `supply_7day_return` | body | number | 否 | 是否支持7天无理由，0不支持，1支持，2支持（拆封后不支持） | `1` |
| `mobile` | body | string | 是 | 客服电话号码 | `40012345` |
| `commit` | body | boolean | 是 | false仅保存，true保存+提审 | `true` |
| `brand_id` | body | number | 否 | （brand_id已废弃，用新字段standard_brand_id）品牌id (请求店铺授权品牌接口获取) (效果即为商品详情页面中的品牌字段) | `123` |
| `remark` | body | string | 否 | 商家可见备注 | `备注` |
| `out_product_id` | body | number | 否 | 外部product_id | `123` |
| `quality_list` | body | array | 否 | 资质，可通过/product/qualificationConfig获取 | `` |
| `  └ quality_key` | body | string | 是 | 资质key | `3457***9470978` |
| `  └ quality_name` | body | string | 是 | 资质名称 | `进货凭证` |
| `  └ quality_attachments` | body | array | 是 | 资质 | `` |
| `    └ media_type` | body | number | 是 | 1-图片，2-pdf | `1` |
| `    └ url` | body | string | 是 | 凭证url | `\"http://www.byted***.com/YYYY\"` |
| `spec_name` | body | string | 否 | 如果不填，则规格名为各级规格名用 \"-\" 自动生成 | `颜色-尺码` |
| `specs` | body | string | 是 | 店铺通用规格，能被同类商品通用。多规格用^分隔，规格与规格值用\|分隔，多个规格值用,分隔。如果创建或编辑现货+预售商品或新预售商品时，须包含发货时效，如：颜色\|黑色,白色,黄色^尺码\|S,M,L^发货时效\|5天内发货,15天内发货 | `颜色\|红色,黑色^尺码\|S,M` |
| `spec_prices` | body | string | 是 | sku详情，数量应该等于规格1规格2规格3，sku数量和规格组合数必须一致 sku不可售时，库存可设置为0。 delivery_infos为SKU物流信息，info_value为字符串类型（示例："12.5"），info_type填weight，info_unit支持mg,g,kg | `[{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":11,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"红色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":22,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"S\",\"spec_detail_name3\":\"\",\"stock_num\":44,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]},{\"spec_detail_name1\":\"黑色\",\"spec_detail_name2\":\"M\",\"spec_detail_name3\":\"\",\"stock_num\":55,\"price\":100,\"code\":\"\",\"step_stock_num\":0,\"supplier_id\":\"\",\"outer_sku_id\":\"\",\"delivery_infos\":[{\"info_type\":\"weight\",\"info_value\":\"100\",\"info_unit\":\"mg\"}]}]` |
| `spec_pic` | body | string | 否 | 如颜色-尺寸, 颜色就是主规格, 颜色如黑,白,黄,它们图片url以逗号分隔 注：\"pic\"、\"description\"、\"spec_pic\"这三个字段里的传入的图片数量总和，不得超过50张。 | `img_url,img_url,img_url` |
| `maximum_per_order` | body | number | 否 | 每个用户每次下单限购件数 | `200` |
| `limit_per_buyer` | body | number | 否 | 每个用户累计限购件数 | `1` |
| `minimum_per_order` | body | number | 否 | 每个用户每次下单至少购买的件数 | `2` |
| `product_format_new` | body | string | 否 | 属性，通过/product/getCatePropertyV2获取 格式：{"property_id":[{"value":value,"name":"property_name","diy_type":0}]} name的类型是string，value和diy_type的类型是number | `{\"405\":[{\"value\":27664,\"name\":\"复习资料\",\"diy_type\":0}],\"449\":[{\"value\":0,\"name\":\"佚名\",\"diy_type\":0}],\"501\":[{\"value\":7310,\"name\":\"否\",\"diy_type\":0}],\"855\":[{\"value\":61683,\"name\":\"北京出版社\",\"diy_type\":0}],\"1088\":[{\"value\":407,\"name\":\"小学五年级\",\"diy_type\":0}],\"1319\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"1601\":[{\"value\":13911,\"name\":\"通用版\",\"diy_type\":0}],\"1618\":[{\"value\":0,\"name\":\"9787218122861\",\"diy_type\":0}],\"1831\":[{\"value\":0,\"name\":\"小学英语看图说话写话二年级\",\"diy_type\":0}],\"2000\":[{\"value\":34762,\"name\":\"无\",\"diy_type\":0}],\"2229\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"2763\":[{\"value\":25193,\"name\":\"英语\",\"diy_type\":0}],\"3271\":[{\"value\":0,\"name\":\"1\",\"diy_type\":0}],\"3296\":[{\"value\":0,\"name\":\"16.80元\",\"diy_type\":0}]}` |
| `spu_id` | body | number | 否 | spu_id | `14567` |
| `appoint_delivery_day` | body | number | 否 | 可预约发货天数 | `2` |
| `third_url` | body | string | 否 | third_url | `http://img.alicdn.com/xxxx` |
| `extra` | body | string | 否 | extra | `略` |
| `src` | body | string | 否 | src | `略` |
| `standard_brand_id` | body | number | 否 | 品牌id，通过/brand/list获取，无品牌id则传596120136 | `111` |
| `need_check_out` | body | boolean | 否 | 卡券类型需要传true | `true` |
| `poi_resource` | body | object | 否 | 卡券信息 | `` |
| `  └ valid_days` | body | number | 否 | 有效时间段，从领取日开始计算，优先级高于ValidStart-ValidEnd | `5` |
| `  └ valid_start` | body | number | 否 | 卡券有效开始时间，秒单位时间戳 | `1636616483` |
| `  └ valid_end` | body | number | 否 | 卡券有效截止时间，秒单位时间戳 | `1636616483` |
| `  └ service_num` | body | string | 否 | 客服电话 | `13111111111` |
| `  └ notification` | body | string | 否 | 领取须知 | `领取须知` |
| `  └ code_type` | body | number | 否 | 平台产生券码: 1 ; 合作方api实时传入的券码: 4 | `1` |
| `  └ count` | body | number | 否 | 券码总量，0/-1表示不限制，平台券时须\u003e0 | `1` |
| `  └ couponSecondExchange` | body | number | 否 | 0-不支持二次兑换，1-支持二次兑换 | `0` |
| `  └ total_can_use_count` | body | string | 否 | 可核销总次数 | `1` |
| `  └ link` | body | string | 否 | 兑换链接 | `https://xxx.xxx.xxx` |
| `  └ condition` | body | string | 否 | 券码使用条件 | `券码使用条件` |
| `  └ coupon_return_methods` | body | array | 否 | 数组当前只支持一个元素且只可为 1或2，其中 1 表示随时退+过期自动退，2 表示不支持退 | `[1]` |
| `car_vin_code` | body | string | 否 | 汽车vin码 | `BA111111111111111` |
| `presell_config_level` | body | number | 否 | 0：全款预售，1：sku预售，2：现货+预售 ，3：新预售 | `3` |
| `need_recharge_mode` | body | boolean | 否 | 充值模式 | `true` |
| `account_template_id` | body | string | 否 | 账号模板id | `122112` |
| `presell_delivery_type` | body | number | 否 | 全款预售和sku预售时传递，其他不传： 0 预售结束后发货  1支付完成后发货 | `1` |
| `white_back_ground_pic_url` | body | string | 否 | 白底图url(仅素材中心url有效) | `http://aaaa` |
| `long_pic_url` | body | string | 否 | 3:4长图url(仅素材中心url有效) | `http://aaaa` |
| `after_sale_service` | body | string | 否 | 推荐传入，售后服务参数,key:value格式。supply_day_return_selector(7天无理由选项)：N天-政策代号，N只支持7和15，政策代号枚举https://bytedance.feishu.cn/docs/doccnF946oh1c98e7mo9DlYZtig 。 supply_red_ass_return（红屁屁无忧）：0不支持，1支持。supply_allergy_return（过敏无忧,仅跨境可选）：0不支持，1支持。 damaged_order_return（坏损包退）：0不支持，1支持。 support_allergy_returnV2（过敏包退，境内可选）：0不支持，1支持 | `` |
| `sell_channel` | body | array | 否 | 售卖方式;0:全渠道手售卖,1:仅指定直播间售卖 | `0` |
| `start_sale_type` | body | number | 否 | 审核通过后上架售卖时间配置:0-立即上架售卖 1-放入仓库 | `0` |
| `delay_rule` | body | object | 否 | 特殊日期延迟发货规则 | `` |
| `  └ enable` | body | boolean | 否 | 是否开启特殊日期延迟发货 | `true` |
| `  └ config_type` | body | string | 否 | 1 时间点；2 时间范围 | `1` |
| `  └ config_value` | body | number | 否 | 特殊日期延迟发货时间最晚发货时间，时间戳，单位秒：当config_type=1时，传时间戳，代表最晚x发货；当config_type=2时，传天数，代表延迟x天发货 | `1673539199` |
| `  └ start_time` | body | number | 否 | 特殊日期延迟发货时间下单开始时间，时间戳，单位秒 | `1643040000` |
| `  └ end_time` | body | number | 否 | 特殊日期延迟发货时间下单结束时间，时间戳，单位秒 | `1672502400` |
| `material_video_id` | body | string | 否 | 主图视频ID，可以先通过https://op.jinritemai.com/docs/api-docs/69/1617接口上传视频，获取审核通过的视频素材ID进行传入 任务需要验证 | `vaaaa` |
| `pickup_method` | body | string | 否 | 提取方式新字段，推荐使用。"0": 普通商品-使用物流发货, "1": 虚拟商品-无需物流与电子交易凭证, "2": 虚拟商品-使用电子交易凭证,  "3": 虚拟商品-充值直连 | `0` |
| `size_info_template_id` | body | number | 否 | 尺码模板ID | `101` |
| `substitute_goods_url` | body | string | 否 | 外部商品url | `https://xxx.xxx.xxx` |
| `sale_channel_type` | body | string | 否 | 销售渠道类型，可选onlineOnly（纯电商，仅在线上售卖）或sameAsOffline（专柜同款，线上线下都有售卖），云零售商家（https://fxg.jinritemai.com/ffa/merchant-growth/cloud-retail）可以设置 | `sameAsOffline` |
| `recruit_info` | body | object | 否 | 招商信息 | `` |
| `  └ recruit_follow_id` | body | string | 否 | 线索ID | `122332` |
| `  └ recruit_type` | body | string | 否 | 招商类型 | `0` |
| `store_id` | body | number | 否 | 门店ID | `103121` |
| `main_product_id` | body | number | 否 | 主商品ID | `3121213` |
| `sale_limit_id` | body | number | 否 | 限售模板ID | `123` |
| `name_prefix` | body | string | 否 | 商品标题前缀推荐 | `钛钢耳饰` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/addV2?app_key=your_appkey_here&method=product.addV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | number | product_id | `product_id` |
| `out_product_id` | number | out_product_id | `out_product_id` |
| `outer_product_id` | string | outer_product_id | `outer_product_id` |
| `create_time` | string | create_time | `create_time` |
| `sku` | array | 1 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 商品创建失败：图片上传错误（sub_code: isv.parameter-invalid:99） | 建议接入素材中心 |
| `20000` | 系统错误 / 商品创建失败: 系统错误（sub_code: isp.service-error:2010001） | 重试 |
| `20000` | 系统错误 / 商品创建失败: 请求超时（sub_code: isp.service-error:2010002） | 重试 |
| `40002` | 缺少必选参数 / 商品创建失败: 缺少参数（sub_code: isv.missing-parameter:2010003） | 请重新进入页面进行补充 |
| `40004` | 非法的参数 / 商品创建失败: 非法参数（sub_code: isv.parameter-invalid:2010004） | 输入正确参数 |
| `40004` | 非法的参数 / 商品创建失败: 无访问权限（sub_code: isv.parameter-invalid:2010005） | 输入正确参数 |
| `50002` | 业务处理失败 / 商品创建失败: 新建商品失败（sub_code: isv.business-failed:2010011） | 检查参数后重试 |
| `50002` | 业务处理失败 / 商品创建失败: 读取失败（sub_code: isv.business-failed:2010013） | 检查参数后重试 |
| `40004` | 非法的参数 / 商品创建失败: 资质类属性必填拒绝（sub_code: isv.parameter-invalid:2010020） | 输入正确参数 |
| `40004` | 非法的参数 / 商品创建失败: 商品状态错误（sub_code: isv.parameter-invalid:2010022） | 输入正确参数 |
| `40004` | 非法的参数 / 商品创建失败: 类目校验（sub_code: isv.parameter-invalid:2010044） | 请重新选择类目进行商品发布 |
| `40004` | 非法的参数 / 商品创建失败: 店铺需要绑定（sub_code: isv.parameter-invalid:2010050） | 完成账号绑定 |
| `40004` | 非法的参数 / 商品创建失败: 类目相关信息过期（sub_code: isv.parameter-invalid:2010053） | 待资质审核通过后再提交 |
| `40002` | 缺少必选参数 / 商品创建失败: 资质不合法（sub_code: isv.missing-parameter:2010101） | 请上传版权页图 |
| `40004` | 非法的参数 / 商品创建失败: 品牌不合法（sub_code: isv.parameter-invalid:2010104） | 检查参数后重试 |
| `50002` | 业务处理失败 / 商品创建失败: 获取类目信息失败（sub_code: isv.business-failed:2010201） | 检查参数后重试 |
| `50002` | 业务处理失败 / 商品创建失败: 调用成功，但填充返回数据时失败,无影响（sub_code: isv.business-failed:2010204） | 无影响，可忽略 |
| `20000` | 系统错误 / 商品创建失败: 查询品牌库失败（sub_code: isp.service-error:2010206） | 重试 |
| `20000` | 系统错误 / 商品创建失败: 查询商家资质失败（sub_code: isp.service-error:2010207） | 重试 |
| `40004` | 非法的参数 / 商品创建失败: 必须支持7天无理由退货（sub_code: isv.parameter-invalid:2010316） | 检查参数后重试 |
| `40002` | 缺少必选参数 / 商品创建失败: 品牌受限（sub_code: isv.missing-parameter:2010317） | 补充参数 |
| `40004` | 非法的参数 / 商品创建失败: 使用的品牌没有授权（sub_code: isv.parameter-invalid:2010319） | 检查参数后重试 |
| `40004` | 非法的参数 / 商品创建失败: 品牌必填（sub_code: isv.parameter-invalid:2010320） | 检查参数后重试 |
| `40002` | 缺少必选参数 / 商品创建失败: 缺少属性（sub_code: isv.missing-parameter:2010321） | 重新进入页面补充 |
| `40004` | 非法的参数 / 商品创建失败: 发布诊断失败（sub_code: isv.parameter-invalid:2010501） | 补充参数 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:4） | 检查参数后重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:7） | 检查参数后重试 |
| `60000` | 触发限流，请稍后重试 / 商品创建失败：接口限流（sub_code: isp.traffic-limited:2010401） | 稍后重试 |
| `50002` | 业务处理失败 / 商品创建失败: 因为店铺受到处罚，限制发品，更多请到商家后台奖惩中心查看（sub_code: isv.business-failed:2010326） | 检查店铺状态后重试 |
| `20000` | 系统错误 / 商品创建失败: 获取类目配置失败（sub_code: isp.service-error:2010202） | 稍后重试 |
| `20000` | 系统错误 / 商品创建失败: 保存素材失败（sub_code: isp.service-error:2010024） | 稍后重试 |
| `50002` | 业务处理失败 / 2010329:商品创建失败: 当前店铺类型下，不支持在该类目发布此品牌商品。您可查看对应“行业管理规范”的入驻方式。请跳转https://zjsms.com/NE7whg4/（sub_code: isv.business-failed:2010329） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010061:商品创建失败: 请求权益信息失败（sub_code: isv.business-failed:2010061） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010063:商品创建失败: 当前店铺在架商品量已达上限，暂无法创建商品，详细规则可查看商品数限额实施细则（sub_code: isv.business-failed:2010063） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010021:商品创建失败: 更新库存数失败: 幂等ID重复（sub_code: isv.business-failed:2010021） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010055:商品创建失败: 因服务器升级，商品价格展示可能异常，请修改价格后重试（sub_code: isv.business-failed:2010055） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010340:商品创建失败: 当前商品使用的品牌未关联当前类目，请切换品牌或者前往商家资质中心补全品牌资质信息，之后再上架商品。（sub_code: isv.business-failed:2010340） | 检查参数后重试 |
| `50002` | 业务处理失败 / 2010304:商品创建失败: 超出测试店铺可创建商品数量上限，请删除未使用商品后再试（sub_code: isv.business-failed:2010304） | 清理无用的商品后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "create_time": "create_time",
    "out_product_id": "out_product_id",
    "outer_product_id": "outer_product_id",
    "product_id": "product_id",
    "sku": [
      {
        "code": "1",
        "out_sku_id": "1",
        "outer_sku_id": "1",
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:99",
  "sub_msg": "商品创建失败：图片上传错误"
}
```

## 备注
