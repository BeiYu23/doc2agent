# product.updateChannelProduct

> 编辑渠道商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.updateChannelProduct` |
| 中文名 | 编辑渠道商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/updateChannelProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4461 |
| 更新日期 | `2025-09-08` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `main_product_id` | body | mixed | 是 | 主商品ID | `3631654780608339610` |
| `channel_id` | body | mixed | 是 | 渠道ID | `1775199232748660` |
| `channel_type` | body | mixed | 是 | 渠道类型。不支持修改。 3：商家自卖 4：达人带货 | `3` |
| `name` | body | string | 否 | 渠道品定制标题，必填 | `半身裙` |
| `main_img_list` | body | array | 否 | 渠道品定制主图，最高支持5张。detail_brief_follow_main值为false时，必须设置商详图 | `["https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600", "https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600"]` |
| `start_time` | body | string | 否 | 有效期开始时间 | `2023-02-21 16:46:21` |
| `end_time` | body | string | 否 | 有效期结束时间 | `2023-02-21 16:46:21` |
| `price_follow_main` | body | boolean | 是 | 渠道品SKU价格是否跟随主品 | `true` |
| `share_main_stock` | body | boolean | 是 | 渠道品SKU库存是否与主商品共享库存 | `true` |
| `is_kol_exclusive` | body | boolean | 是 | 是否『达人专属』渠道品，不支持修改 | `false` |
| `channel_buy_limit` | body | object | 否 | 渠道品限购信息 | `` |
| `  └ total_buy_num` | body | mixed | 否 | 单用户累计购买上限数 | `3` |
| `  └ max_buy_num` | body | mixed | 否 | 每次购买上限数 | `1` |
| `  └ min_buy_num` | body | mixed | 否 | 每次至少购买数 | `1` |
| `sku_channel` | body | array | 是 | 渠道SKU相关信息 | `` |
| `  └ stock_set_mode` | body | mixed | 否 | 库存设置方式。0=设置绝对值，1=增量设置 | `1` |
| `  └ code` | body | string | 否 | 渠道品定制SKU商家编码。可忽略，默认使用主商品SKU商家编码。 | `49374` |
| `  └ sku_id` | body | mixed | 是 | 主商品SkuID | `2343432432432` |
| `  └ price` | body | mixed | 否 | 价格。设置价格跟随主品时，可不填 | `11` |
| `  └ stock_num` | body | mixed | 否 | 库存，勿大于主SKU的可售库存。设置库存与主商品共享时，可不填 | `22` |
| `detail_brief_img` | body | array | 否 | 渠道品定制详情图，最高支持50张。可省略，默认使用主商品详情图列表 | `["https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600", "https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600"]` |
| `freight_template` | body | object | 否 | 运费模板 | `` |
| `  └ freight_follow_main` | body | boolean | 否 | 渠道品运费模板是否与主品保持一致 | `true` |
| `  └ freight_id` | body | mixed | 否 | 渠道品定制运费模板ID，当设置了freight_follow_main=true时与主品运费模板保持一致；否则需要传渠道品定制运费模板。 | `0` |
| `sku_code_follow_main` | body | boolean | 否 | 商家编码与主品保持一致配置，true-商家编码与主品保持一致，false-商家编码自定义 | `false` |
| `detail_brief_follow_main` | body | boolean | 否 | 商详与主品保持一致配置，true：保持一致；false：单独配置（此时必须传入商详图片，否则渠道品在c端将没有商详图） | `true` |
| `name_prefix` | body | string | 否 | 标题前缀 | `标题前缀` |
| `name_subject` | body | string | 否 | 标题内容。注意：后续推荐使用name_prefix和name_subject设置标题，不建议使用name字段。并且name字段和name_prefix\name_subject2套传参互斥 | `标题内容` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/updateChannelProduct?app_key=your_appkey_here&method=product.updateChannelProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_id` | mixed | 店铺ID | `12332` |
| `product_id` | mixed | 主商品ID | `3631654780608339610` |
| `channel` | object | 渠道信息 | `` |
| `is_kol_exclusive` | boolean | 是否『达人专属』渠道品 | `false` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 渠道品查询失败，请重试（sub_code: isv.business-failed:2010001） | 请求重试 |
| `40004` | 非法的参数 / 仅达人带货渠道品可设置达人专属（sub_code: isv.parameter-invalid:110101051） | 仅达人带货渠道品可设置达人专属 |
| `50002` | 业务处理失败 / 达人专属配置不支持更改（sub_code: isv.business-failed:2010004） | 达人专属配置不支持更改 |
| `50002` | 业务处理失败 / 商品不存在（sub_code: isv.business-failed:2010058） | 商品不存在 |
| `50002` | 业务处理失败 / 110102140:店铺尚未开通联盟权限，暂无法创建达人渠道品，请先前往精选联盟完成权限开通。（sub_code: isv.business-failed:110102140） | 110102140:店铺尚未开通联盟权限，暂无法创建达人渠道品，请先前往精选联盟完成权限开通。 |
| `50002` | 业务处理失败 / 110101045:渠道主商品为在线审核通过状态才可以创建（sub_code: isv.business-failed:110101045） | 110101045:渠道主商品为在线审核通过状态才可以创建 |
| `50002` | 业务处理失败 / 110406011:销量评价设置禁止修改（sub_code: isv.business-failed:110406011） | 110406011:销量评价设置禁止修改 |
| `50002` | 业务处理失败 / 110101150:商品标题最长不能超过30个汉字（60个字符）（sub_code: isv.business-failed:110101150） | 110101150:商品标题最长不能超过30个汉字（60个字符） |
| `50002` | 业务处理失败 / 110101229:商品正在参加<a href='https://fxg.jinritemai.com/ffa/merchant/parent-campaign-detail?id=7538389770477994291&step=ProductAudition' target="_blank">9月商城加补活动（原商城市集） </a>（活动类型:平台活动），暂不支持修改SKU（sub_code: isv.business-failed:110101229） | 110101229:商品正在参加<a href='https://fxg.jinritemai.com/ffa/merchant/parent-campaign-detail?id=7538389770477994291&step=ProductAudition' target="_blank">9月商城加补活动（原商城市集） </a>（活动类型:平台活动），暂不支持修改SKU |

## 响应示例

成功：

```json
{
  "data": {
    "channel": {
      "channel_id": "1775199232748660",
      "channel_type": "3"
    },
    "is_kol_exclusive": "false",
    "product_id": "3631654780608339610",
    "shop_id": "12332"
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
  "sub_code": "isv.business-failed:2010001",
  "sub_msg": "渠道品查询失败，请重试"
}
```

## 备注
