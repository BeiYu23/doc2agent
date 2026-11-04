# 更新备案

> crossBorder.UpdateProductRecord — 更新备案

| 元信息 | 值 |
| --- | --- |
| 中文名 | 更新备案 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-crossBorder-UpdateProductRecord` |
| 接口 ID | `doudian.cross-border.crossBorder.UpdateProductRecord` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/UpdateProductRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6248 |
| 更新日期 | `2024-10-10` |

## 接口说明

- 文档书: 跨境API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `record_id` | body | string | 是 | 备案ID，唯一 | `7034043070463115533` |
| `customs_clear_type` | body | mixed | 否 | 清关方式 1: 保税备货 2: 直购进口 保税备货：跨境电商企业通过集中海外采购，商品整批提前备货至中国大陆保税仓，当消费者网上下单后，将包裹以1210保税电商方式办理海关清关手续，直接从国内保税仓库配送至中国大陆境内消费者； 直购进口：BC业务模式，海关进出口管理模式：当消费者网上下单后，跨境电商企业将包裹通过9610直购进口方式办理海关清关手续，并派送至中国大陆境内消费者 | `2` |
| `brand_name` | body | string | 否 | 品牌名称 请以注册商标名称为准； 填写商品品牌中外文，顺序应先外文后中文，如：Nutrilon荷兰牛栏； “品牌名称”字符串长度不能超过50。 | `测试品牌` |
| `record_name` | body | string | 否 | 备案品名 建议填写商品的品牌+品名+规格，保税模式下应当与账册申报名称一致； 品名应当包含具有通用的可识别产品特性的中文表述词。例如：乐事薯条番茄牛肉烘烤味250克/袋。 该商品名称中，乐事为品牌，薯条为通用说明，250克/袋装为规格。 “备案品名”字符串长度不能超过250。 | `测试衬衫白色L码` |
| `purpose` | body | string | 否 | 按商品用途分类，如食品用品、衣着用品、日用品、文化用品、家用电器、保健食品、宠粮饲料等； 功能用途 字符串长度不能超过30。 | `衣着用品` |
| `pack_type` | body | string | 否 | 包装类型 按包装材料划分的最小销售单位的外包装，如纸质包装、金属包装、塑料包装、玻璃包装等； “包装类型”字符串长度不能超过30。 | `塑料包装` |
| `is_4pl` | body | mixed | 否 | 备案类型:  1-4PL，2-3PL 3PL:未订购官方供应链服务的备案类型 4PL:已订购官方供应链服务的备案类型 说明：如果Is_4pl、CustomsCode、SpCode、WarehouseCode任意一个字段变更，必须将这四个字段一起传过来，否则返回参数错误。 | `1` |
| `customs_code` | body | string | 否 | 清关口岸编码，以备案基础数据接口返回的数据为准 说明：如果Is_4pl、CustomsCode、SpCode、WarehouseCode任意一个字段变更，必须将这四个字段一起传过来，否则返回参数错误。 | `0127` |
| `sp_code` | body | string | 否 | 服务商编码，以备案基础数据接口返回的数据为准 说明：如果Is_4pl、CustomsCode、SpCode、WarehouseCode任意一个字段变更，必须将这四个字段一起传过来，否则返回参数错误。 | `ZZJC` |
| `warehouse_code` | body | string | 否 | 仓库编码，以备案基础数据接口返回的数据为准 说明：如果Is_4pl、CustomsCode、SpCode、WarehouseCode任意一个字段变更，必须将这四个字段一起传过来，否则返回参数错误。 | `4PLWMSTESTBBC1` |
| `origin_country_customs_code` | body | string | 否 | 原产国编码 进口商品的生产或制造的国家(地区)编码，填写海关3 位国别编码，参照「BBC&BC导入模板.xlsx」【国家列表】sheet。 | `116` |
| `origin_country_area` | body | string | 否 | 原产国具体地区 1.原产国地区，为日本时可传值，参照「BBC&BC导入模板.xlsx」【原产国具体地区】sheet 2.“原产国具体地区”字符串长度不能超过100。 | `奈良县` |
| `source_country_customs_code` | body | string | 否 | 货源地编码 进入中国大陆前，商品所在的海外国家或地区编码，填写海关3 位国别编码，参照「BBC&BC导入模板.xlsx」【国家列表】sheet | `116` |
| `sku_spec` | body | string | 否 | SKU规格 请输入商品最小销售单元规格，如150ml/瓶、500g/袋；“SKU规格”字符串长度不能超过250。 | `白色L码` |
| `sku_spec_value` | body | string | 否 | 规格型号 包括:品名、牌名、规格、型号、成分、含量、等级等，满足海关归类、审价以及监管的要求，保税备货模式应和海关账册规格型号保持一致； “规格型号”字符串长度不能超过255。 | `某品牌\|女式\|衬衫\|针织\|有扣\|100%棉\|N47872\|白色WHITE MULTI` |
| `net_weight_qty` | body | string | 否 | 商品净重 1.单件商品重量（不包含外包装重量，必须大于0），单位kg，最多保留5位小数。 2.“法定第一单位”为千克时，“商品净重”需要大于等于“法定第一单位数量" | `0.5` |
| `gross_weight_qty` | body | string | 否 | 商品毛重 单件商品重量（包括包装重量，必须大于0，要大于等于净重），单位kg，最多保留3位小数。 | `0.6` |
| `ingredient_desc` | body | string | 否 | 成分 1.请按照实际成分完整填写， - 化妆品需填写具体化妆品成分。 - 食品类需填写具体配料名称；鱼油还需提供DHA+EPA浓度。 - 纺织品类商品需注明商品具体的成分含量及百分比（如羊毛80%化纤20%）、编织方法（针织，机织）等，如有填充需写明填充材质和包面材质，童装需写清适用年龄或者适合身高。 - 鞋类需提供款式、鞋面材料、鞋底材料。 - 电器需写清功率。 - 宠粮需提供各种配料和成分含量，务必在海关总署宠物食品准入名单内，同时不在宠物食品黑名单，动物源性配料务必提供成分含量百分比。 2.“成分”字符串长度不能超过2000。 | `100%棉` |
| `hscode` | body | string | 否 | 海关hscode，参考「正面清单」 说明：更新Hscode、FirstMeasureQty、SecondMeasureQty其中一个字段，必须将这3个字段的值一起传过来，否则返回参数错误。 | `6204430090` |
| `first_measure_qty` | body | string | 否 | 法定第一单位数量，大于0 说明：更新Hscode、FirstMeasureQty、SecondMeasureQty其中一个字段，必须将这3个字段的值一起传过来，否则返回参数错误。 | `1` |
| `second_measure_qty` | body | string | 否 | 法定第二单位数量，存在法定第二单位则需要传值，并且大于0；不存在法定第二单位，则传0 说明：更新Hscode、FirstMeasureQty、SecondMeasureQty其中一个字段，必须将这3个字段的值一起传过来，否则返回参数错误。 | `1` |
| `unit` | body | string | 否 | 海关申报计量单位，可与售卖单位一致，参考「申报计量单位对照表」 | `件` |
| `is_endangered` | body | mixed | 否 | 是否涉濒危 1: 涉及 2: 不涉及 进口商品是否涉濒危可查询「《濒危野生动植物种国际贸易公约》」；如选择不涉及，须确保商品成分来源的动植物不在公约范围内，或可提供公约免管证明文件，包括但不限于原产地证、非《进出口野生动植物种商品目录》物种证明等 | `2` |
| `is_hk_otc` | body | mixed | 否 | 是否药品 1: 是 2: 否 请选择是否为用于预防、诊断、治疗疾病用的处方或非处方药品 | `2` |
| `is_med_equip` | body | mixed | 否 | 是否医疗器械 1: 是 2: 否 请选择是否为用于预防、诊断、治疗疾病用的仪器、器具 | `2` |
| `is_pack_box` | body | mixed | 否 | 是否套盒 1: 是 2: 否 请选择是否为多个单品组合而成的套装商品 | `2` |
| `clothing_type` | body | mixed | 否 | 服饰种类：服饰可选填 0挡风御寒类外套(大衣、短大衣、斗篷、短斗篷、带风帽的防寒短上衣、防风衣、防风短上衣及类似品) 1上衣 2衬衫 3睡衣 4睡衣裤 5晨衣 6浴衣 7T恤衫 8汗衫 9背心 10套头衫 11开襟衬 12长裤 13护胸背带工装裤 14马裤 15短裤 16内裤 17三角裤 18连衣裙 19裙子 20裙裤 21长衬裙 22衬裙 23短衬裙 24西服套装 25便服套装 26运动服 27滑雪服 28游泳服 29经浸渍、涂层等处理的服装 30其他服饰 | `2` |
| `beauty_purpose` | body | mixed | 否 | 美妆用途：化妆品可选填 0化妆用 1护肤用 2洁肤用 3香水 | `0` |
| `prod_ent_name` | body | string | 否 | 生产企业名称 商品的境外生产企业名称，宠粮、肉类、水产品必填；“生产企业名称”字符串长度不能超过100。 | `ALTER RMACIA, S.A.` |
| `prod_ent_reg_no` | body | string | 否 | 生产企业注册号 境外生产企业在海关总署的注册号，宠粮、肉类、水产品必填；“生产企业注册号”字符串长度不能超过30。 | `2134` |
| `prod_ent_addr` | body | string | 否 | 生产企业地址 境外生产企业的具体地址，宠粮、肉类、水产品必填；“生产企业地址”字符串长度不能超过255。 | `Heisinger Strasse 8` |
| `record_element` | body | string | 否 | 备案要素 商品规格、成分、含量等相关要素；“备案要素”字符串长度不能超过30。 | `-` |
| `web_link` | body | string | 否 | 网络链接 商品详情页的网络链接，如果没有本平台的网络链接可以提供其他网站同款产品描述最详细的链接； “网络链接”字符串长度不能超过2048。 | `-` |
| `add_attachment_files` | body | array | 否 | 增加的附件文件列表 1.支持上传jpg、jpeg、png、PPT、PPTX、PDF格式  2.单个文件最大10M 3.本次新增的附件 加上 备案中已存在的附件，不能超过3个文件 | `` |
| `  └ file_no` | body | string | 是 | 文件编号 1.由商家提供并保证唯一，最长32个字符 2.只允许 a-zA-Z大小写字母、0-9数字、- | `a1a23456789ads` |
| `  └ file_uri` | body | string | 是 | 文件素材URI 请先参考「抖店开放平台二进制素材上传接入说明」拿到URI。 | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `remove_attachment_file_nos` | body | array | 否 | 删除的附件文件编号列表，与添加附件时的文件编号对应 | `["a1a23456789ads","1a23456789ad234"]` |
| `remark` | body | string | 否 | 备注 其他对商品的补充说明；“备注”字符串长度不能超过1000。 | `-` |
| `action` | body | string | 是 | 备案动作 save/apply save表示保存备案，apply表示备案保存并提交申请。 - 若设置为 save   - 准入驳回状态下保存，备案转为编辑中状态；   - 备案驳回状态下保存，备案转为编辑中状态。 - 若设置为 apply   - 准入驳回状态下申请，备案转为准入中状态；   - 备案驳回状态下申请，备案转为准入中状态。 | `save` |
| `extra` | body | string | 否 | 额外信息 | `{"示例":""}` |
| `add_origin_country_cert` | body | object | 否 | 要新增的原产地证明文件，为日本时可传值。 1.支持上传jpg、jpeg、png、PPT、PPTX、PDF格式  2.单个文件最大10M | `` |
| `  └ file_no` | body | string | 是 | 文件编号 1.由商家提供并保证唯一，最长32个字符 2.只允许 a-zA-Z大小写字母、0-9数字、- | `a1a23456789ads` |
| `  └ file_uri` | body | string | 是 | 文件素材URI 请先参考「抖店开放平台二进制素材上传接入说明」拿到URI。 | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `remove_origin_country_cert_file_no` | body | string | 否 | 删除的原产地证明文件编号，与添加原产地证明文件时的文件编号对应 | `a1a23456789ads` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/UpdateProductRecord?app_key=your_appkey_here&method=crossBorder.UpdateProductRecord&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 返回码 | `0` |
| `msg` | string | 返回结果描述 | `-` |
| `product_record_info` | object | 备案更新后的最新数据，商家基于此数据更新自己的备案 | `` |
| `extra` | string | 额外信息 | `{"示例":""}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 内部系统异常（sub_code: isp.service-error:10000） | 重试，多次失败联系平台处理 |
| `60000` | 触发限流，请稍后重试 / 达到qps上限，触发限流（sub_code: isp.traffic-limited:10002） | 重试，并调整流量，控制QPS符合平台要求 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:20000） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 业务处理异常，如备案审核状态不正确、备案不存在、仓所属口岸与传入口岸不一致等（sub_code: isv.business-failed:30000） | 结合返回信息处理，有疑问联系平台处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "extra": {},
    "msg": "-",
    "product_record_info": {
      "attachment_file_nos": "[\"a1a23456789ads\",\"f1a23456789adg\"]",
      "audit_memo": "请修改货品名称与备案名称一致",
      "audit_status": "100",
      "beauty_purpose": "0",
      "brand_name": "某品牌",
      "cargo_code": "7031837824806568204",
      "clothing_type": "2",
      "customs_clear_type": "1",
      "customs_code": "0127",
      "delete_status": "0",
      "external_cargo_code": "920701213",
      "first_measure_qty": "1",
      "first_measure_unit": "件",
      "golden_gate_no": "23541",
      "gross_weight_qty": "0.6",
      "hscode": "6204430090",
      "ingredient_desc": "100%棉",
      "is_4pl": "1",
      "is_endangered": "2",
      "is_hk_otc": "2",
      "is_invalid": "0",
      "is_med_equip": "2",
      "is_pack_box": "2",
      "limit_rule_info": "[\"跨境保税进口食品报关前,报关单上的境外发货人需完成食品出口商或代理商备案才可完成入境申报,请您知悉并提前办理,避免可能导致的退单风险；办理路径：http://online.customs.gov.cn,“企业管理和稽查”版块；\"]",
      "net_weight_qty": "0.5",
      "origin_country_area": "奈良县",
      "origin_country_cert_file_no": "a1a23456789ads",
      "origin_country_customs_code": "116",
      "pack_type": "塑料包装",
      "prod_ent_addr": "Heisinger Strasse 8",
      "prod_ent_name": "ALTER RMACIA, S.A.",
      "prod_ent_reg_no": "2134",
      "purpose": "衣着用品",
      "record_create_time": "1708256513000",
      "record_element": "-",
      "record_id": "7034043070463115533",
      "record_name": "某品牌衬衫白色L码",
      "record_part_no": "7317191992788877603",
      "record_update_time": "1708257513000",
      "remark": "-",
      "second_measure_qty": "1",
      "second_measure_unit": "千克",
      "sku_spec": "白色L码",
      "sku_spec_value": "某品牌|女式|衬衫|针织|有扣|100%棉|N47872|白色WHITE MULTI",
      "source_country_customs_code": "116",
      "sp_code": "ZZJC",
      "unit": "件",
      "warehouse_code": "4PLWMSTESTBBC1",
      "web_link": "-"
    }
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10000",
  "sub_msg": "内部系统异常"
}
```

## 备注
