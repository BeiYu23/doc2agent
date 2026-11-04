# instantShopping.logistics.newCreateOrder

> 取号接口，传入收货人密文获取运单号

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-waybill.instantShopping.logistics.newCreateOrder` |
| 中文名 | 取号接口，传入收货人密文获取运单号 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1578/7242 |
| 更新日期 | `2026-08-13` |

## 接口说明

- 文档书: 电子面单API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 否 | 物流商编码 | `jtexpress` |
| `sender_info` | body | object | 是 | 寄件人信息 | `` |
| `  └ address` | body | object | 是 | 寄件人地址信息 | `` |
| `    └ street_name` | body | string | 否 | 街道名称 | `丹棱街1号` |
| `    └ city_name` | body | string | 是 | 城市名称 | `北京市` |
| `    └ country_code` | body | string | 是 | 国家编码（默认CHN，目前只有国内业务） | `CHN` |
| `    └ detail_address` | body | string | 是 | 详细地址 | `丹棱街1号` |
| `    └ province_name` | body | string | 是 | 省名称 | `北京市` |
| `    └ district_name` | body | string | 是 | 地区名称 | `海淀区` |
| `  └ contact` | body | object | 是 | 联系方式 | `` |
| `    └ name` | body | string | 是 | 名称 | `-` |
| `    └ phone` | body | string | 否 | 收件人固话（和mobile二选一） | `-` |
| `    └ mobile` | body | string | 否 | 收件人移动电话（和phone二选一），支持密文 | `-` |
| `order_channel` | body | string | 否 | 订单渠道来源编码，具体请参考[下单渠道来源编码表](https://bytedance.feishu.cn/sheets/shtcngIVwcJlgXLzWhEtKrmv7Af)，当order_id订单号为非抖音订单时必传 | `1` |
| `delivery_req` | body | object | 否 | 派送要求（目前仅德邦支持） | `` |
| `  └ is_center_delivery` | body | boolean | 否 | 条件，物流商=德邦时，该字段必须有值，前端系统（ISV、商家后台等前端传值以传入的值为准；未传值，默认传false） 是否接受仅镇中心派送 | `true` |
| `  └ is_pickup_self` | body | boolean | 否 | 条件，物流商=德邦时，该字段必须有值，前端系统（ISV、商家后台等前端传值以传入的值为准；未传值，默认传false）是否合伙人自提 | `true` |
| `store_id` | body | mixed | 是 | 门店id | `-` |
| `order_infos` | body | array | 是 | 详细订单列表 | `` |
| `  └ pay_method` | body | mixed | 否 | 支付方式（1-寄付，2-到付，3-第三方付）不传默认为寄付 | `1` |
| `  └ order_id` | body | string | 是 | 订单号（合单情况下，isv只需传其中一个订单号） | `112322` |
| `  └ total_pack_count` | body | mixed | 否 | 包裹总数，本期不支持子母单，传1 | `1` |
| `  └ volume` | body | string | 否 | 订单货物总体积，单位立方厘米,精确到小数点后3位，会用于计抛 | `1` |
| `  └ pack_id` | body | string | 否 | 包裹id。拆包（一个订单获取多个独立的运单，非子母件）场景使用，只能传入15位以内的数字、字母和下划线，大小写敏感（即123A,123a为不同包裹id），仅第2个及以后的运单取号时传不同id。 | `1` |
| `  └ sender_fetch_time` | body | string | 否 | 要求上门取件时间段 | `2020-11-11 22:00:00\|2020-11-11 23:00:00` |
| `  └ special_delivery_type_value` | body | string | 否 | 顺丰极效前置场景（必填）使用  2:极效前置单 | `1` |
| `  └ shipping_code` | body | string | 否 | 寄件码/运单号，根据快递商提供的服务决定 一个订单只能有一个主单号；若是子母单的情况，主运单号（母运单号）在首位，子运单号以半角逗号分隔 | `1` |
| `  └ product_type` | body | string | 否 | 产品类型 | `1` |
| `  └ warehouse` | body | object | 否 | 仓相关信息 | `` |
| `    └ wh_order_no` | body | string | 否 | 仓库订单号(丹鸟等仓发链路使用) | `8837383` |
| `    └ delivery_type` | body | string | 否 | 发货方式（用于韵达、京东链路）1或不传-普通发货2-门店发货3-仓库发货 | `2` |
| `    └ wh_code` | body | string | 否 | 仓库编码 | `1` |
| `    └ is_sumup` | body | boolean | 是 | 是否为总对总 | `true` |
| `  └ total_width` | body | string | 否 | 客户订单货物总宽，单位厘米，精确到小数点后3位，包含子母件 | `1` |
| `  └ remark` | body | string | 否 | 备注 | `1` |
| `  └ items` | body | array | 是 | 商品明细信息 | `` |
| `    └ item_net_weight` | body | mixed | 否 | 总净重量 | `-` |
| `    └ item_volume` | body | mixed | 否 | 体积 | `-` |
| `    └ item_specs` | body | string | 否 | 商品规格 | `-` |
| `    └ item_name` | body | string | 是 | 商品名称 | `手机` |
| `    └ item_weight` | body | mixed | 否 | 总重量 | `-` |
| `    └ item_count` | body | mixed | 是 | 商品数量 | `-` |
| `  └ net_info` | body | object | 否 | 网点信息 | `` |
| `    └ secret_key` | body | string | 否 | 总对总时的密码 | `ddfdfdf` |
| `    └ category` | body | string | 否 | 物流服务商类型（直营or加盟）可不穿 | `加盟` |
| `    └ net_code` | body | string | 否 | 网点编码,当category为加盟类型时，该字段必填；为直营类型时可不传；对总模式该字段均为非必填 | `XS222` |
| `    └ monthly_account` | body | string | 否 | 月结账号，当类型字段为直营制时，则该字段会用到，加盟制时无需使用； 总对总时的账号 | `324322432` |
| `  └ total_height` | body | string | 否 | 客户订单货物总高，单位厘米，精确到小数点后3位，包含子母件 | `1` |
| `  └ receiver_info` | body | object | 是 | 收件人信息 | `` |
| `    └ address` | body | object | 是 | - | `` |
| `      └ city_code` | body | string | 否 | 市编码code | `111` |
| `      └ province_code` | body | string | 否 | 省编码code | `11` |
| `      └ street_code` | body | string | 否 | 街道编码code | `11111` |
| `      └ country_code` | body | string | 是 | 国家编码CHN | `CHN` |
| `      └ district_name` | body | string | 是 | 区/县名称 | `海淀区` |
| `      └ street_name` | body | string | 否 | 街道名称 | `丹棱街1号` |
| `      └ province_name` | body | string | 是 | 省名称 | `北京市` |
| `      └ detail_address` | body | string | 是 | 剩余详细地址，支持密文 | `丹棱街1号` |
| `      └ district_code` | body | string | 否 | 区编码code | `1111` |
| `      └ city_name` | body | string | 是 | 城市名称 | `市辖区` |
| `    └ contact` | body | object | 是 | - | `` |
| `      └ phone` | body | string | 否 | 收件人固话（和mobile二选一） | `-` |
| `      └ name` | body | string | 是 | 名称 | `-` |
| `      └ mobile` | body | string | 否 | 收件人移动电话（和phone二选一），支持密文 | `-` |
| `  └ extra` | body | string | 否 | 备用扩展字段 | `1` |
| `  └ total_length` | body | string | 否 | 客户订单货物总长，单位厘米，精确到小数点后3位，包含子母件 | `1` |
| `  └ total_weight` | body | string | 否 | 订单货物总重量，若为子母件必填，单位克,如果提供此值，必须>0 (子母件需>6) | `1` |
| `  └ package_weight` | body | mixed | 否 | 包裹总重量 | `1` |
| `  └ service_list` | body | array | 否 | 增值服务列表 | `` |
| `    └ service_value` | body | string | 否 | 增值服务对应的value值 "{\"value\":\"1000000\", \"value1\":\"\",\"value2\":\"\"}" | `{\"value\":\"2200\"}` |
| `    └ service_code` | body | string | 否 | 增值服务类型 | `SVC-INSURE` |
| `  └ combine_orders` | body | array | 否 | 合单场景的订单列表 | `1` |
| `  └ special_delivery_type_code` | body | string | 否 | 顺丰极效前置场景使用 | `1` |
| `  └ pay_amount` | body | mixed | 否 | 到付运费金额，单位为分 | `11` |
| `user_id` | body | mixed | 否 | 单号使用用户ID | `1` |
| `out_warehouse_id` | body | mixed | 否 | 发货仓id，次日达发货仓取号需要，不同仓的订单必须分开调用接口取号 | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logistics.newCreateOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `err_infos` | array | 错误信息列表 | `` |
| `e_bill_infos` | array | 电子面单信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:40004） | 参数非法 |
| `40004` | 非法的参数 / 共享订单不存在（sub_code: isv.parameter-invalid:10003） | 检查参数是否准确 |
| `40004` | 非法的参数 / 寄件人姓名不能为空（sub_code: isv.parameter-invalid:4006） | 检查参数是否准确 |
| `40004` | 非法的参数 / 拼接参数异常（sub_code: isv.parameter-invalid:1000） | 检查参数是否准确 |
| `50002` | 业务处理失败 / 查询订单信息失败，请重试（sub_code: isv.business-failed:4007） | 检查参数是否准确，如果确认无误提工单或者群里反馈 |
| `50002` | 业务处理失败 / 订单不是该店铺下的订单（sub_code: isv.business-failed:15000） | 切换店铺或更换订单号 |
| `50002` | 业务处理失败 / 订单信息不存在（sub_code: isv.business-failed:15002） | 确认订单信息是否正确 |
| `20000` | 系统错误（sub_code: isp.service-error:15001） | 稍后重试 |
| `50002` | 业务处理失败 / 系统内部错误（sub_code: isv.business-failed:4029） | 稍后重试 |
| `50002` | 业务处理失败 / 1004:Internal Server Error（sub_code: isv.business-failed:1004） | 业务处理失败 |
| `50002` | 业务处理失败 / 40001:仅支持抖音渠道订单（sub_code: isv.business-failed:40001） | 仅支持抖音渠道订单 |

## 响应示例

成功：

```json
{
  "data": {
    "e_bill_infos": [
      {
        "company": "zhongtong",
        "extra": "1",
        "extra_resp": "1",
        "hint_code": "1",
        "hint_msg": "您传入的收件地址与订单不一致，已采用平台订单地址完成取号",
        "mark_destination_code": "1",
        "mark_destination_code_name": "1",
        "order_channel": "1",
        "order_id": "202011809",
        "pack_id": "1",
        "package_code": "1",
        "package_code_name": "1",
        "shipping_code": "1",
        "sort_code": "1",
        "sub_waybill_codes": "1",
        "track_no": "1"
      }
    ],
    "err_infos": [
      {
        "err_code": "10701",
        "err_msg": "电子面单库存不足",
        "order_channel": "2",
        "order_id": "1",
        "pack_id": "1"
      }
    ]
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
  "sub_code": "isv.parameter-invalid:40004",
  "sub_msg": "非法的参数"
}
```

## 备注
