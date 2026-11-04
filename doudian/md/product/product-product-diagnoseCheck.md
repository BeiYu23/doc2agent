# 发布前校验

> product.diagnoseCheck — 发布前校验

| 元信息 | 值 |
| --- | --- |
| 中文名 | 发布前校验 |
| 文档地址 | `/docs/doudian/product/product-product-diagnoseCheck` |
| 接口 ID | `doudian.product.product.diagnoseCheck` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/diagnoseCheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7342 |
| 更新日期 | `2025-04-24` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_format_new` | body | string | 否 | 属性实体 | `{}` |
| `  └ value` | body | mixed | 否 | 属性值id | `纯棉` |
| `  └ name` | body | string | 否 | 属性值名称 | `聚酯纤维` |
| `  └ diy_type` | body | mixed | 否 | 是否为商家自定义属性值，1为是，0为不是，默认为0 | `0` |
| `short_product_name` | body | string | 否 | 短标题 | `商品短标题` |
| `spec_name` | body | string | 否 | 规格名 | `颜色分类` |
| `spec_value` | body | string | 否 | 规格词 | `红色` |
| `sku_list` | body | array | 否 | 商品sku | `` |
| `  └ price` | body | mixed | 否 | 价格 | `1000` |
| `  └ name` | body | string | 否 | sku名称用属性项和属性值拼接组成，格式： 规格项1:规格值1;规格项2:规格值2; | `颜色分类:红色;尺码:M;` |
| `  └ stock` | body | mixed | 否 | 库存 | `100` |
| `  └ image_url` | body | string | 否 | 规格图片 | `ecom-shop-material/jpeg_m_bb06b738f66a8e34355a2f6d65856010_sx_592497_www800-800` |
| `  └ sku_id` | body | mixed | 否 | skuid | `232323` |
| `  └ spec_detail_ids` | body | array | 否 | 规格id列表 | `[                 "1825226749200409",                 "1825226749202489"             ]` |
| `  └ sku_classification_type` | body | string | 否 | sku分类 | `无` |
| `  └ sell_properties` | body | array | 否 | 销售属性 | `` |
| `    └ property_name` | body | string | 否 | 销售属性项名称 | `颜色分类` |
| `    └ value_name` | body | string | 否 | 销售属性值名字 | `黄色` |
| `    └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `      └ template_id` | body | mixed | 否 | 标准化的公式模板ID | `1212` |
| `      └ values` | body | array | 否 | 度量衡值组 | `` |
| `        └ prefix` | body | string | 否 | 前缀：如日用 | `日用` |
| `        └ module_id` | body | mixed | 否 | 模块ID | `122` |
| `        └ value` | body | string | 否 | 值：如10 | `10` |
| `        └ unit_id` | body | mixed | 否 | 单位ID | `23` |
| `        └ unit_name` | body | string | 否 | 单位名称：如抽 | `抽` |
| `        └ suffix` | body | string | 否 | 后缀：如* | `*` |
| `quality_score_version` | body | string | 否 | 质量分 | `100` |
| `product_main_pic` | body | array | 否 | 主图信息，主图1：1和主图3：4 | `` |
| `  └ url` | body | string | 否 | 图片url | `https://p3-aio.ecombdimg.com/obj/ecom-shop-material/png_m_abf25b2634afc5710defa529796f97bd_sx_859041_www600-800` |
| `  └ type` | body | mixed | 否 | 图片类型 | `2` |
| `  └ pic_id` | body | mixed | 否 | 图片id | `0` |
| `poi_use_condition` | body | string | 否 | 卡券使用条件 | `无` |
| `size_info_template_id` | body | mixed | 否 | 尺码模板id | `123` |
| `props` | body | string | 否 | 属性 | `废弃` |
| `biz_kind` | body | mixed | 否 | 0:普通商品，1:教育类商品 2:跨境商品 | `0` |
| `desc_text` | body | string | 否 | 详情文字 | `详情文字` |
| `risk_prop` | body | string | 否 | 高危词判断 | `高危词判断` |
| `product_type` | body | mixed | 是 | 商品类型 | `0` |
| `category` | body | mixed | 是 | 叶子类目ID | `24981` |
| `pic` | body | array | 否 | 主图 | `["https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_8f6130a19c5af35f7fbe9d56ef24e25e_sx_707570_www800-800","https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_8f6130a19c5af35f7fbe9d56ef24e25e_sx_707570_www800-800"]` |
| `product_material_map` | body | string | 否 | 商品素材信息 | `` |
| `  └ media_type` | body | mixed | 否 | 素材类型 | `0` |
| `  └ urls` | body | array | 否 | 素材图片url | `[                 "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_85c0dbe86f70bc22ccb3f20353ebc721_sx_318770_www800-800"             ]` |
| `  └ resource_ids` | body | array | 否 | 视频id | `[                 "v0227cg10001cv2q9ivog65p1fpta0ug"             ]` |
| `  └ material_id` | body | mixed | 否 | 素材ID | `123` |
| `product_id` | body | mixed | 是 | 商品id | `351111111111111` |
| `product_name` | body | string | 否 | 商品名称 | `商品名称` |
| `product_biz` | body | mixed | 否 | 业务类型 | `1223233423232` |
| `is_template_opened` | body | boolean | 否 | 尺码模板开关 | `true` |
| `poi_notification` | body | string | 否 | 商品卡券领取 | `废弃` |
| `check_type` | body | mixed | 否 | 场景 1发布 2诊断 | `0` |
| `brand_id` | body | string | 否 | 品牌ID | `122323` |
| `desc_pic` | body | array | 否 | 详情图 | `[         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_bb06b738f66a8e34355a2f6d65856010_sx_592497_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_a3bd8b131292c606714addb42ac49994_sx_515811_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_1204eabbf5dd783f2763e8c2e448e4f8_sx_621215_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_c44f2b860c07f9391682c43acc60372d_sx_491669_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_776be48ff5bdc35311d0eb8ba18024fd_sx_578742_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_4730dfb87ade298e5bebf26224a5e7a2_sx_728745_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_b71a3bbdefc5cc1ee6342855ba2bf245_sx_646607_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_58956b9470b717a582797969f84ffbe5_sx_771903_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_0c8133579f1befff9493bf421740bff7_sx_824777_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_77878fc69879a331b916c3e253cace78_sx_894403_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_61b5b9a136704383a9482970d52478e8_sx_758447_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_692481144791458665a93017af20ad1b_sx_794850_www800-800",         "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_48ba5b33e39dd2b7cbf80238caed839b_sx_691435_www800-800"     ]` |
| `cross_border` | body | mixed | 否 | 是否跨境 0 否 1 是 | `0` |
| `brand_related_id` | body | string | 否 | 品牌关联ID | `0` |
| `component_template` | body | object | 否 | 尺码结构及详细数据 | `` |
| `  └ template_type` | body | string | 否 | 模板类型: size_info(尺码表) | `size_info` |
| `  └ template_sub_type` | body | string | 否 | 指定模板类型: clothing、undies、shoes、children_clothing | `clothing` |
| `  └ template_name` | body | string | 否 | 模板名称 | `模板名称` |
| `  └ component_front_data` | body | string | 否 | 商品组件编辑器源数据 json | `{\"title\":\"连身衣/爬服/哈衣\",\"desc\":\"连身衣/爬服/哈衣\",\"tempName\":\"\",\"configTable\":[{\"size\":\"66cm\",\"specMap\":{\"体重(斤)\":\"5-7\",\"身高(CM)\":\"66\"}},{\"size\":\"73cm\",\"specMap\":{\"体重(斤)\":\"7-9\",\"身高(CM)\":\"73\"}},{\"size\":\"80cm\",\"specMap\":{\"体重(斤)\":\"9-12\",\"身高(CM)\":\"80\"}},{\"size\":\"90cm\",\"specMap\":{\"体重(斤)\":\"11-15\",\"身高(CM)\":\"90\"}}],\"selectedSpecs\":[\"身高(CM)\",\"体重(斤)\"],\"headerName\":\"尺码\",\"specOptions\":[\"身高(CM)\",\"体重(斤)\"],\"selectedSize\":[\"66cm\",\"73cm\",\"80cm\",\"90cm\"],\"selectedSizeSpecValMap\":{}}` |
| `  └ component_data` | body | string | 否 | 商品组件数据 json | `{\"title\":\"连身衣/爬服/哈衣\",\"sub_title\":\"连身衣/爬服/哈衣\",\"selected_size\":[\"66cm\",\"73cm\",\"80cm\",\"90cm\"],\"selected_specs\":[\"身高(CM)\",\"体重(斤)\"],\"config\":{\"66cm\":{\"体重(斤)\":\"5-7\",\"身高(CM)\":\"66\"},\"73cm\":{\"体重(斤)\":\"7-9\",\"身高(CM)\":\"73\"},\"80cm\":{\"体重(斤)\":\"9-12\",\"身高(CM)\":\"80\"},\"90cm\":{\"体重(斤)\":\"11-15\",\"身高(CM)\":\"90\"}},\"selected_size_spec_val_map\":{}}` |
| `  └ shareable` | body | boolean | 否 | 是否可共享 | `false` |
| `recommend_remark` | body | string | 否 | 商品推荐语 | `废弃` |
| `only_base_score` | body | mixed | 否 | 是否仅需要基础分相关诊断项 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/diagnoseCheck?app_key=your_appkey_here&method=product.diagnoseCheck&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `quality_score` | object | 质量分 | `` |
| `diagnose_essential_material` | object | 必要图文 | `` |
| `quality_score_calculating` | boolean | 质量分是否计算中 | `true` |
| `field_problem` | array | 字段问题 | `` |
| `base_score` | mixed | 基础分 | `无` |
| `diagnose_recommend` | object | 推荐值 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2030001:商品诊断失败（sub_code: isv.business-failed:2030001） | 报错 |

## 响应示例

成功：

```json
{
  "data": {
    "base_score": "无",
    "diagnose_essential_material": {
      "essential_material_info_list": [
        {
          "code": "0",
          "material_component_id": "0",
          "material_source": "无",
          "url": "无"
        }
      ]
    },
    "diagnose_recommend": {
      "ai_suggest_prop": [
        {
          "property_id": "无",
          "property_name": "无",
          "value_id": "无",
          "value_name": "无"
        }
      ],
      "name": "无",
      "prop_map": {},
      "recommend_tag_info_list": [
        {
          "name": "无",
          "tag_type": "无"
        }
      ],
      "suggest_seo_title_words": "无"
    },
    "field_problem": [
      {
        "detail_link": "无",
        "diagnose_target": "无",
        "field_key": "props",
        "field_name": "主图",
        "first_optimization_type": "无",
        "index": "0",
        "is_app_support": "false",
        "is_base_score": "false",
        "is_block": "false",
        "is_empty_type": "false",
        "is_fatal": "false",
        "is_ignored": "false",
        "is_quality_score": "true",
        "is_support_exemption": "true",
        "is_support_ignore": "无",
        "item_rcmd_effect": {
          "effct_desc": "无",
          "improve_value_lower_bound": "无",
          "improve_value_upper_bound": "无",
          "optimization_info": {
            "default_event_type": "无",
            "default_index_value": "[1,2,3]",
            "optimization_key": "无",
            "optimization_name": "无",
            "optimization_status": "无",
            "unavailable_reason": "无"
          },
          "peer_usage_rate": "无"
        },
        "jump_link": "无",
        "optimization_issue": "无",
        "optimization_object": "无",
        "optimization_type": "无",
        "problem_affect_describe": "无",
        "problem_biz_extra": {
          "conflict_props_docs_map": {},
          "similar_product_list": "无",
          "title_typo": "无"
        },
        "problem_category": "suggest_problem",
        "problem_desc": "无",
        "problem_key": "2002",
        "problem_name": "商品缺少白底图",
        "problem_position": "无",
        "problem_score": "12",
        "problem_simple_name": "商品缺少白底图",
        "problem_type": "废弃",
        "prop_ids": "[1,2,3]",
        "second_optimization_type": "无",
        "suggestion": "商品缺少白底图素材，影响商品活动报名，建议补充纯白背景加商品主体图片",
        "tab_optimization_type": "无"
      }
    ],
    "quality_score": {
      "level": "lv2",
      "score": "100",
      "version": "new_quality_score"
    },
    "quality_score_calculating": "true"
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
  "sub_code": "isv.business-failed:2030001",
  "sub_msg": "2030001:商品诊断失败"
}
```

## 备注
