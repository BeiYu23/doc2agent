# superm.product.createSubProduct

> 基于店铺主品创建门店子品 (同步创建)

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.superm.product.createSubProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/product/createSubProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2698 |
| 更新日期 | `2024-11-22` |

## 接口说明

- 文档书: 商品API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `main_product_id` | body | mixed | 是 | 店铺主商品ID | `3576410646054571500` |
| `store_id` | body | mixed | 是 | 门店ID | `56386074` |
| `sku_info` | body | array | 否 | 子商品SKU的库存、价格信息 | `` |
| `  └ sell_property_names` | body | array | 是 | 子商品规格值列表 | `红色,XL` |
| `  └ price` | body | mixed | 否 | 子商品SKU价格 (单位：分) | `100` |
| `  └ stock` | body | mixed | 否 | 子商品SKU库存 | `1000` |
| `start_sale_type` | body | mixed | 否 | 审核通过后上架售卖时间配置：0-立即上架售卖 1-放入仓库 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/dutyFree/orderList?app_key=your_appkey_here&method=dutyFree.orderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sub_product_id` | mixed | 门店子商品ID | `3576410646054571501` |
| `sub_sku_infos` | array | sku信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |
| `50002` | 业务处理失败 / 2010005:<span>该商品的类目【奶粉/辅食/营养品/零食/宝宝辅食/果/菜/肉/混合泥】无资质授权,请前往<a href='/ffa/grs/qualification/list' target='_blank'>【店铺-店铺信息设置-店铺资质-行业资质】</a>中申请授权</span>（sub_code: isv.business-failed:2010005） | 2010005:<span>该商品的类目【奶粉/辅食/营养品/零食/宝宝辅食/果/菜/肉/混合泥】无资质授权,请前往<a href='/ffa/grs/qualification/list' target='_blank'>【店铺-店铺信息设置-店铺资质-行业资质】</a>中申请授权</span> |
| `50002` | 业务处理失败 / 110103017:重复创建渠道商品（sub_code: isv.business-failed:110103017） | 110103017:重复创建渠道商品 |
| `50002` | 业务处理失败 / 110102119:主商品非在线审核通过状态，不允许操作子商品（sub_code: isv.business-failed:110102119） | 110102119:主商品非在线审核通过状态，不允许操作子商品 |
| `50002` | 业务处理失败 / 2010001:获取账号信息失败（sub_code: isv.business-failed:2010001） | 2010001:获取账号信息失败 |
| `50002` | 业务处理失败 / 110210021:该商品对应的类目已处于禁发状态，需先修改商品对应类目为合适类目（sub_code: isv.business-failed:110210021） | 110210021:该商品对应的类目已处于禁发状态，需先修改商品对应类目为合适类目 |
| `50002` | 业务处理失败 / 2010053:所选类目经营资质已失效，您可以选择保存草稿，待资质审核通过后再提交（sub_code: isv.business-failed:2010053） | 2010053:所选类目经营资质已失效，您可以选择保存草稿，待资质审核通过后再提交 |
| `50002` | 业务处理失败 / 110101199:只支持门店创建子品（sub_code: isv.business-failed:110101199） | 110101199:只支持门店创建子品 |
| `50002` | 业务处理失败 / 2010058:商品不存在（sub_code: isv.business-failed:2010058） | 2010058:商品不存在 |
| `50002` | 业务处理失败 / 110103015:唯一码：4137397，唯一类型：外部商品ID 已被商品[3704216150360588337]占用（sub_code: isv.business-failed:110103015） | 110103015:唯一码：4137397，唯一类型：外部商品ID 已被商品[3704216150360588337]占用 |
| `50002` | 业务处理失败 / 110101198:门店不在主品店铺组织层级下（sub_code: isv.business-failed:110101198） | 110101198:门店不在主品店铺组织层级下 |
| `50002` | 业务处理失败 / 110102118:主品信息不合法（sub_code: isv.business-failed:110102118） | 110102118:主品信息不合法 |
| `50002` | 业务处理失败 / 2010004:传入SKU价格为0（sub_code: isv.business-failed:2010004） | 2010004:传入SKU价格为0 |
| `50002` | 业务处理失败 / 110103013:获取主子品差异化规则失败（sub_code: isv.business-failed:110103013） | 110103013:获取主子品差异化规则失败 |
| `50002` | 业务处理失败 / 2010012:当前商品的部分SKU库存不得低于活动/达人专属价设置的0，可到营销中心修改对应的活动/达人专属价库存，或直接修改当前商品库存数。（sub_code: isv.business-failed:2010012） | 2010012:当前商品的部分SKU库存不得低于活动/达人专属价设置的0，可到营销中心修改对应的活动/达人专属价库存，或直接修改当前商品库存数。 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "actural_paid": "2100",
        "buyer_id_number": "321312123243454",
        "buyer_id_type": "1",
        "buyer_name": "赵雷",
        "buyer_reg_no": "235345346454",
        "buyer_telephone": "15261890777",
        "consignee": "赵雷",
        "consignee_address": "{\"province\":{\"name\":\"江苏省\",\"id\":\"320000\"},\"city\":{\"name\":\"泰州市\",\"id\":\"321200\"},\"town\":{\"name\":\"姜堰区\",\"id\":\"321204\"},\"detail\":\"南苑二区5号楼102室\"}",
        "consignee_telephone": "15261890777",
        "create_time": "1624260016",
        "customs_clear_type": "4",
        "delivery_location": "**自提点地址",
        "delivery_method": "1",
        "discount": "400",
        "exp_ship_time": "1624260016",
        "freight": "0",
        "frequency_no": "HU7661",
        "goods_value": "2500",
        "leave_date": "1624260016",
        "leave_type": "2",
        "no_public_discount": "300",
        "order_date": "1624260016",
        "order_detail_list": [
          {
            "bar_code": "14324545",
            "cdf_category": "30",
            "coupon_amount": "300",
            "discount": "400",
            "fulldiscount_amount": "100",
            "is_suit": "1",
            "item_name": "SHERMY婴儿尿布裤",
            "original_price": "1250",
            "out_sku_id": "453464542343",
            "price": "1250",
            "qty": "2",
            "sku_id": "453464542343",
            "suit_num": "2",
            "total_price": "2500",
            "volume": "1000"
          }
        ],
        "order_id": "2021061619395010955",
        "pay_time": "1624260016",
        "pay_transaction_id": "2353453464542343",
        "pay_type": "1",
        "pre_sale_type": "1",
        "shop_id": "14802",
        "status": "100"
      }
    ],
    "has_next": "true",
    "total": "100"
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
  "sub_code": "isv.parameter-invalid:4100003",
  "sub_msg": "参数非法"
}
```

## 备注
