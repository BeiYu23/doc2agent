# logistics.newCreateOrder

> 商家ERP/ISV 向字节电子面单系统获取单号和打印信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.newCreateOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/newCreateOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1339 |
| 更新日期 | `2026-10-26` |

## 接口说明

- 文档书: 电子面单API（版本 V9.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sender_info` | body | object | 是 | 寄件人信息 | `` |
| `  └ address` | body | object | 是 | 寄件人地址信息（需要调用/logistics/listShopNetsite查询） | `` |
| `    └ city_name` | body | string | 是 | 市名称 | `市辖区` |
| `    └ district_name` | body | string | 是 | 区/县名称 | `海淀区` |
| `    └ country_code` | body | string | 是 | 国家编码（默认CHN，目前只有国内业务） | `CHN` |
| `    └ province_name` | body | string | 是 | 省名称 | `北京市` |
| `    └ street_name` | body | string | 否 | 街道名称 | `丹棱街1号` |
| `    └ detail_address` | body | string | 是 | 剩余详细地址 | `丹棱街1号` |
| `  └ contact` | body | object | 是 | 寄件人联系信息 | `` |
| `    └ phone` | body | string | 否 | 寄件人固话（和mobile二选一） | `1` |
| `    └ name` | body | string | 是 | 寄件人姓名 | `张三` |
| `    └ mobile` | body | string | 否 | 寄件人移动电话（和phone二选一） | `18500000034` |
| `logistics_code` | body | string | 是 | 物流服务商编码 | `jtexpress` |
| `order_infos` | body | array | 是 | 详细订单列表 | `` |
| `  └ shipping_code` | body | string | 否 | 物料码 | `SF24234234234234` |
| `  └ items` | body | array | 是 | 商品明细列表 | `` |
| `    └ item_specs` | body | string | 否 | 商品规格 | `1` |
| `    └ item_count` | body | mixed | 是 | 商品数量 | `1` |
| `    └ item_name` | body | string | 是 | 商品名称 | `手机` |
| `    └ item_volume` | body | mixed | 否 | 单件商品体积（cm3 | `1` |
| `    └ item_weight` | body | mixed | 否 | 单件商品重量（g) | `1` |
| `    └ item_net_weight` | body | mixed | 否 | 单件总净重量（g） | `1` |
| `  └ special_delivery_type_value` | body | string | 否 | 顺丰极效前置场景（必填）使用   Y:若不支持则返回普通运单 N:若不支持则返回错误码 | `Y` |
| `  └ pod_model_address` | body | object | 否 | 回单寄回地址 | `` |
| `    └ detail_address` | body | string | 是 | 剩余详细地址 | `宜山路` |
| `    └ country_code` | body | string | 是 | 国家编码（默认CHN，目前只有国内业务） | `CHN` |
| `    └ province_name` | body | string | 是 | 省名称 | `浙江省` |
| `    └ city_name` | body | string | 是 | 市名称 | `1` |
| `    └ street_name` | body | string | 否 | 街道名称 | `宜山路` |
| `    └ district_name` | body | string | 是 | 区/县名称 | `闵行区` |
| `  └ net_info` | body | object | 否 | 总对总信息门店信息 | `` |
| `    └ secret_key` | body | string | 否 | 总对总密码 | `ddfdfdf` |
| `    └ net_code` | body | string | 否 | 网点编码,当category为加盟类型时，该字段必填；为直营类型时可不传；对总模式该字段均为非必填 | `XS222` |
| `    └ monthly_account` | body | string | 否 | 总对总账号 月结账号 | `324322432` |
| `    └ category` | body | string | 否 | 物流服务商类型，直营/加盟 | `加盟` |
| `  └ total_height` | body | string | 否 | 商品总高，单位：cm（仅支持顺丰物流使用） | `1` |
| `  └ warehouse` | body | object | 否 | 仓、门店、总对总发货 | `` |
| `    └ is_sum_up` | body | boolean | 是 | true 总对总门店发货 | `true` |
| `    └ wh_order_no` | body | string | 否 | 仓库订单号(丹鸟等仓发链路使用) | `8837383` |
| `    └ wh_code` | body | string | 否 | 仓库id编码 | `1` |
| `    └ delivery_type` | body | string | 否 | 发货方式，2-门店发货 3-仓库发货（不传默认为3） | `2` |
| `  └ is_sign_back` | body | mixed | 否 | 是否返回签回单（签单返还）的运单号，支持以下值：1：要求 0：不要求\" | `0` |
| `  └ package_weight` | body | mixed | 否 | 包裹总重量（g）（丹鸟专用，其余物流商取号不要传该字段） | `100` |
| `  └ total_pack_count` | body | mixed | 否 | 子母件的总包裹数量，仅子母件场景使用，使用时包裹数量必须≥2，不传则默认为普通的一单一包裹运单。 | `子母件数` |
| `  └ total_length` | body | string | 否 | 商品总长，单位：cm（仅支持顺丰物流使用） | `1` |
| `  └ sender_fetch_time` | body | string | 否 | 要求上门取件时间段 | `2020-11-11 22:00:00\|2020-11-11 23:00:00` |
| `  └ total_weight` | body | string | 否 | 商品总重量，单位：克（仅支持顺丰物流使用） | `1` |
| `  └ volume` | body | string | 否 | 商品总体积，单位：cm3（仅支持顺丰物流使用） | `1` |
| `  └ product_type` | body | string | 否 | 快递产品类型，更多产品类型参考[抖音电商电子面单对接文档](https://bytedance.feishu.cn/wiki/wikcnNVdm3TlJutNCUlKmiVuwnf) | `1` |
| `  └ combine_orders` | body | array | 否 | 包裹涉及到的所有订单号/售后单号信息，合单取号场景下必传 | `["49111111","49111112"]` |
| `  └ remark` | body | string | 否 | 订单备注 | `我的包裹易碎，包严实点` |
| `  └ special_delivery_type_code` | body | string | 否 | 顺丰极效前置场景（必填）使用  2:极效前置单 | `2` |
| `  └ pack_id` | body | string | 否 | 包裹id。拆包（一个订单获取多个独立的运单，非子母件）场景使用，只能传入15位以内的数字、字母和下划线，大小写敏感（即123A,123a为不同包裹id），仅第2个及以后的运单取号时传不同id。 | `1` |
| `  └ service_list` | body | array | 否 | 增值服务列表，更多增值服务参考[抖音电商电子面单对接文档](https://bytedance.feishu.cn/wiki/wikcnNVdm3TlJutNCUlKmiVuwnf) | `` |
| `    └ service_value` | body | string | 否 | 增值服务对应的value值，如果增值类型涉及金额会校验，单位：分 | `{\"value\":\"2200\"}` |
| `    └ service_code` | body | string | 否 | 增值服务类型 | `SVC-INSURE` |
| `  └ pay_amount` | body | mixed | 否 | 运费金额，单位为分 | `5000` |
| `  └ extra` | body | string | 否 | 备用扩展字段（非必传字段，如果传值不可为"null",按照示例来传。） | `"extra":"{\"sfOtherInfo\":\"{\\\"e1\\\":\\\"GUER\\\",\\\"e2\\\":\\\"DOUYIN\\\"}\"}",` |
| `  └ order_id` | body | string | 是 | 抖音订单请传入正向店铺单ID或售后单ID（合单情况下，isv只需传其中一个订单号，其他的合单订单号，请统一传入combine_orders字段)；非抖音订单需要传order_channel字段，长度仅支持32个字符，格式：数字、大小写字母及“-”、“/”2种分隔符的组合字符串，例如：Doudian-123456 | `202011809` |
| `  └ pay_method` | body | mixed | 否 | 支付方式：1-寄付月结，2-寄付现结）若不传，默认为商家与物流商网点约定的支付方式 | `1` |
| `  └ receiver_info` | body | object | 是 | 收件人信息 | `` |
| `    └ address` | body | object | 是 | 收件人地址信息 | `` |
| `      └ province_name` | body | string | 是 | 省名称 | `北京市` |
| `      └ street_code` | body | string | 否 | 街道编码code | `11111111` |
| `      └ street_name` | body | string | 否 | 街道名称 | `丹棱街1号` |
| `      └ city_code` | body | string | 否 | 市编码code | `1111` |
| `      └ district_name` | body | string | 是 | 区/县名称 | `海淀区` |
| `      └ country_code` | body | string | 是 | 国家编码（默认中国CHN） | `CHN` |
| `      └ province_code` | body | string | 否 | 省编码code | `11` |
| `      └ detail_address` | body | string | 是 | 剩余详细地址，支持密文 | `丹棱街1号` |
| `      └ city_name` | body | string | 是 | 市名称 | `市辖区` |
| `      └ district_code` | body | string | 否 | 区编码code | `111111` |
| `    └ contact` | body | object | 是 | 收件人联系信息 | `` |
| `      └ name` | body | string | 是 | 收件人姓名，支持密文 | `李四` |
| `      └ mobile` | body | string | 否 | 收件人移动电话（和phone二选一），支持密文 | `18500000034` |
| `      └ phone` | body | string | 否 | 收件人固话（和mobile二选一） | `1` |
| `  └ total_width` | body | string | 否 | 商品总宽，单位：cm（仅支持顺丰物流使用） | `1` |
| `user_id` | body | mixed | 否 | 共享账号场景下需传，代表实际使用取号服务的shop_id（需与order_id匹配） | `1` |
| `delivery_req` | body | object | 否 | 派送要求（目前仅德邦支持） | `` |
| `  └ is_pickup_self` | body | boolean | 否 | true | `是否合伙人自提` |
| `  └ is_center_delivery` | body | boolean | 否 | true | `是否接受仅镇中心派送` |
| `order_channel` | body | string | 否 | 订单渠道来源编码，具体请参考[下单渠道来源编码表](https://bytedance.feishu.cn/sheets/shtcngIVwcJlgXLzWhEtKrmv7Af)，当order_id订单号为非抖音订单时必传 | `1` |
| `ebill_delivery_info` | body | object | 否 | 发货场景结构体，仅在线寄件场景使用，其余场景请不要传 | `` |
| `  └ scene` | body | string | 否 | 仅在线寄件场景使用，枚举（OnlineShip），其余场景请不要传 | `场景` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/newCreateOrder?app_key=your_appkey_here&method=logistics.newCreateOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ebill_infos` | array | 电子面单信息列表 | `` |
| `err_infos` | array | 错误信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 共享订单不存在（sub_code: isv.parameter-invalid:10003） | 检查参数是否准确 |
| `40004` | 非法的参数 / 寄件人姓名不能为空（sub_code: isv.parameter-invalid:4006） | 检查参数是否准确 |
| `40004` | 非法的参数 / 拼接参数异常（sub_code: isv.parameter-invalid:1000） | 检查参数是否准确 |
| `50002` | 业务处理失败 / 查询订单信息失败，请重试（sub_code: isv.business-failed:4007） | 检查参数是否准确，如果确认无误提工单或者群里反馈 |
| `50002` | 业务处理失败 / 订单不是该店铺下的订单（sub_code: isv.business-failed:15000） | 切换店铺或更换订单号 |
| `50002` | 业务处理失败 / 订单信息不存在（sub_code: isv.business-failed:15002） | 确认订单信息是否正确 |
| `20000` | 系统错误（sub_code: isp.service-error:15001） | 稍后重试 |
| `50002` | 业务处理失败 / 系统内部错误（sub_code: isv.business-failed:4029） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "ebill_infos": [
      {
        "company": "zhongtong",
        "extra_resp": "1",
        "hint_msg": "您传入的收件地址与订单不一致，已采用平台订单地址完成取号",
        "order_channel": "c",
        "order_id": "202011809",
        "pack_id": "1",
        "package_center_code": "1",
        "package_center_name": "1",
        "shipping_code": "34343",
        "short_address_code": "1",
        "short_address_name": "1",
        "sort_code": "400-W00 000",
        "sub_waybill_codes": "13,434,556",
        "track_no": "202011809"
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
  "sub_code": "isv.parameter-invalid:10003",
  "sub_msg": "共享订单不存在"
}
```

## 备注
