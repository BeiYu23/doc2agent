# product.detail

> 查询商品详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.detail` |
| 中文名 | 查询商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/56 |
| 更新日期 | `2026-09-09` |

## 接口说明

- 文档书: 商品API（版本 V12.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 否 | 商品ID，抖店系统生成，店铺下唯一；长度19位 | `3558192687276554544` |
| `out_product_id` | body | string | 否 | 外部商家编码，商家自定义字段 | `dy001` |
| `show_draft` | body | string | 否 | true：读取草稿数据；false：读取线上数据；不传默认为false | `false` |
| `store_id` | body | string | 否 | 门店ID，不建议小时达一期用，即时零售单店版，无需使用 | `1111420330` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/detail?app_key=your_appkey_here&method=product.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | mixed | 商品ID，抖店系统生成，店铺下唯一；长度19位。 | `3539925204033339668` |
| `product_id_str` | string | 商品ID（字符串类型），抖店系统生成，店铺下唯一；长度19位。 | `3539925204033339668` |
| `out_product_id` | mixed | 【即将废弃】外部商家编码，商家自定义字段。推荐使用，outer_product_id字段 | `133321` |
| `outer_product_id` | string | 外部商家编码，商家自定义字段，支持最多 255个字符 | `dy001` |
| `open_user_id` | mixed | 【已废弃】open应用id | `""` |
| `name` | string | 商品标题，规则：至少输入8个字（16个字符）以上~输入30个字（60个字符）以内。；标题不规范会引起商品下架，影响您的正常销售，详见商品发布规范：https://school.jinritemai.com/doudian/web/article/101800?from=shop_article | `夏季男生白色短袖` |
| `description` | string | 商品详情，最大支持50张图片，单张详情图宽高比不超2000*2000px，大小5M内，仅支持jpg/jpeg/png格式，返回HTML格式；注意：商品详情不规范，会引起商品下架，影响您的正常销售：https://school.jinritemai.com/doudian/web/article/101800?from=shop_article | `<p><img src=\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933\" style=\"max-width:100%;\"/><img src=\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153426724709337920183_dd825b6f3c1bc43ec26faea488447709_sx_1059417_www1080-933\" style=\"max-width:100%;\"/><img src=\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153465487927217040183_d963cc36ef6e66c0cba70e4cb2188f88_sx_436442_www1920-1080\" style=\"max-width:100%;\"/></p>` |
| `delivery_method` | mixed | 承诺发货时间，单位是天; 不传则默认为2天，当presell_type为0或2均只支持传入2；当presell_type为1时支持可选值为: 2、3、5、7、10、15； | `7` |
| `cdf_category` | string | 海南免税，海关限购分类编码，仅海淘商品有值返回。 | `""` |
| `status` | mixed | 商品在店铺中状态: 0-在线；1-下线；2-删除；详见商品状态机：https://op.jinritemai.com/docs/question-docs/92/2070 | `1` |
| `spec_id` | mixed | 商品规格，新增商品是全局唯一，注意：有部分历史存量商品可能存在规格复用 | `1737144307943485` |
| `check_status` | mixed | 商品审核状态: 1-未提交；2-待审核；3-审核通过；4-审核未通过；5-封禁；7-审核通过待上架；详见商品状态机：https://op.jinritemai.com/docs/question-docs/92/2070 | `1` |
| `mobile` | string | 【已废弃】手机号 | `15677775555` |
| `brand_id` | mixed | 【已废弃】品牌id，推荐使用standard_brand_id字段，通过【/brand/list】获取，无品牌id商品返回默认值：596120136； | `596120136` |
| `is_sub_product` | boolean | 是否是组合商品的子商品；true-是，false-不是； | `true` |
| `draft_status` | mixed | 草稿状态；0-无草稿,1-未提审,2-待审核,3-审核通过,4-审核未通过。详见：https://op.jinritemai.com/docs/question-docs/92/2070 | `2` |
| `category_detail` | object | 类目详情；商品类目id可使用【/shop/getShopCategory】查询 | `` |
| `pay_type` | mixed | 【已废弃】支持的支付方式：0货到付款 1在线支付 2两者都支持 | `1` |
| `recommend_remark` | string | 【已废弃】商家推荐语 | `真的很好啊` |
| `extra` | string | 额外信息，如资质 | `{\"category_detail\":{\"first_cid\":20117,\"second_cid\":22139,\"third_cid\":28901,\"fourth_cid\":31800,\"first_cname\":\"本地生活服务\",\"second_cname\":\"餐饮美食卡券\",\"third_cname\":\"甜品/冰淇淋/咖啡/冷饮\",\"fourth_cname\":\"咖啡\",\"is_leaf\":true},\"class_quality\":\"\",\"is_publish\":1,\"quality_opId\":\"7132044312682119463\",\"quality_report\":\"\"}` |
| `is_create` | mixed | 【已废弃】无业务意义 | `【已废弃】` |
| `create_time` | string | 商品创建时间，时间格式：yyyy-mm-dd hh:mm:ss | `2022-07-04 13:29:47` |
| `update_time` | string | 商品更新时间，时间格式：yyyy-mm-dd hh:mm:ss | `2022-07-08T16:29:01+08:00` |
| `pic` | array | 商品主图；最多支持5张图片；仅支持png，jpg，jpeg格式，宽高比例为1:1（至少600*600px），大小5M内 | `["https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933",     "https://p6-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153429136760998540183_e3d0578bd8b499ff9dee11a0fd040070_sx_889253_www3072-3072",     "https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153465665006472060183_1d037ea9f83818829d3a502df6135ae4_sx_280269_www1080-1080"]` |
| `product_format` | string | 【即将废弃】推荐使用product_format_new；属性名称\|属性值 之间用\|分隔, 多组之间用^分开 | `{"货号":"8888"}` |
| `spec_pics` | array | 规格图片 | `` |
| `spec_prices` | array | 商品sku详情 | `` |
| `specs` | array | 规格信息，规格项和规格值 | `` |
| `img` | string | 头图，主图第一张 | `https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933` |
| `presell_type` | mixed | 预售类型，1-全款预售，0-非预售，2-阶梯库存 | `1` |
| `maximum_per_order` | mixed | 单用户下单限购件数 | `5` |
| `limit_per_buyer` | mixed | 单用户累计限购件数 | `5` |
| `minimum_per_order` | mixed | 用户每次下单至少购买的件数 | `1` |
| `quality_list` | array | 资质信息 | `` |
| `logistics_info` | object | 跨境物流信息（仅海淘商品返回） | `` |
| `after_sale_service` | string | 售后服务 | `{"supply_7day_return":"2"}` |
| `price_has_tax` | mixed | 商品价格是否含税 | `0` |
| `appoint_delivery_day` | mixed | 可预约发货天数 | `2` |
| `product_format_new` | string | 类目属性 | `{"1088":[{"Value":0,"Name":"小33学二年级","PropertyId":1088,"PropertyName":"适用学龄段","diy_type":1}],"1319":[{"Value":0,"Name":"1","PropertyId":1319,"PropertyName":"适用地区","diy_type":0}],"1618":[{"Value":0,"Name":"9787218122861","PropertyId":1618,"PropertyName":"ISBN编号","diy_type":0}],"1831":[{"Value":0,"Name":"小学英语看图说话写话二年级","PropertyId":1831,"PropertyName":"书名","diy_type":0}],"2000":[{"Value":34762,"Name":"无","PropertyId":2000,"PropertyName":"作者地区","diy_type":0}],"2229":[{"Value":0,"Name":"1","PropertyId":2229,"PropertyName":"编者","diy_type":0}],"3271":[{"Value":0,"Name":"1","PropertyId":3271,"PropertyName":"出版时间","diy_type":0}],"449":[{"Value":0,"Name":"1","PropertyId":449,"PropertyName":"作者","diy_type":0}],"501":[{"Value":7310,"Name":"否","PropertyId":501,"PropertyName":"是否是套装","diy_type":0}],"855":[{"Value":0,"Name":"陕西人民教育出版社","PropertyId":855,"PropertyName":"出版社名称","diy_type":0}]}` |
| `standard_brand_id` | mixed | 品牌库brand id，原brand_id代表商标关系id | `121354` |
| `market_price` | mixed | 划线价 单位分 | `12000` |
| `discount_price` | mixed | 售卖价 单位分 | `12000` |
| `car_vin_code` | string | 汽车vin码 | `VIN11111111111111` |
| `need_recharge_mode` | boolean | 生活娱乐充值模式 | `false` |
| `account_template_id` | string | 多账号充值账号模板 | `1` |
| `presell_config_level` | mixed | 发货模式：presell_type = 0 现货；presell_type = 2 阶梯；presell_type = 1 && presell_config_level = 0 全款预售；presell_type = 1 && presell_config_level = 1 sku预售；presell_type = 1 && presell_config_level = 2 现货+预售；presell_type = 1 && presell_config_level = 3 新预售 | `2` |
| `delivery_delay_day` | mixed | 现货模式的发货天数；阶梯模式现货部分的发货天数，9999=当日发、1=次日发 | `2` |
| `presell_delay` | mixed | 阶梯模式阶梯部分的发货天数；商品全款预售模式，预售天数 | `4` |
| `poi_resource` | object | 卡券信息 | `` |
| `delay_rule` | object | 特殊日期延迟发货规则 | `` |
| `long_pic_url` | string | 3:4长图url(仅素材中心url有效) | `https://aaa` |
| `sell_channel` | array | 售卖方式;0:全渠道手售卖,1:仅指定直播间售卖 | `[0]` |
| `freight_id` | mixed | 运费模版ID | `123` |
| `material_video_id` | string | 主图视频ID | `Vaaxxaa` |
| `pickup_method` | string | 提取方式新字段，推荐使用。"0": 普通商品-使用物流发货, "1": 虚拟商品-无需物流与电子交易凭证, "2": 虚拟商品-使用电子交易凭证,  "3": 虚拟商品-充值直连 | `0` |
| `size_info_template_id` | mixed | 尺码模板ID | `7102988069296423000` |
| `white_back_ground_pic_url` | string | 白底图url(仅素材中心url有效) | `https://aaa` |
| `sale_channel_type` | string | 销售渠道类型，包括纯电商（onlineOnly）、专柜同款（sameAsOffline），云零售商家（https://fxg.jinritemai.com/ffa/merchant-growth/cloud-retail）可以设置 | `sameAsOffline` |
| `store_id` | mixed | 门店ID | `103121` |
| `main_product_id` | mixed | 主商品ID | `3121213` |
| `sale_limit_id` | mixed | 限售模板ID | `123` |
| `name_prefix` | string | 系统推荐的标题前缀 | `钛钢木质耳饰` |
| `product_type` | mixed | 商品类型，0-普通，3-虚拟，6玉石闪购，7云闪购 | `0` |
| `presell_delivery_type` | mixed | 预售发货方式配置 0-预售结束后xx天发货; 1-支付完成后xx天发货 | `0` |
| `start_sale_type` | mixed | 审核通过后上架售卖时间配置：0-立即上架售卖 1-放入仓库 | `0` |
| `reduce_type` | mixed | 库存扣减方式，1-拍下减库存 2-付款减库存 | `1` |
| `presell_end_time` | string | 预售结束时间，格式2020-02-21 18:54:27，最多支持设置距离当前30天 | `2020-02-21 18:54:27` |
| `weight_value` | string | 重量数值 | `0` |
| `weight_unit` | mixed | 重量单位，0-kg, 1-g | `0` |
| `reference_price_certificate` | object | 参考价凭证 | `` |
| `reference_price` | mixed | 参考价，单位分 | `12300` |
| `quality_inspection_info` | object | 前置质检相关（特定二手商家、特定二手类目使用） | `` |
| `unit_price_info` | object | 单位价格信息 | `` |
| `main_image_three_to_four` | string | 商品主图3:4；最多支持5张图片；宽高比例为3:4 | `[https://p9-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_a9223a677dc42718d1203bd2165e3bf5_sx_89532_www570-760,https://p3-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_cd15cfb47c3091dea24d2f84d17e2cad_sx_975664_www750-1000,https://p6-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_ed6f9c9914a5a6ff444a25afc71313c3_sx_63512_www570-760]` |
| `is_c2b_switch_on` | boolean | 是否支持c2b小程序（特定c2b定制商家使用） | `false` |
| `micro_app_id` | string | 支持c2b定制时的小程序id（特定c2b定制商家使用） | `abcde` |
| `is_auto_charge` | boolean | 是否是自动充值商品 | `false` |
| `spu_id` | mixed | spu_id 大于0代表有挂载spu | `1234` |
| `short_product_name` | string | 导购短标题，短标题可用于物流打单及商品搜索场景，若未填写，则系统将智能生成最优短标题在商详购买页面展示，说明详见：https://school.jinritemai.YOUR_SECRET_KEY?from=shop_article | `好吃牛肉干` |
| `after_sale_service_v2` | object | 售后服务新结构 | `` |
| `format_update_time` | string | 更新时间，和update_time一样，只是格式不同 | `2021-11-23 10:17:48` |
| `sell_num` | mixed | 商品销量 | `123` |
| `product_audit_info` | object | 商品审核结果 | `` |
| `main_pic_3_4` | array | 商品主图3:4；最多支持5张图片；宽高比例为3:4 | `[https://p9-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_a9223a677dc42718d1203bd2165e3bf5_sx_89532_www570-760,https://p3-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_cd15cfb47c3091dea24d2f84d17e2cad_sx_975664_www750-1000,https://p6-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_ed6f9c9914a5a6ff444a25afc71313c3_sx_63512_www570-760]` |
| `shop_category` | object | 店铺装修分类 | `` |
| `name_suffix` | string | 标题后缀 | `36.9度` |
| `use_brand_name` | boolean | 是否勾选使用品牌名 | `false` |
| `new_step_product` | boolean | 新现货+预售商品标识，true-新现货+预售商品 | `true` |
| `is_charity_product` | boolean | 是否公益商品 | `false` |
| `charity_id` | string | 公益项目id | `123` |
| `is_evaluate_opened` | string | 测评模块是否打开 | `false` |
| `custom_property` | object | 定制属性 | `` |
| `default_process_time` | object | 商品默认处理时长 | `` |
| `is_second_hand_digital` | boolean | 是否二手数码(成色机) | `false` |
| `delivery_time_sub_type` | mixed | 发货时间子类型，该值仅在现货发货时效（presellType = 0）下有意义，1 sku维度发货时效，0或者缺省为商品维度发货时效 | `1` |
| `home_install_service_info` | object | 上门安装服务信息 | `` |
| `original_category_detail` | object | 门捷列夫类目详情，临时字段，类目数升级期间使用的字段，主要返回老的类目信息，方便开发者做映射使用，升级结束后字段会下线，下线时间另行通知 | `` |
| `future_category_detail` | object | 标准类目详情（新类目信息）方便开发者做映射使用，升级结束后字段会下线，下线时间另行通知 | `` |
| `category_property_pics` | string | 属性图，如水洗标等，key=属性id | `` |
| `correct_size_suggestion` | object | 偏码建议 | `` |
| `shipping_origin_info` | object | 发货地信息 | `` |
| `food_label_image_url` | string | 食品标签图 | `https://p3-aio.ecombdimg.com/ecom-shop-material/png_m_da821f77ec1a287fb2820969b50733c3_sx_655174_www1080-1080~tplv-qzsgku4lz6-fxg-image:0:q75.avis` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / out_product_id未找到或商品已删除（sub_code: isv.parameter-invalid:4） | 请检查参数后重试 |
| `20000` | 系统错误 / 7:请求失败，请稍后再试（sub_code: isp.service-error:7） | 请检查参数后重试 |
| `40004` | 非法的参数 / 商品不存在或已彻底删除（sub_code: isv.parameter-invalid:2010058） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010401:触发商品操作限流,请稍后再试（sub_code: isv.business-failed:2010401） | 请稍后再试 |
| `20000` | 系统错误 / 2010001:系统异常,请重试（sub_code: isp.service-error:2010001） | 请稍后再试 |
| `20000` | 系统错误 / 2010327:销售属性查询失败（sub_code: isp.service-error:2010327） | 请稍后再试 |
| `20000` | 系统错误 / 2010013:数据查询异常（sub_code: isp.service-error:2010013） | 请稍后再试 |
| `20000` | 系统错误 / 2010321:类目属性查询异常（sub_code: isp.service-error:2010321） | 请稍后再试 |
| `50002` | 业务处理失败 / 2010004:商品参数错误（sub_code: isv.business-failed:2010004） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010203:获取商品信息失败（sub_code: isv.business-failed:2010203） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 110103023:商品ID不合法（sub_code: isv.business-failed:110103023） | 110103023:商品ID不合法 |

## 响应示例

成功：

```json
{
  "data": {
    "account_template_id": "1",
    "after_sale_service": "{\"supply_7day_return\":\"2\"}",
    "after_sale_service_v2": {
      "is_large_product": "1",
      "three_guarantees": {
        "duration": "180",
        "service_type": "1"
      }
    },
    "appoint_delivery_day": "2",
    "brand_id": "596120136",
    "car_vin_code": "VIN11111111111111",
    "category_detail": {
      "first_cid": "20117",
      "first_cname": "本地生活服务",
      "fourth_cid": "31800",
      "fourth_cname": "咖啡",
      "second_cid": "22139",
      "second_cname": "餐饮美食卡券",
      "third_cid": "28901",
      "third_cname": "甜品/冰淇淋/咖啡/冷饮"
    },
    "category_property_pics": {},
    "cdf_category": "\"\"",
    "charity_id": "123",
    "check_status": "1",
    "correct_size_suggestion": {
      "size": "0.5",
      "value_id": "2"
    },
    "create_time": "2022-07-04 13:29:47",
    "custom_property": {
      "customPropertyGroups": [
        {
          "name": "加工方式",
          "propertyDetail": [
            {
              "extra_info": {
                "process_time": "600"
              },
              "name": "宰杀"
            }
          ]
        }
      ]
    },
    "default_process_time": {
      "value": "处理时长值"
    },
    "delay_rule": {
      "config_type": "1",
      "config_value": "1673539199",
      "enable": "true",
      "end_time": "1672502400",
      "rule_scope": "1",
      "start_time": "1643040000"
    },
    "delivery_delay_day": "2",
    "delivery_method": "7",
    "delivery_time_sub_type": "1",
    "description": "<p><img src=\\\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933\\\" style=\\\"max-width:100%;\\\"/><img src=\\\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153426724709337920183_dd825b6f3c1bc43ec26faea488447709_sx_1059417_www1080-933\\\" style=\\\"max-width:100%;\\\"/><img src=\\\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153465487927217040183_d963cc36ef6e66c0cba70e4cb2188f88_sx_436442_www1920-1080\\\" style=\\\"max-width:100%;\\\"/></p>",
    "discount_price": "12000",
    "draft_status": "2",
    "extra": "{\\\"category_detail\\\":{\\\"first_cid\\\":20117,\\\"second_cid\\\":22139,\\\"third_cid\\\":28901,\\\"fourth_cid\\\":31800,\\\"first_cname\\\":\\\"本地生活服务\\\",\\\"second_cname\\\":\\\"餐饮美食卡券\\\",\\\"third_cname\\\":\\\"甜品/冰淇淋/咖啡/冷饮\\\",\\\"fourth_cname\\\":\\\"咖啡\\\",\\\"is_leaf\\\":true},\\\"class_quality\\\":\\\"\\\",\\\"is_publish\\\":1,\\\"quality_opId\\\":\\\"7132044312682119463\\\",\\\"quality_report\\\":\\\"\\\"}",
    "food_label_image_url": "https://p3-aio.ecombdimg.com/ecom-shop-material/png_m_da821f77ec1a287fb2820969b50733c3_sx_655174_www1080-1080~tplv-qzsgku4lz6-fxg-image:0:q75.avis",
    "format_update_time": "2021-11-23 10:17:48",
    "freight_id": "123",
    "future_category_detail": {
      "first_cid": "1000007740",
      "first_cname": "黄金珠宝玉石",
      "fourth_cid": "1000008663",
      "fourth_cname": "裸石",
      "second_cid": "1000007878",
      "second_cname": "合成宝石",
      "third_cid": "1000007926",
      "third_cname": "合成钻石"
    },
    "home_install_service_info": {
      "home_install_service_template_id": "12345"
    },
    "img": "https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933",
    "is_auto_charge": "false",
    "is_c2b_switch_on": "false",
    "is_charity_product": "false",
    "is_create": "【已废弃】",
    "is_evaluate_opened": "false",
    "is_second_hand_digital": "false",
    "is_sub_product": "true",
    "limit_per_buyer": "5",
    "logistics_info": {
      "brand_country_id": "123",
      "customs_clear_type": "1",
      "net_weight_qty": "100",
      "origin_country_id": "123",
      "source_country_id": "123",
      "tax_payer": "0"
    },
    "long_pic_url": "https://aaa",
    "main_image_three_to_four": "[https://p9-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_a9223a677dc42718d1203bd2165e3bf5_sx_89532_www570-760,https://p3-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_cd15cfb47c3091dea24d2f84d17e2cad_sx_975664_www750-1000,https://p6-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_ed6f9c9914a5a6ff444a25afc71313c3_sx_63512_www570-760]",
    "main_pic_3_4": "[https://p9-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_a9223a677dc42718d1203bd2165e3bf5_sx_89532_www570-760,https://p3-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_cd15cfb47c3091dea24d2f84d17e2cad_sx_975664_www750-1000,https://p6-aio.ecombdimg.com/obj/ecom-shop-material/rgKVRhPW_m_ed6f9c9914a5a6ff444a25afc71313c3_sx_63512_www570-760]",
    "main_product_id": "3121213",
    "market_price": "12000",
    "material_video_id": "Vaaxxaa",
    "maximum_per_order": "5",
    "micro_app_id": "abcde",
    "minimum_per_order": "1",
    "mobile": "15677775555",
    "name": "夏季男生白色短袖",
    "name_prefix": "钛钢木质耳饰",
    "name_suffix": "36.9度",
    "need_recharge_mode": "false",
    "new_step_product": "true",
    "open_user_id": "\"\"",
    "original_category_detail": {
      "first_cid": "20117",
      "first_cname": "本地生活服务",
      "fourth_cid": "31800",
      "fourth_cname": "咖啡",
      "second_cid": "22139",
      "second_cname": "餐饮美食卡券",
      "third_cid": "28901",
      "third_cname": "甜品/冰淇淋/咖啡/冷饮"
    },
    "out_product_id": "133321",
    "outer_product_id": "dy001",
    "pay_type": "1",
    "pic": "[\"https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933\",     \"https://p6-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153429136760998540183_e3d0578bd8b499ff9dee11a0fd040070_sx_889253_www3072-3072\",     \"https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153465665006472060183_1d037ea9f83818829d3a502df6135ae4_sx_280269_www1080-1080\"]",
    "pickup_method": "0",
    "poi_resource": {
      "code_type": "1",
      "condition": "仅可在XXX门店范围使用",
      "coupon_return_methods": "[1]",
      "notification": "发码后可核销使用",
      "poi_lib_id": "3526522",
      "service_num": "86668888",
      "total_can_use_count": "1",
      "valid_days": "7"
    },
    "presell_config_level": "2",
    "presell_delay": "4",
    "presell_delivery_type": "0",
    "presell_end_time": "2020-02-21 18:54:27",
    "presell_type": "1",
    "price_has_tax": "0",
    "product_audit_info": {
      "material_audit_reason": [
        {
          "material_type": "0",
          "reasons": "[\"白底图不符合规范\",\"白底图太黑了\"]"
        }
      ],
      "material_audit_status": {}
    },
    "product_format": "{\"货号\":\"8888\"}",
    "product_format_new": "{\"1088\":[{\"Value\":0,\"Name\":\"小33学二年级\",\"PropertyId\":1088,\"PropertyName\":\"适用学龄段\",\"diy_type\":1}],\"1319\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":1319,\"PropertyName\":\"适用地区\",\"diy_type\":0}],\"1618\":[{\"Value\":0,\"Name\":\"9787218122861\",\"PropertyId\":1618,\"PropertyName\":\"ISBN编号\",\"diy_type\":0}],\"1831\":[{\"Value\":0,\"Name\":\"小学英语看图说话写话二年级\",\"PropertyId\":1831,\"PropertyName\":\"书名\",\"diy_type\":0}],\"2000\":[{\"Value\":34762,\"Name\":\"无\",\"PropertyId\":2000,\"PropertyName\":\"作者地区\",\"diy_type\":0}],\"2229\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":2229,\"PropertyName\":\"编者\",\"diy_type\":0}],\"3271\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":3271,\"PropertyName\":\"出版时间\",\"diy_type\":0}],\"449\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":449,\"PropertyName\":\"作者\",\"diy_type\":0}],\"501\":[{\"Value\":7310,\"Name\":\"否\",\"PropertyId\":501,\"PropertyName\":\"是否是套装\",\"diy_type\":0}],\"855\":[{\"Value\":0,\"Name\":\"陕西人民教育出版社\",\"PropertyId\":855,\"PropertyName\":\"出版社名称\",\"diy_type\":0}]}",
    "product_id": "3539925204033339668",
    "product_id_str": "3539925204033339668",
    "product_type": "0",
    "quality_inspection_info": {
      "agency": "123",
      "certificate_code": "abc",
      "mode": "1",
      "supported": "false"
    },
    "quality_list": [
      {
        "quality_attachments": [
          {
            "media_type": "1",
            "url": "http://www.byted***.com/YYYY"
          }
        ],
        "quality_key": "3457***9470978",
        "quality_name": "进货凭证"
      }
    ],
    "recommend_remark": "真的很好啊",
    "reduce_type": "1",
    "reference_price": "12300",
    "reference_price_certificate": {
      "certificate_type": "1",
      "certificate_urls": "http://www."
    },
    "sale_channel_type": "sameAsOffline",
    "sale_limit_id": "123",
    "sell_channel": "[0]",
    "sell_num": "123",
    "shipping_origin_info": {
      "shipping_origin_id": "12345",
      "shipping_origin_type": "1"
    },
    "shop_category": {
      "leaf_category_ids": "123"
    },
    "short_product_name": "好吃牛肉干",
    "size_info_template_id": "7102988069296423000",
    "spec_id": "1737144307943485",
    "spec_pics": [
      {
        "pic": "temai/b637513c50b994f4c89de56a17886caca5d6569awww800-800",
        "spec_detail_id": "1695459998447656"
      }
    ],
    "spec_prices": [
      {
        "SkuServiceQuotation": {
          "extra": "\"\"",
          "install_service_assembly_fee": "12300",
          "provider_id": "1124124",
          "service_pricing_prop": "{}",
          "service_quotation_id": "123124",
          "service_template_id": "123412"
        },
        "barcodes": "111111",
        "cargo_info": {
          "cargo_id": "777777777777777",
          "source_type": "1"
        },
        "code": "aaa",
        "commit_code": "3000",
        "customs_report_info": {
          "bar_code": "-",
          "first_measure_qty": "1",
          "first_measure_unit": "-",
          "g_model": "-",
          "hs_code": "1564564",
          "report_brand_name": "-",
          "report_name": "-",
          "second_measure_qty": "1",
          "second_measure_unit": "-",
          "unit": "-",
          "usage": "-"
        },
        "delivery_infos": [
          {
            "info_type": "weight",
            "info_unit": "当info_type=weight时，支持mg,g,kg三种类型",
            "info_value": "100"
          }
        ],
        "gift_suit_detail": [
          {
            "name": {
              "unit": "空",
              "value": "开心果"
            },
            "net_content": {
              "unit": "g",
              "value": "20"
            },
            "quantity": {
              "unit": "袋",
              "value": "5"
            },
            "total_net_content": {
              "unit": "g",
              "value": "100"
            }
          }
        ],
        "gold_process_charge": "12300",
        "lock_step_stock_num": "1",
        "lock_stock_num": "1",
        "merchant_cargo_info": [
          {
            "merchant_cargo_id": "123",
            "merchant_cargo_num": "123",
            "merchant_cargo_type": "1"
          }
        ],
        "multi_time_stocks": [
          {
            "stock_num": "500",
            "time_desc": "5天内发",
            "time_type": "5"
          }
        ],
        "operator": "商家",
        "out_sku_id": "0",
        "outer_sku_id": "dy001-1",
        "presell_delay": "5",
        "price": "102",
        "prom_step_stock_num": "0",
        "prom_stock_num": "0",
        "promotion_step_stock_num": "0",
        "promotion_stock_num": "0",
        "reason": "商家下架",
        "sell_properties": [
          {
            "perperty_id": "0",
            "property_name": "颜色",
            "remark": "非常黄",
            "value_id": "12345678910",
            "value_name": "黄色",
            "value_spec_detail_id": "123123123123"
          }
        ],
        "ship_time": "\"2025-09-01\"",
        "ship_time_type": "2",
        "sku_classification_type": "\"main_sale_single_product\"",
        "sku_id": "1737398770243598",
        "sku_picture_url": "[\"img_url\"]",
        "sku_status": "true",
        "sku_type": "0",
        "spec_detail_id1": "1695459998494734",
        "spec_detail_id2": "1695459998494734",
        "spec_detail_id3": "0",
        "spec_detail_ids": "[1695459998494734,1695459998494766]",
        "spec_model_code": "[\"123\"]",
        "step_stock_num": "0",
        "stock_num": "13",
        "stock_num_map": {},
        "supplier_id": "123",
        "tax_exemption_sku_info": {
          "is_suit": "1",
          "suit_num": "10",
          "volume": "100"
        }
      }
    ],
    "specs": [
      {
        "id": "1713023986705415",
        "is_leaf": "0",
        "name": "颜色",
        "pid": "1713023986705415",
        "property_id": "123",
        "spec_id": "1713023983665214",
        "values": [
          {
            "extra": {
              "cpv_path": [
                {
                  "cpid": "1234",
                  "cpvid": "123"
                }
              ],
              "measure_info": {
                "template_id": "234",
                "values": [
                  {
                    "module_id": "123",
                    "prefix": "-",
                    "suffix": "\"\"",
                    "unit_id": "2",
                    "unit_name": "g",
                    "value": "10"
                  }
                ]
              }
            },
            "id": "1695459998447656",
            "is_leaf": "1",
            "name": "红色",
            "pid": "1695459998447640",
            "spec_id": "1713023983665214",
            "status": "1",
            "value_id": "12"
          }
        ]
      }
    ],
    "spu_id": "1234",
    "standard_brand_id": "121354",
    "start_sale_type": "0",
    "status": "1",
    "store_id": "103121",
    "unit_price_info": {
      "price_rule_type": "1"
    },
    "update_time": "2022-07-08T16:29:01+08:00",
    "use_brand_name": "false",
    "weight_unit": "0",
    "weight_value": "0",
    "white_back_ground_pic_url": "https://aaa"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4",
  "sub_msg": "out_product_id未找到或商品已删除"
}
```

## 备注
