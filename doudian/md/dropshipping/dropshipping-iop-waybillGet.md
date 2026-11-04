# 电子面单取号

> iop.waybillGet — 电子面单取号

| 元信息 | 值 |
| --- | --- |
| 中文名 | 电子面单取号 |
| 文档地址 | `/docs/doudian/dropshipping/dropshipping-iop-waybillGet` |
| 接口 ID | `doudian.dropshipping.iop.waybillGet` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/waybillGet` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/674 |
| 更新日期 | `2021-09-15` |

## 接口说明

- 文档书: 代发API（版本 V3.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sender` | body | object | 是 | 寄件人信息 | `` |
| `  └ contact` | body | object | 是 | 寄件人联系信息 | `` |
| `    └ name` | body | string | 是 | 寄件人姓名 | `张三` |
| `    └ phone` | body | string | 否 | 寄件人固话（和mobile二选一） | `1` |
| `    └ mobile` | body | string | 否 | 寄件人移动电话（和phone二选一） | `18500000034` |
| `  └ address` | body | object | 是 | 寄件人地址信息 | `` |
| `    └ countryCode` | body | string | 是 | 国家编码（默认CHN，目前只有国内业务） | `CHN` |
| `    └ provinceCode` | body | string | 否 | 省编码 | `112` |
| `    └ provinceName` | body | string | 是 | 省名称 | `北京市` |
| `    └ cityCode` | body | string | 否 | 市编码 | `112` |
| `    └ cityName` | body | string | 是 | 市名称 | `北京市` |
| `    └ districtCode` | body | string | 否 | 区/县编码 | `112` |
| `    └ districtName` | body | string | 是 | 区/县名称 | `海淀区` |
| `    └ streetCode` | body | string | 否 | 街道编码 | `112` |
| `    └ streetName` | body | string | 否 | 街道名称 | `丹棱街1号` |
| `    └ detailAddress` | body | string | 是 | 剩余详细地址 | `丹棱街1号` |
| `trade_order_list` | body | array | 是 | 取号列表 | `` |
| `  └ user_id` | body | number | 是 | 代打店铺id | `884334435345` |
| `  └ order_infos` | body | array | 是 | 代打订单列表 | `` |
| `    └ service_list` | body | array | 否 | 增值服务列表 | `` |
| `      └ service_code` | body | string | 是 | 增值服务类型 | `SVC-INSURE` |
| `      └ service_value` | body | string | 是 | 增值服务对应的value值，如果增值类型涉及金额会校验，单位：分 | `["value":"2200"]` |
| `    └ product_type` | body | string | 否 | 快递产品类型 | `1` |
| `    └ pay_method` | body | string | 否 | 支付方式：1-寄付月结，2-寄付现结）若不传，默认为商家与物流商网点约定的支付方式 | `1` |
| `    └ distr_order_id` | body | string | 是 | 代打订单id | `7874584357345` |
| `    └ items` | body | array | 是 | 商品明细列表 | `` |
| `      └ item_name` | body | string | 是 | 商品名称 | `手机` |
| `      └ item_specs` | body | string | 否 | 商品规格 | `绿色/小` |
| `      └ item_count` | body | string | 是 | 商品数量 | `1` |
| `      └ item_volume` | body | string | 否 | 单件商品体积（cm3) | `1` |
| `      └ item_weight` | body | string | 否 | 单件商品重量（g) | `1` |
| `      └ item_net_weight` | body | string | 否 | 单件总净重量（g） | `1` |
| `    └ sender_fetch_time` | body | string | 否 | 要求上门取件时间段 | `2020-11-11 22:00:00\|2020-11-11 23:00:00` |
| `    └ is_sign_back` | body | string | 否 | 是否返回签回单（签单返还）的运单号，支持以下值：1：要求 0：不要求" | `0` |
| `    └ remark` | body | string | 否 | 订单备注 | `我的包裹易碎，包严实点` |
| `    └ extra` | body | string | 否 | 备用扩展字段 | `1` |
| `    └ pay_amount` | body | number | 否 | 运费金额，单位为分 | `5000` |
| `    └ total_pack_count` | body | string | 否 | 大于1，示例3 | `子母件数` |
| `    └ total_weight` | body | string | 否 | 商品总重量，单位：克（仅支持顺丰物流使用） | `1` |
| `    └ total_length` | body | string | 否 | 商品总长，单位：cm（仅支持顺丰物流使用） | `1` |
| `    └ total_width` | body | string | 否 | 商品总宽，单位：cm（仅支持顺丰物流使用） | `1` |
| `    └ total_height` | body | string | 否 | 商品总高，单位：cm（仅支持顺丰物流使用） | `1` |
| `    └ volume` | body | string | 否 | 商品总体积，单位：cm3（仅支持顺丰物流使用） | `1` |
| `    └ pack_id` | body | string | 否 | 包裹id（只能传入数字、字母和下划线；大小写敏感，即123A,123a 不可当做相同ID，否则存在一定可能取号失败）一单一包裹是不需要传，有2个以上时，从第二个开始都需要传不同id | `0` |
| `    └ warehouse` | body | object | 否 | 仓相关信息 | `` |
| `      └ wh_code` | body | string | 否 | 仓库编码 | `1` |
| `      └ delivery_type` | body | string | 否 | 发货方式（用于韵达、京东链路）1或不传-普通发货2-门店发货3-仓库发货 | `1` |
| `      └ wh_order_no` | body | string | 否 | 仓库订单号(丹鸟等仓发链路使用) | `1` |
| `  └ delivery_req` | body | object | 否 | 派送要求（目前仅德邦支持） | `` |
| `    └ is_center_delivery` | body | boolean | 否 | 是否接受仅镇中心派送 | `true` |
| `    └ is_pickup_self` | body | boolean | 否 | 是否合伙人自提 | `true` |
| `  └ company_code` | body | string | 是 | 物流服务商编码 | `jtexpress` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillGet?app_key=your_appkey_here&method=iop.waybillGet&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `40004` | 非法的参数 / 取号信息一次最多支持10个（sub_code: isv.parameter-invalid:10000） | 取号信息一次最多支持10个 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:88888） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10005） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "ebill_infos": [
      {
        "distr_order_id": "7874584357345",
        "extra": "1",
        "extra_resp": "1",
        "mark_destination_code": "1",
        "mark_destination_code_name": "1",
        "pack_id": "0",
        "package_code": "1",
        "package_code_name": "1",
        "sort_code": "400-W00 000",
        "sub_waybill_codes": "13,434,556",
        "track_no": "202011809"
      }
    ],
    "err_infos": [
      {
        "distr_order_id": "7874584357345",
        "err_code": "10701",
        "err_msg": "电子面单库存不足",
        "pack_id": "0"
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
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "取号信息一次最多支持10个"
}
```

## 备注
