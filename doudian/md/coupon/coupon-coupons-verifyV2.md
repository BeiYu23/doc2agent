# coupons.verifyV2

> 卡券核销接口V2版本

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.coupon.coupons.verifyV2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/verifyV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/52/797 |
| 更新日期 | `2026-10-20` |

## 接口说明

- 文档书: 卡券API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cert_no` | body | string | 是 | 卡券号码 | `123456` |
| `verify_time` | body | string | 否 | 核销时间 | `2021-03-04 00:00：00` |
| `batch_no` | body | string | 否 | 幂等请求id | `3` |
| `verify_count` | body | mixed | 否 | 当次核销的次数 | `12345` |
| `cert_key` | body | string | 否 | 卡券密码 | `12345` |
| `cert_type` | body | mixed | 否 | 卡券类型：0-电商三方卡券，1-即时零售提货券/电商服饰自提/电商到店安装场景（请传入1），不传默认是0（电商三方卡券）核销方式 | `123` |
| `store_id` | body | mixed | 否 | 门店Id（提货券核销必传） | `123` |
| `verify_order_id` | body | string | 否 | 三方订单Id | `123123` |
| `check_verify_order_id` | body | boolean | 否 | 是否检查订单Id（verify_order_id）和卡券号码（cert_no）的关联关系 | `false` |
| `vehicle_identity` | body | string | 否 | 车架码（电动车自提） | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/verifyV2?app_key=your_appkey_here&method=coupons.verifyV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:000002） | 参数错误 |
| `50002` | 业务处理失败 / 010002:非未使用状态电子凭证禁止核销（sub_code: isv.business-failed:010002） | 010002:非未使用状态电子凭证禁止核销 |
| `50002` | 业务处理失败 / 030001:UpdateCertInfo error（sub_code: isv.business-failed:030001） | 030001:UpdateCertInfo error |
| `50002` | 业务处理失败 / 核销码与订单不匹配，请重新核对订单（sub_code: isv.business-failed:010021） | 核销码与订单不匹配，请重新核对订单 |
| `50002` | 业务处理失败 / 010009:核销数量超出最大可核销数量（sub_code: isv.business-failed:010009） | 010009:核销数量超出最大可核销数量 |
| `50002` | 业务处理失败 / 010017:未在有效期内禁止核销（sub_code: isv.business-failed:010017） | 010017:未在有效期内禁止核销 |
| `50002` | 业务处理失败 / 010006:找不到该电子凭证（sub_code: isv.business-failed:10006） | 找不到该电子凭证 |
| `50002` | 业务处理失败 / 010014:卡密校验失败（sub_code: isv.business-failed:010014） | 010014:卡密校验失败 |
| `50002` | 业务处理失败 / 010016:订单中还存在未处理的售后，请先完成售后单处理（sub_code: isv.business-failed:010016） | 010016:订单中还存在未处理的售后，请先完成售后单处理 |
| `50002` | 业务处理失败 / 1（sub_code: isv.business-failed:9） | 1 |
| `50002` | 业务处理失败 / 2（sub_code: isv.business-failed:8） | 2 |
| `50002` | 业务处理失败 / 3（sub_code: isv.business-failed:30002） | 3 |
| `50002` | 业务处理失败 / 009999:系统内部错误（sub_code: isv.business-failed:9999） | 009999:系统内部错误 |
| `50002` | 业务处理失败 / 020005:查询订单失败（sub_code: isv.business-failed:20005） | 020005:查询订单失败 |
| `50002` | 业务处理失败 / 020008:卡券查询失败（sub_code: isv.business-failed:20008） | 020008:卡券查询失败 |
| `50002` | 业务处理失败 / 020027:门店查询失败（sub_code: isv.business-failed:20027） | 020027:门店查询失败 |
| `50002` | 业务处理失败 / 020011:ByteScheduler处理失败（sub_code: isv.business-failed:20011） | 020011:ByteScheduler处理失败 |
| `40004` | 非法的参数 / 订单与核销码不匹配，请重新核对订单（sub_code: isv.parameter-invalid:020014） | 订单与核销码不匹配，请重新核对订单 |
| `50002` | 业务处理失败 / 010029:并发请求,请稍后重试（sub_code: isv.business-failed:10029） | 请重试 |
| `50002` | 业务处理失败 / 门店状态异常，无法核销，请联系商家（sub_code: isv.business-failed:20025） | 门店状态异常，无法核销，请联系商家 |
| `50002` | 业务处理失败 / 核销门店id未正确传参（sub_code: isv.business-failed:20024） | 核销门店id未正确传参 |
| `50002` | 业务处理失败 / 不允许跨城市核销，请联系商家（sub_code: isv.business-failed:20032） | 不允许跨城市核销，请联系商家 |
| `50002` | 业务处理失败 / 车架码不存在，请核对信息（sub_code: isv.business-failed:020034） | 车架码不存在，请核对信息 |
| `50002` | 业务处理失败 / 010031:缺少车架号等发票必填信息（sub_code: isv.business-failed:10031） | 010031:缺少车架号等发票必填信息 |

## 响应示例

成功：

```json
{
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:000002",
  "sub_msg": "参数错误"
}
```

## 备注
