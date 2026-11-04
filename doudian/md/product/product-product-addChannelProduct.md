# product.addChannelProduct

> 创建销售渠道品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.addChannelProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/addChannelProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4462 |
| 更新日期 | `2025-09-08` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `main_product_id` | body | mixed | 是 | 主商品ID | `3627614096842696400` |
| `channel_type` | body | mixed | 是 | 渠道类型 3：商家自卖 4：达人带货 | `3` |
| `name` | body | string | 否 | 渠道品定制标题。必填 | `【直播专属】电竞椅台式电脑桌` |
| `main_img_list` | body | array | 否 | 渠道品定制主图，最高支持5张。可省略，默认使用主商品主图列表 | `["https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600", "https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600"]` |
| `start_time` | body | string | 否 | 有效期开始时间。不填开始和结束时间，代表长期有效 | `2023-07-13 17:42:03` |
| `end_time` | body | string | 否 | 有效期结束时间。不填开始和结束时间，代表长期有效 | `2023-07-15 17:42:06` |
| `price_follow_main` | body | boolean | 是 | 渠道品SKU价格是否跟随主品 | `false` |
| `share_main_stock` | body | boolean | 是 | 渠道品SKU库存是否与主商品共享库存 | `false` |
| `is_kol_exclusive` | body | boolean | 是 | 是否『达人专属』渠道品 | `false` |
| `channel_buy_limit` | body | object | 否 | 渠道品限购信息 | `` |
| `  └ total_buy_num` | body | mixed | 否 | 单用户累计购买上限数 | `10` |
| `  └ max_buy_num` | body | mixed | 否 | 每次购买上限数 | `5` |
| `  └ min_buy_num` | body | mixed | 否 | 每次至少购买数 | `1` |
| `sku_channel` | body | array | 是 | 渠道SKU相关信息 | `` |
| `  └ stock_set_mode` | body | mixed | 否 | 库存编辑模式，0=设置绝对值，1=增量设置 | `1` |
| `  └ code` | body | string | 否 | 渠道品定制SKU商家编码。可忽略，默认使用主商品SKU商家编码。 | `49374` |
| `  └ sku_id` | body | mixed | 是 | 主商品SkuID | `1771295549374468` |
| `  └ price` | body | mixed | 否 | 价格，单位分。设置价格跟随主品时，可不填 | `10` |
| `  └ stock_num` | body | mixed | 否 | 库存，勿大于主SKU的可售库存。设置库存与主商品共享时，可不填 | `100` |
| `detail_brief_img` | body | array | 否 | 渠道品定制详情图，最高支持50张。detail_brief_follow_main值为false时，必须设置商详图 | `["https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600", "https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_290637ca0b8211e45bf4a441fc10b938_sx_47135_www600-600"]` |
| `freight_template` | body | object | 否 | 运费模板信息 | `` |
| `  └ freight_follow_main` | body | boolean | 否 | 渠道品运费模板是否与主品保持一致 | `true` |
| `  └ freight_id` | body | mixed | 否 | 渠道品定制运费模板ID，当设置了freight_follow_main=true时与主品运费模板保持一致；否则需要传值。 | `0` |
| `sku_code_follow_main` | body | boolean | 否 | 商家编码与主品保持一致 | `false` |
| `detail_brief_follow_main` | body | boolean | 否 | 商详与主品保持一致配置，true：保持一致；false：单独配置（此时必须传入商详图片，否则渠道品在c端将没有商详图） | `true` |
| `name_prefix` | body | string | 否 | 标题前缀 | `标题前缀` |
| `name_subject` | body | string | 否 | 标题内容。注意：后续推荐使用name_prefix和name_subject设置标题，不建议使用name字段。并且name字段和name_prefix\name_subject2套传参互斥 | `标题内容` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/addChannelProduct?app_key=your_appkey_here&method=product.addChannelProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_id` | mixed | 店铺ID | `95078` |
| `product_id` | mixed | 主商品ID | `3627614096842696400` |
| `channel` | object | 渠道信息 | `` |
| `is_kol_exclusive` | boolean | 是否『达人专属』渠道品 | `false` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 达人专属配置不支持库存与主品共享（sub_code: isv.parameter-invalid:400002） | 取消勾选库存共享，设置库存信息 |
| `40004` | 非法的参数 / 精选联盟权限校验失败（sub_code: isv.parameter-invalid:400001） | 请按返回的详细错误信息处理 |
| `40004` | 非法的参数 / 渠道主商品为在线审核通过状态才可以创建（sub_code: isv.parameter-invalid:101045） | 变更主商品状态 |
| `40004` | 非法的参数 / 不支持该商品类型创建渠道品（sub_code: isv.parameter-invalid:101046） | 暂不支持奖品、拍卖商品、非卖品、保证金品、闪购商品、定金找货、保险业务等主商品创建渠道品 |
| `40004` | 非法的参数 / 渠道商详链接不合法（sub_code: isv.parameter-invalid:2010001） | 请检查商详图片链接格式以及是否可用 |
| `40004` | 非法的参数 / 开始时间解析异常（sub_code: isv.parameter-invalid:2010004） | 请检查开始时间格式 |
| `40004` | 非法的参数 / 仅达人带货渠道品可设置达人专属（sub_code: isv.parameter-invalid:110101051） | 仅达人带货渠道品可设置达人专属 |
| `50002` | 业务处理失败 / 无效的渠道SKU（sub_code: isv.business-failed:110103009） | 无效的渠道SKU |
| `50002` | 业务处理失败 / 店铺尚未开通联盟权限，暂无法创建达人渠道品，请先前往精选联盟完成权限开通。（sub_code: isv.business-failed:110102140） | 店铺尚未开通联盟权限，暂无法创建达人渠道品，请先前往精选联盟完成权限开通。 |
| `50002` | 业务处理失败 / 渠道主商品为在线审核通过状态才可以创建（sub_code: isv.business-failed:110101045） | 渠道主商品为在线审核通过状态才可以创建 |
| `50002` | 业务处理失败 / 商品不存在（sub_code: isv.business-failed:2010058） | 商品不存在 |
| `50002` | 业务处理失败 / 每次限购件数不能超过累计限购件数（sub_code: isv.business-failed:110280111） | 每次限购件数不能超过累计限购件数 |
| `50002` | 业务处理失败 / 限购值最大可设置200（sub_code: isv.business-failed:110280114） | 限购值最大可设置200 |
| `50002` | 业务处理失败 / 商品标题最长不能超过30个汉字（60个字符）（sub_code: isv.business-failed:110101150） | 商品标题最长不能超过30个汉字（60个字符） |
| `50002` | 业务处理失败 / 奖品不支持创建渠道品（sub_code: isv.business-failed:110101046） | 奖品不支持创建渠道品 |

## 响应示例

成功：

```json
{
  "data": {
    "channel": {
      "channel_id": "1771297785994256",
      "channel_type": "3"
    },
    "is_kol_exclusive": "false",
    "product_id": "3627614096842696400",
    "shop_id": "95078"
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
  "sub_code": "isv.parameter-invalid:400002",
  "sub_msg": "达人专属配置不支持库存与主品共享"
}
```

## 备注
