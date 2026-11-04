# 发货时效规则预览

> product.calDelayShipTimeForOpen — 发货时效规则预览

| 元信息 | 值 |
| --- | --- |
| 中文名 | 发货时效规则预览 |
| 文档地址 | `/docs/doudian/product/product-product-calDelayShipTimeForOpen` |
| 接口 ID | `doudian.product.product.calDelayShipTimeForOpen` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/calDelayShipTimeForOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8066 |
| 更新日期 | `2026-01-29` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | mixed | 否 | 类目id | `0` |
| `presell_end_time` | body | string | 否 | 预售结束时间 | `""` |
| `delay_rule` | body | object | 否 | 商品维度 延迟发货配置 | `` |
| `  └ end_time` | body | mixed | 否 | 商家配置的结束时间 | `0` |
| `  └ start_time` | body | mixed | 否 | 商家配置的开始时间 | `0` |
| `  └ config_type` | body | mixed | 否 | 配置类型 | `0` |
| `  └ config_value` | body | mixed | 否 | 配置值 | `0` |
| `  └ rule_scope` | body | mixed | 否 | 规则生效范围 | `0` |
| `  └ enable` | body | boolean | 否 | 是否开启 | `false` |
| `presell_type` | body | mixed | 否 | 预售类型 | `0` |
| `pickup_method` | body | string | 否 | "0": 普通商品-使用物流发货, "1": 虚拟商品-无需物流与电子交易凭证, "2": 虚拟商品-使用电子交易凭证,  "3": 虚拟商品-充值直连 | `""` |
| `is_mass_auction_product` | body | boolean | 否 | 是否大众拍卖商品 | `false` |
| `product_id` | body | mixed | 否 | 商品id | `0` |
| `presell_delay` | body | mixed | 否 | 预售结束后几天发货 | `0` |
| `selected_multi_times` | body | array | 否 | 选择的时效 新阶梯 | `[]` |
| `is_c2b_switch_on` | body | boolean | 否 | 是否打开c2b定制商品开关 | `false` |
| `presell_config_level` | body | mixed | 否 | 预售类型 0 全款预售 1SKU预售 2时效SKU现货+预售  3时效SKU预售 | `0` |
| `delivery_delay_day` | body | mixed | 否 | 承诺发货时间 | `0` |
| `presell_delivery_type` | body | mixed | 否 | 0 预售结束后发货  1支付完成后发货 | `0` |
| `spec_prices_v2` | body | array | 否 | 新sku字段 时效SKU | `` |
| `  └ spec_model_code` | body | array | 否 | 规格型号编码 | `[]` |
| `  └ cargo` | body | object | 否 | 绑定货品（如果传0 0 表示解绑） | `` |
| `    └ cargo_id` | body | string | 否 | cargo_id | `""` |
| `    └ source_type` | body | mixed | 否 | source_type | `0` |
| `  └ out_sku_id` | body | mixed | 否 | 外部sku_id-i64 | `0` |
| `  └ sell_properties` | body | array | 否 | 销售属性（逐步替代specDetailId1、2、3，过渡期互相兼容，大于三级规格时只能用sellProperty）。 | `` |
| `    └ property_name` | body | string | 否 | property_name | `""` |
| `    └ measurement` | body | object | 否 | 度量衡信息 | `` |
| `      └ measure_unit_id` | body | mixed | 否 | 单位id，与类目属性应该保持一致 | `0` |
| `      └ measure_unit` | body | string | 否 | 单位名字（g或克等） | `""` |
| `      └ value` | body | string | 否 | 输入值 | `""` |
| `    └ value_id` | body | mixed | 否 | value_id | `0` |
| `    └ remark` | body | string | 否 | 备注 | `""` |
| `    └ property_id` | body | mixed | 否 | property_id | `0` |
| `    └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `      └ template_id` | body | mixed | 否 | 度量衡模板id | `0` |
| `      └ values` | body | array | 否 | 度量衡内容 | `` |
| `        └ suffix` | body | string | 否 | 后缀 | `""` |
| `        └ extra` | body | string | 否 | 自定义度量衡扩展信息 | `{}` |
| `        └ value_id` | body | mixed | 否 | 值id | `0` |
| `        └ suffix_id` | body | mixed | 否 | 后缀id | `0` |
| `        └ value` | body | string | 否 | 值内容 | `""` |
| `        └ unit_name` | body | string | 否 | 度量衡单位名称 | `""` |
| `        └ prefix` | body | string | 否 | 前缀 | `""` |
| `        └ prefix_id` | body | mixed | 否 | 前缀id | `0` |
| `        └ value_required` | body | boolean | 否 | 是否必填 | `false` |
| `        └ unit_id` | body | mixed | 否 | 度量衡单位id | `0` |
| `        └ module_id` | body | mixed | 否 | 模块id | `0` |
| `      └ extra` | body | string | 否 | 自定义度量衡扩展信息 | `{}` |
| `    └ value_spec_detail_id` | body | mixed | 否 | 规格值detailId，支持3级以上多规格，代替原specDetailId123 | `0` |
| `    └ cpv_path` | body | array | 否 | 销售属性值路径 | `` |
| `      └ cpid` | body | mixed | 否 | cpid | `0` |
| `      └ cpvid` | body | mixed | 否 | cpvid | `0` |
| `    └ value_name` | body | string | 否 | value_name | `""` |
| `  └ supplier_id` | body | string | 否 | 供应商编码 | `""` |
| `  └ id` | body | mixed | 否 | skuId,支持open基于skuId修改sku信息 | `0` |
| `  └ stock_num_map` | body | string | 否 | 仓ID -> 库存数量 | `{}` |
| `  └ service_quotation` | body | object | 否 | sku服务报价信息 | `` |
| `    └ provider_id` | body | string | 否 | 供应商id | `""` |
| `    └ service_template_id` | body | string | 否 | 所属模版id | `""` |
| `    └ extra` | body | string | 否 | 扩展信息 | `""` |
| `    └ service_quotation_id` | body | string | 否 | sku粒度的服务商品信息 服务报价id | `""` |
| `  └ spec_value_lib_id` | body | mixed | 否 | 懂车帝商品规格值id | `0` |
| `  └ ignore_price_update` | body | boolean | 否 | 忽略价格更新 | `false` |
| `  └ customs_report_info` | body | object | 否 | 海关申报要素 | `` |
| `    └ second_measure_unit` | body | string | 否 | 法定第二计量单位 | `""` |
| `    └ unit` | body | string | 否 | 售卖单位 | `""` |
| `    └ report_brand_name` | body | string | 否 | 品牌 | `""` |
| `    └ g_model` | body | string | 否 | 规格型号 | `""` |
| `    └ bar_code` | body | string | 否 | 条形码 | `""` |
| `    └ first_measure_qty` | body | string | 否 | 法定第一计量数量 | `0` |
| `    └ second_measure_qty` | body | string | 否 | 法定第二计量数量 | `0` |
| `    └ usage` | body | string | 否 | 用途 | `""` |
| `    └ first_measure_unit` | body | string | 否 | 法定第一计量单位 | `""` |
| `    └ hs_code` | body | string | 否 | 海关代码 | `""` |
| `    └ report_name` | body | string | 否 | 品名 | `""` |
| `  └ price` | body | mixed | 否 | price | `0` |
| `  └ delivery_infos` | body | array | 否 | SKU物流信息 | `` |
| `    └ info_unit` | body | string | 否 | 信息计量单位 | `""` |
| `    └ info_value` | body | string | 否 | 信息值 | `""` |
| `    └ info_type` | body | string | 否 | 物流采集信息 信息类型 | `""` |
| `  └ spec_detail_name2` | body | string | 否 | 二级规格值名称，已废弃，open对接不再使用 | `""` |
| `  └ sku_classification_type` | body | string | 否 | sku分类信息 | `""` |
| `  └ package_sku` | body | array | 否 | 组套信息 | `` |
| `    └ sku_id` | body | mixed | 否 | sku_id | `0` |
| `    └ stock_type` | body | mixed | 否 | stock_type | `0` |
| `    └ category_leaf_id` | body | mixed | 否 | 叶子类目id | `0` |
| `    └ settlement_ratio` | body | mixed | 否 | 子品结算分摊比例 | `0` |
| `    └ extra_info` | body | object | 否 | 扩展信息，受选项的控制 | `` |
| `      └ pic` | body | array | 否 | 商品主图，1—5张 | `` |
| `        └ url` | body | string | 否 | url | `""` |
| `        └ process_info` | body | object | 否 | process_info | `` |
| `          └ origin_url` | body | string | 否 | origin_url | `""` |
| `          └ process_type` | body | array | 否 | process_type | `[]` |
| `        └ pic_type` | body | mixed | 否 | 图片类型 | `0` |
| `      └ self_sell_stock_num` | body | mixed | 否 | 自售库存 | `0` |
| `      └ quality_list` | body | array | 否 | 商品资质 | `` |
| `        └ quality_attachments` | body | array | 否 | 资质附件 | `` |
| `        └ quality_content_name` | body | string | 否 | 资质名 | `""` |
| `        └ quality_name` | body | string | 否 | 资质种类名称 | `""` |
| `        └ quality_id` | body | mixed | 否 | 资质id 复用 | `0` |
| `        └ quality_key` | body | string | 否 | 资质种类key | `""` |
| `      └ bind_cargo_info` | body | object | 否 | 国内货品信息 | `` |
| `        └ delivery_type_options` | body | array | 否 | 可选发发货模式类型 | `[]` |
| `        └ cargo_name` | body | string | 否 | cargo_name | `""` |
| `        └ cost_price` | body | mixed | 否 | 货品价格 | `0` |
| `        └ disable_stock` | body | boolean | 否 | 是否禁止编辑库存 | `false` |
| `        └ cargo_type` | body | mixed | 否 | 货品类型 | `0` |
| `        └ img_urls` | body | array | 否 | 货品图片 | `[]` |
| `        └ tags` | body | array | 否 | 货品标签 | `[]` |
| `        └ cargo_id` | body | mixed | 否 | 货品id | `0` |
| `        └ need_validate_price` | body | boolean | 否 | 是否需要校验价格 | `false` |
| `        └ stock` | body | mixed | 否 | 货品库存 | `0` |
| `      └ main_image_three_to_four` | body | array | 否 | 商品主图3:4，1—5张 | `` |
| `        └ url` | body | string | 否 | url | `""` |
| `        └ pic_type` | body | mixed | 否 | pic_type | `0` |
| `        └ process_info` | body | object | 否 | process_info | `` |
| `          └ origin_url` | body | string | 否 | origin_url | `""` |
| `          └ process_type` | body | array | 否 | process_type | `[]` |
| `    └ combo_num` | body | mixed | 否 | combo_num | `0` |
| `    └ stock_num` | body | mixed | 否 | stock_num | `0` |
| `    └ sell_properties` | body | array | 否 | 销售属性 | `` |
| `      └ value_spec_detail_id` | body | mixed | 否 | 规格值detailId，支持3级以上多规格，代替原specDetailId123 | `0` |
| `      └ property_name` | body | string | 否 | property_name | `""` |
| `      └ cpv_path` | body | array | 否 | 销售属性值路径 | `` |
| `        └ cpvid` | body | mixed | 否 | cpvid | `0` |
| `        └ cpid` | body | mixed | 否 | cpid | `0` |
| `      └ remark` | body | string | 否 | 备注 | `""` |
| `      └ property_id` | body | mixed | 否 | property_id | `0` |
| `      └ measurement` | body | object | 否 | 度量衡信息 | `` |
| `        └ measure_unit_id` | body | mixed | 否 | 单位id，与类目属性应该保持一致 | `0` |
| `        └ value` | body | string | 否 | 输入值 | `""` |
| `        └ measure_unit` | body | string | 否 | 单位名字（g或克等） | `""` |
| `      └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `        └ extra` | body | string | 否 | 自定义度量衡扩展信息 | `{}` |
| `        └ values` | body | array | 否 | 度量衡内容 | `` |
| `        └ template_id` | body | mixed | 否 | 度量衡模板id | `0` |
| `      └ value_name` | body | string | 否 | value_name | `""` |
| `      └ value_id` | body | mixed | 否 | value_id | `0` |
| `    └ price` | body | mixed | 否 | sku实时价格 | `0` |
| `    └ short_name` | body | string | 否 | short_name | `""` |
| `    └ pic_url` | body | string | 否 | 图片url | `""` |
| `    └ ori_price` | body | mixed | 否 | ori_price | `0` |
| `    └ sub_sku_id` | body | mixed | 否 | sub_sku_id | `0` |
| `    └ sub_product_id` | body | mixed | 否 | sub_product_id | `0` |
| `  └ spec_detail_name1` | body | string | 否 | 一级规格值名称，已废弃，open对接不再使用 | `""` |
| `  └ imei_num` | body | mixed | 否 | IMEI数量 | `0` |
| `  └ copied_sku_id` | body | mixed | 否 | 复制创建时，记录原商品skuId | `0` |
| `  └ quantity_info` | body | object | 否 | 外卖份量信息 | `` |
| `    └ unit_prefix` | body | string | 否 | unit_prefix | `""` |
| `    └ unit_desc` | body | string | 否 | unit_desc | `""` |
| `    └ value` | body | mixed | 否 | value | `0` |
| `    └ unit_name` | body | array | 否 | unit_name | `[]` |
| `  └ tax_exemption_sku_info` | body | object | 否 | 海南免税：Sku 信息 | `` |
| `    └ volume` | body | mixed | 否 | 净含量 | `0` |
| `    └ suit_num` | body | mixed | 否 | 套装数量 | `0` |
| `    └ is_suit` | body | mixed | 否 | 是否套装（0 否 1 是） | `0` |
| `  └ outer_sku_id` | body | string | 否 | 外部sku_id-string | `""` |
| `  └ supply_price` | body | mixed | 否 | 供货价,单位：分，nil代表不修改，0代表清空 | `0` |
| `  └ multi_time_stocks` | body | array | 否 | 时效库存明细 | `` |
| `    └ stock_num` | body | mixed | 否 | 库存数 | `0` |
| `    └ time_desc` | body | string | 否 | 时效描述 | `""` |
| `    └ time_type` | body | mixed | 否 | 时效类型 | `0` |
| `  └ barcodes` | body | array | 否 | 条码 | `[]` |
| `  └ product_code` | body | object | 否 | SKU产品编码 | `` |
| `    └ code` | body | string | 否 | 二维码码值 | `""` |
| `  └ spec_detail_name3` | body | string | 否 | 三级规格值名称，已废弃，open对接不再使用 | `""` |
| `  └ gold_process_charge` | body | mixed | 否 | 黄金加工费，单位：分，nil代表不修改 | `0` |
| `  └ sku_status` | body | boolean | 否 | sku状态是否有效，true上架 false下架 | `false` |
| `  └ presell_delay` | body | mixed | 否 | SKU维度预售发货延迟时间 | `0` |
| `  └ sku_type` | body | mixed | 否 | 库存类型 | `0` |
| `  └ step_stock_num` | body | mixed | 否 | 阶梯库存数 | `0` |
| `  └ stock_num` | body | mixed | 否 | stock_num | `0` |
| `  └ code` | body | string | 否 | code | `""` |
| `  └ batch_stocks` | body | array | 否 | 批次库存 | `` |
| `    └ out_warehouse_id` | body | string | 否 | 外部仓id，仅区域库存模式填写 | `""` |
| `    └ batch_stock_items` | body | array | 否 | 批次库存项 | `` |
| `      └ stock_num` | body | mixed | 否 | 库存数 | `0` |
| `      └ unique_id` | body | string | 否 | 唯一码 | `""` |
| `      └ batch_type` | body | mixed | 否 | 批次类型：0为时效 1为唯一码 | `0` |
| `product_type` | body | mixed | 否 | 商品类型 | `0` |
| `open_logistics_info` | body | object | 否 | 跨境：物流信息 | `` |
| `  └ customs_clear_type` | body | mixed | 否 | 通关模式，1BBC 2BC 3邮关 | `0` |
| `  └ origin_country_id` | body | mixed | 否 | 原产国id | `0` |
| `  └ source_country_id` | body | mixed | 否 | 货源国id | `0` |
| `  └ cross_warehouse_id` | body | string | 否 | 商家仓id | `""` |
| `  └ tax_payer` | body | mixed | 否 | 税金承担方，0商家承担，1用户承担 | `0` |
| `  └ net_weight_qty` | body | string | 否 | 商品净重 | `0` |
| `  └ brand_country_id` | body | mixed | 否 | 品牌所在地id | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/calDelayShipTimeForOpen?app_key=your_appkey_here&method=product.calDelayShipTimeForOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `not_can_calculate_code` | mixed | 不能计算发货时效的错误码 | `0` |
| `not_can_calculate_msg` | string | 不能计算发货时效的错误文案 | `""` |
| `delay_ship_time_tip` | string | 发货时效计算说明文案 | `""` |
| `delay_ship_time_results` | array | 发货时效计算结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "delay_ship_time_results": [
      {
        "delay_ship_time_desc_items": [
          {
            "payment_period": "\"\"",
            "ship_time_desc": "\"\"",
            "ship_time_rule_desc": "\"\""
          }
        ],
        "delay_ship_time_desc_title": "\"\""
      }
    ],
    "delay_ship_time_tip": "\"\"",
    "not_can_calculate_code": "0",
    "not_can_calculate_msg": "\"\""
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
