# logistics.getOutRange

> 查询地址快递是否可以送达

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.getOutRange` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getOutRange` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/582 |
| 更新日期 | `2026-08-12` |

## 接口说明

- 文档书: 电子面单API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 是 | 快递公司编码 | `jtexpress` |
| `sender_address` | body | object | 否 | 发货地址 | `` |
| `  └ city_name` | body | string | 是 | 城市名称 | `杭州市` |
| `  └ district_name` | body | string | 是 | 区名称 | `滨江区` |
| `  └ street_name` | body | string | 否 | 街道名称 | `长河街道` |
| `  └ country_code` | body | string | 是 | CHN | `CHN` |
| `  └ detail_address` | body | string | 是 | 详细地址 | `XX小区X幢` |
| `  └ province_name` | body | string | 是 | 省份名称 | `浙江省` |
| `receiver_address` | body | object | 否 | 收件地址 | `` |
| `  └ city_name` | body | string | 是 | 城市名称 | `杭州市` |
| `  └ district_name` | body | string | 是 | 区名称 | `滨江区` |
| `  └ detail_address` | body | string | 是 | 详细地址，支持密文 | `XX小区X幢` |
| `  └ country_code` | body | string | 是 | CHN | `CHN` |
| `  └ street_name` | body | string | 否 | 街道名称 | `长河街道` |
| `  └ province_name` | body | string | 是 | 省份名称 | `浙江省` |
| `type` | body | mixed | 是 | 类型（0-揽派合一；1-揽收区域；2-派送区域） 0：取senderAddress, receiverAddress值 1：取senderAddress值 2：取receiverAddress值 | `1` |
| `service_list` | body | array | 否 | 增值服务 目前只支持德邦 | `` |
| `  └ service_value` | body | string | 否 | value | `100` |
| `  └ service_code` | body | string | 否 | code | `SVC-INSURE` |
| `product_type` | body | string | 否 | 产品类型 目前只支持德邦 | `ll-sd-m` |
| `delivery_req` | body | object | 否 | 投递要求 目前只支持德邦 | `` |
| `  └ is_center_delivery` | body | boolean | 否 | 是否接受仅镇中心派送  目前仅支持德邦 | `true` |
| `  └ is_pickup_self` | body | boolean | 否 | 是否接受合伙人自提，目前仅支持德邦 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getOutRange?app_key=your_appkey_here&method=logistics.getOutRange&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_out_range` | boolean | 是否超区响应结果（超区-true；未超区-fasle） | `false` |
| `out_range_reason` | string | 超区原因，1、疫情管控 2、洪涝台风等自然灾害 3、特殊会议管控 4、网点经营问题 5、其他原因 | `地址未覆盖` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 请求物流服务商超时（sub_code: isp.service-error:4009） | 可等待一段时间进行重试 |
| `50002` | 业务处理失败 / 内部数据格式非法（sub_code: isv.business-failed:4008） | 可等待一段时间进行重试 |
| `20000` | 系统错误 / 请求物流服务商异常，请重试（sub_code: isp.service-error:4007） | 可等待一段时间进行重试 |
| `40004` | 非法的参数 / youzhengguonei 物流服务商不支持该接口（sub_code: isv.parameter-invalid:4006） | 以文档上面支持的为准 |
| `50002` | 业务处理失败 / 500:发生异常，请咨询对接人（sub_code: isv.business-failed:500） | 无 |
| `50002` | 业务处理失败 / 10002:服务异常～（sub_code: isv.business-failed:10002） | 无 |
| `50002` | 业务处理失败 / 3017:筛单异常（sub_code: isv.business-failed:3017） | 无 |
| `50002` | 业务处理失败 / 1000:request param [receiverAddress.detailAddress] can not be null（sub_code: isv.business-failed:1000） | 1000:request param [receiverAddress.detailAddress] can not be null |
| `50002` | 业务处理失败 / 9020501:请求失败，请重试（sub_code: isv.business-failed:9020501） | 请重试 |
| `50002` | 业务处理失败 / 4001:系统发生数据错误或运行时异常（sub_code: isv.business-failed:4001） | 统发生数据错误或运行时异常 |
| `50002` | 业务处理失败 / 10001:无效签名（sub_code: isv.business-failed:10001） | 无效签名 |
| `50002` | 业务处理失败 / 11102:收件地址解析失败（sub_code: isv.business-failed:11102） | 请检查收件地址信息 |
| `50002` | 业务处理失败 / 11108:{"outRangeRsason":"该收件地址属于偏远地区暂时无法下单。","isOutRange":true}（sub_code: isv.business-failed:11108） | 请调整地址 |

## 响应示例

成功：

```json
{
  "data": {
    "is_out_range": "false",
    "out_range_reason": "地址未覆盖"
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
  "sub_code": "isp.service-error:4009",
  "sub_msg": "请求物流服务商超时"
}
```

## 备注
