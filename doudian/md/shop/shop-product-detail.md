# 商品查询

> product.detail — 商品查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商品查询 |
| 文档地址 | `/docs/doudian/shop/shop-product-detail` |
| 接口 ID | `doudian.shop.product.detail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2083 |
| 更新日期 | `2022-06-29` |

## 接口说明

- 文档书: 店铺API（版本 V12.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 否 | 商品id | `3539925204033339668` |
| `out_product_id` | body | string | 否 | 外部商品id | `11111` |
| `show_draft` | body | string | 否 | "true"：读取草稿数据；"false"：读取上架数据 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/detail?app_key=your_appkey_here&method=product.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_id` | number | 商品ID | `3539925204033339668` |
| `product_id_str` | string | 商品ID，字符串格式 | `3539925204033339668` |
| `out_product_id` | number | 商品外部ID | `11111` |
| `outer_product_id` | string | 商品外部ID字符串 | `11111` |
| `open_user_id` | number | open应用id | `1` |
| `name` | string | 商品名称 | `xxx爽肤水` |
| `description` | string | 详情html | `<img src=\"https://tosv.boe.byted.org/obj/temai/54cbf542128eff94a3549284817c0af5bf5c2960www800-800\" style=\"width:100%;\">` |
| `delivery_method` | string | 承诺发货时间，单位是天 不传则默认为2天，presell_type为0或2均只支持传入2，presell_type为1时支持可选值为: 2、3、5、7、10、15 | `7` |
| `cdf_category` | string | 海南免税：海关限购分类编码 | `1` |
| `status` | number | 商品上下架状态：0上架 1下架 2已删除 | `1` |
| `spec_id` | number | 规格id | `1` |
| `check_status` | number | 商品审核状态：1未提审 2审核中 3审核通过 4审核驳回 5封禁 7审核通过，待上架状态 | `1` |
| `mobile` | string | 手机号 | `15677775555` |
| `brand_id` | number | 品牌id | `12344` |
| `is_sub_product` | boolean | 是否是组套商品的子商品 | `true` |
| `draft_status` | number | 草稿状态：0 无草稿,1 未提审,2 待审核,3 审核通过,4 审核未通过 | `2` |
| `category_detail` | object | 新类目的详情 | `` |
| `pay_type` | number | 支持的支付方式：0货到付款 1在线支付 2两者都支持 | `1` |
| `recommend_remark` | string | 商家推荐语 | `真的很好啊` |
| `extra` | string | 扩展字段 | `-` |
| `is_create` | number | 已废弃，无业务意义 | `1` |
| `create_time` | string | 创建时间 | `2021-03-29 15:52:52` |
| `update_time` | string | 更新时间 | `2021-03-29T15:52:52+08:00` |
| `pic` | array | 商品主图 | `["https://sf6-ttcdn-tos.pstatp.com/obj/temai/0c71ce6acb4e3b508e0d30042b1a94262818ab41www800-800"]` |
| `product_format` | string | 属性名称\|属性值 之间用\|分隔, 多组之间用^分开 | `{"货号":"8888"}` |
| `spec_pics` | array | 规格图片 | `` |
| `spec_prices` | array | sku详情 | `` |
| `specs` | array | 销售属性 | `` |
| `img` | string | 头图，主图第一张 | `https://xxxx.byted.org/obj/temai/54cbf542128eff94a3549284817c0af5bf5c2960www800-800` |
| `presell_type` | number | 预售类型，1-全款预售，0-非预售，2-阶梯库存 | `1` |
| `maximum_per_order` | number | 每个用户每次下单限购件数 | `5` |
| `limit_per_buyer` | number | 每个用户累计限购件数 | `5` |
| `minimum_per_order` | number | 每个用户每次下单至少购买的件数 | `1` |
| `quality_list` | array | 资质信息 | `` |
| `logistics_info` | object | 跨境物流信息 | `` |
| `after_sale_service` | string | 售后服务 | `{"supply_7day_return":"2"}` |
| `price_has_tax` | number | 商品价格是否含税 | `0` |
| `appoint_delivery_day` | number | 可预约发货天数 | `2` |
| `product_format_new` | string | 类目属性 | `{"1088":[{"Value":0,"Name":"小33学二年级","PropertyId":1088,"PropertyName":"适用学龄段","diy_type":1}],"1319":[{"Value":0,"Name":"1","PropertyId":1319,"PropertyName":"适用地区","diy_type":0}],"1618":[{"Value":0,"Name":"9787218122861","PropertyId":1618,"PropertyName":"ISBN编号","diy_type":0}],"1831":[{"Value":0,"Name":"小学英语看图说话写话二年级","PropertyId":1831,"PropertyName":"书名","diy_type":0}],"2000":[{"Value":34762,"Name":"无","PropertyId":2000,"PropertyName":"作者地区","diy_type":0}],"2229":[{"Value":0,"Name":"1","PropertyId":2229,"PropertyName":"编者","diy_type":0}],"3271":[{"Value":0,"Name":"1","PropertyId":3271,"PropertyName":"出版时间","diy_type":0}],"449":[{"Value":0,"Name":"1","PropertyId":449,"PropertyName":"作者","diy_type":0}],"501":[{"Value":7310,"Name":"否","PropertyId":501,"PropertyName":"是否是套装","diy_type":0}],"855":[{"Value":0,"Name":"陕西人民教育出版社","PropertyId":855,"PropertyName":"出版社名称","diy_type":0}]}` |
| `standard_brand_id` | number | 品牌库brand id，原brand_id代表商标关系id | `121354` |
| `market_price` | number | 划线价 单位分 | `12000` |
| `discount_price` | number | 售卖价 单位分 | `12000` |
| `car_vin_code` | string | 汽车vin码 | `VIN11111111111111` |
| `need_recharge_mode` | boolean | 生活娱乐充值模式 | `false` |
| `account_template_id` | string | 多账号充值账号模板 | `1` |
| `presell_config_level` | number | 发货模式：presell_type = 0 现货；presell_type = 2 阶梯；presell_type = 1 && presell_config_level = 0 全款预售；presell_type = 1 && presell_config_level = 1 sku预售；presell_type = 1 && presell_config_level = 2 现货+预售；presell_type = 1 && presell_config_level = 3 新预售 | `2` |
| `delivery_delay_day` | number | 现货模式的发货天数；阶梯模式现货部分的发货天数，9999=当日发、1=次日发 | `2` |
| `presell_delay` | number | 阶梯模式阶梯部分的发货天数；商品全款预售模式，预售天数 | `4` |
| `poi_resource` | object | 卡券信息 | `` |
| `delay_rule` | object | 特殊日期延迟发货规则 | `` |
| `long_pic_url` | string | 3:4长图url(仅素材中心url有效) | `https://aaa` |
| `sell_channel` | array | 售卖方式;0:全渠道手售卖,1:仅指定直播间售卖 | `[0]` |
| `freight_id` | number | 运费模版ID | `123` |
| `material_video_id` | string | 主图视频ID | `Vaaxxaa` |
| `pickup_method` | string | 提取方式新字段，推荐使用。"0": 普通商品-使用物流发货, "1": 虚拟商品-无需物流与电子交易凭证, "2": 虚拟商品-使用电子交易凭证,  "3": 虚拟商品-充值直连 | `0` |
| `size_info_template_id` | number | 尺码模板ID | `7102988069296423000` |
| `white_back_ground_pic_url` | string | 白底图url(仅素材中心url有效) | `https://aaa` |
| `sale_channel_type` | string | 销售渠道类型，包括纯电商（onlineOnly）、专柜同款（sameAsOffline），云零售商家（https://fxg.jinritemai.com/ffa/merchant-growth/cloud-retail）可以设置 | `sameAsOffline` |
| `store_id` | number | 门店ID | `103121` |
| `main_product_id` | number | 主商品ID | `3121213` |
| `sale_limit_id` | number | 限售模板ID | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / out_product_id未找到或商品已删除（sub_code: isv.parameter-invalid:4） | 请检查参数后重试 |
| `20000` | 系统错误 / 7:请求失败，请稍后再试（sub_code: isp.service-error:7） | 请检查参数后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "account_template_id": "1",
    "after_sale_service": "{\"supply_7day_return\":\"2\"}",
    "appoint_delivery_day": "2",
    "brand_id": "12344",
    "car_vin_code": "VIN11111111111111",
    "category_detail": {
      "first_cid": "23264",
      "first_cname": "教育培训",
      "fourth_cid": "0",
      "fourth_cname": "-",
      "second_cid": "0",
      "second_cname": "学习卡",
      "third_cid": "0",
      "third_cname": "-"
    },
    "cdf_category": "1",
    "check_status": "1",
    "create_time": "2021-03-29 15:52:52",
    "delay_rule": {
      "config_type": "1",
      "config_value": "1673539199",
      "enable": "true",
      "end_time": "1672502400",
      "start_time": "1643040000"
    },
    "delivery_delay_day": "2",
    "delivery_method": "7",
    "description": "<img src=\\\"https://tosv.boe.byted.org/obj/temai/54cbf542128eff94a3549284817c0af5bf5c2960www800-800\\\" style=\\\"width:100%;\\\">",
    "discount_price": "12000",
    "draft_status": "2",
    "extra": "-",
    "freight_id": "123",
    "img": "https://xxxx.byted.org/obj/temai/54cbf542128eff94a3549284817c0af5bf5c2960www800-800",
    "is_create": "1",
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
    "main_product_id": "3121213",
    "market_price": "12000",
    "material_video_id": "Vaaxxaa",
    "maximum_per_order": "5",
    "minimum_per_order": "1",
    "mobile": "15677775555",
    "name": "xxx爽肤水",
    "need_recharge_mode": "false",
    "open_user_id": "1",
    "out_product_id": "11111",
    "outer_product_id": "11111",
    "pay_type": "1",
    "pic": "[\"https://sf6-ttcdn-tos.pstatp.com/obj/temai/0c71ce6acb4e3b508e0d30042b1a94262818ab41www800-800\"]",
    "pickup_method": "0",
    "poi_resource": {
      "coupon_return_methods": "[1]"
    },
    "presell_config_level": "2",
    "presell_delay": "4",
    "presell_type": "1",
    "price_has_tax": "0",
    "product_format": "{\"货号\":\"8888\"}",
    "product_format_new": "{\"1088\":[{\"Value\":0,\"Name\":\"小33学二年级\",\"PropertyId\":1088,\"PropertyName\":\"适用学龄段\",\"diy_type\":1}],\"1319\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":1319,\"PropertyName\":\"适用地区\",\"diy_type\":0}],\"1618\":[{\"Value\":0,\"Name\":\"9787218122861\",\"PropertyId\":1618,\"PropertyName\":\"ISBN编号\",\"diy_type\":0}],\"1831\":[{\"Value\":0,\"Name\":\"小学英语看图说话写话二年级\",\"PropertyId\":1831,\"PropertyName\":\"书名\",\"diy_type\":0}],\"2000\":[{\"Value\":34762,\"Name\":\"无\",\"PropertyId\":2000,\"PropertyName\":\"作者地区\",\"diy_type\":0}],\"2229\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":2229,\"PropertyName\":\"编者\",\"diy_type\":0}],\"3271\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":3271,\"PropertyName\":\"出版时间\",\"diy_type\":0}],\"449\":[{\"Value\":0,\"Name\":\"1\",\"PropertyId\":449,\"PropertyName\":\"作者\",\"diy_type\":0}],\"501\":[{\"Value\":7310,\"Name\":\"否\",\"PropertyId\":501,\"PropertyName\":\"是否是套装\",\"diy_type\":0}],\"855\":[{\"Value\":0,\"Name\":\"陕西人民教育出版社\",\"PropertyId\":855,\"PropertyName\":\"出版社名称\",\"diy_type\":0}]}",
    "product_id": "3539925204033339668",
    "product_id_str": "3539925204033339668",
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
    "sale_channel_type": "sameAsOffline",
    "sale_limit_id": "123",
    "sell_channel": "[0]",
    "size_info_template_id": "7102988069296423000",
    "spec_id": "1",
    "spec_pics": [
      {
        "pic": "temai/b637513c50b994f4c89de56a17886caca5d6569awww800-800",
        "spec_detail_id": "1695459998447656"
      }
    ],
    "spec_prices": [
      {
        "code": "aaa",
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
        "delivery_infos": {
          "info_type": "weight",
          "info_unit": "当info_type=weight时，支持mg,g,kg三种类型",
          "info_value": "100"
        },
        "lock_step_stock_num": "1",
        "lock_stock_num": "1",
        "out_sku_id": "0",
        "outer_sku_id": "0",
        "presell_delay": "5",
        "price": "102",
        "prom_step_stock_num": "0",
        "prom_stock_num": "0",
        "promotion_step_stock_num": "0",
        "promotion_stock_num": "0",
        "sku_id": "1695459998495774",
        "sku_type": "0",
        "spec_detail_id1": "1695459998494734",
        "spec_detail_id2": "1695459998494734",
        "spec_detail_id3": "0",
        "spec_detail_ids": "[1695459998494734, 1695459998494766]",
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
        "spec_id": "1713023983665214",
        "values": [
          {
            "id": "1695459998447656",
            "is_leaf": "1",
            "name": "红色",
            "pid": "1695459998447640",
            "spec_id": "1713023983665214",
            "status": "1"
          }
        ]
      }
    ],
    "standard_brand_id": "121354",
    "status": "1",
    "store_id": "103121",
    "update_time": "2021-03-29T15:52:52+08:00",
    "white_back_ground_pic_url": "https://aaa"
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
  "sub_code": "isv.parameter-invalid:4",
  "sub_msg": "out_product_id未找到或商品已删除"
}
```

## 备注
