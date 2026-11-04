# 商家接单（触发平台发码

> coupons.SendCodeByPlatform — 商家接单（触发平台发码）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家接单（触发平台发码 |
| 文档地址 | `/docs/doudian/order/order-coupons-SendCodeByPlatform` |
| 接口 ID | `doudian.order.coupons.SendCodeByPlatform` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/SendCodeByPlatform` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7110 |
| 更新日期 | `2025-09-11` |

## 接口说明

- 文档书: 订单API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 店铺单号 | `693434343434343421` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/SendCodeByPlatform?app_key=your_appkey_here&method=coupons.SendCodeByPlatform&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:000002） | 参数错误 |
| `20000` | 系统错误 / 系统异常,请稍后重试（sub_code: isp.service-error:030001） | 数据库访问异常 |
| `20000` | 系统错误 / 系统内部异常,请求失败,等待人工处理（sub_code: isp.service-error:010003） | 订单为空,但是券码不为空 |
| `40004` | 非法的参数 / 请求参数和之前的参数不一致（sub_code: isv.parameter-invalid:010004） | 幂等性校验失败,请求参数和库中已经存在的参数不一致 |
| `50002` | 业务处理失败 / 订单包含的卡券没有完全发放完成,不允许不允许同步订单（sub_code: isv.business-failed:010005） | 订单包含的卡券没有完全发放完成,不允许不允许同步订单 |
| `40004` | 非法的参数 / 卡券为空（sub_code: isv.parameter-invalid:010006） | 卡券为空 |
| `40004` | 非法的参数 / 履约单为空（sub_code: isv.parameter-invalid:020010） | 履约单为空 |
| `50002` | 业务处理失败 / 010013:并发请求,请稍后重试（sub_code: isv.business-failed:010013） | 010013:并发请求,请稍后重试 |
| `50002` | 业务处理失败 / 010023:校验发放卡券数量错误（sub_code: isv.business-failed:010023） | 010023:校验发放卡券数量错误 |
| `50002` | 业务处理失败 / 010020:卡券映射信息重入错误（sub_code: isv.business-failed:010020） | 010020:卡券映射信息重入错误 |
| `50002` | 业务处理失败 / 010012:卡券同步超出24小时（sub_code: isv.business-failed:010012） | 010012:卡券同步超出24小时 |
| `50002` | 业务处理失败 / 000006:类型转换错误（sub_code: isv.business-failed:000006） | 000006:类型转换错误 |
| `50002` | 业务处理失败 / 020007:履约单查询异常（sub_code: isv.business-failed:020007） | 020007:履约单查询异常 |
| `50002` | 业务处理失败 / 030004:系统繁忙,请稍后重试（sub_code: isv.business-failed:030004） | 030004:系统繁忙,请稍后重试 |
| `50002` | 业务处理失败 / 010008:非卡券中心业务（sub_code: isv.business-failed:10008） | 010008:非卡券中心业务 |
| `50002` | 业务处理失败 / 000008:请求已处理（sub_code: isv.business-failed:000008） | 000008:请求已处理 |
| `50002` | 业务处理失败 / 000008:请求已处理（sub_code: isv.business-failed:8） | 000008:请求已处理 |
| `50002` | 业务处理失败 / 009999:系统繁忙,请稍后重试（sub_code: isv.business-failed:9999） | 009999:系统繁忙,请稍后重试 |
| `50002` | 业务处理失败 / 020008:券码重复（sub_code: isv.business-failed:20008） | 020008:券码重复 |
| `50002` | 业务处理失败 / 020011:ByteScheduler处理失败（sub_code: isv.business-failed:20011） | 020011:ByteScheduler处理失败 |
| `50002` | 业务处理失败 / 010081:订单在退款流程中，不允许发码（sub_code: isv.business-failed:10081） | 010081:订单在退款流程中，不允许发码 |
| `50002` | 业务处理失败 / 020005:查询订单失败（sub_code: isv.business-failed:20005） | 020005:查询订单失败 |
| `50002` | 业务处理失败 / 010024:该订单状态下无法同步卡券（sub_code: isv.business-failed:10024） | 010024:该订单状态下无法同步卡券 |
| `50002` | 业务处理失败 / 010010:履约订单不包含资源信息（sub_code: isv.business-failed:10010） | 010010:履约订单不包含资源信息 |
| `50002` | 业务处理失败 / 030002:数据处理失败（sub_code: isv.business-failed:30002） | 030002:数据处理失败 |
| `20000` | 系统错误 / 系统异常,请稍后重试（sub_code: isp.service-error:020011） | 系统异常,请稍后重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:000002",
  "sub_msg": "参数错误"
}
```

## 备注
