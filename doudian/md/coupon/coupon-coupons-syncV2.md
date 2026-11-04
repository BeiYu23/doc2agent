# 卡券同步

> coupons.syncV2 — 卡券同步

| 元信息 | 值 |
| --- | --- |
| 中文名 | 卡券同步 |
| 文档地址 | `/docs/doudian/coupon/coupon-coupons-syncV2` |
| 接口 ID | `doudian.coupon.coupons.syncV2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/syncV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/52/712 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 卡券API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 子订单id | `123421345` |
| `sku_id` | body | mixed | 否 | skuid | `1` |
| `cert_list` | body | array | 是 | 卡券信息列表 | `` |
| `  └ valid_start` | body | string | 否 | 有效开始时间，大闸蟹场景必传 | `2010-01-01 12:12:12` |
| `  └ out_cert_id` | body | string | 否 | 外部卡券id | `666` |
| `  └ status` | body | mixed | 否 | 状态：1未激活 2未使用 | `1` |
| `  └ valid_end` | body | string | 否 | 有效结束时间，大闸蟹场景必传 | `2010-01-01 12:12:12` |
| `  └ url_type` | body | mixed | 否 | 卡券跳转链接类型，2为小程序 | `0/2` |
| `  └ cert_link` | body | string | 否 | 卡券跳转链接，长度限制255 | `https://obd.gtimg.com/new-benefit-web-schema/dev/dist/index.html?ShortLinkId=6438f6f4a87f2&e=test&dyp=1&c=cafsdadsfas` |
| `  └ grant_time` | body | string | 是 | 发券时间 | `2010-01-01 12:12:12` |
| `  └ cert_key` | body | string | 否 | 卡密（三方卡券订单无需回传），长度限制64 | `1` |
| `  └ cert_no` | body | string | 是 | 卡券券码，长度限制64，请勿传中文字符 | `7136xxxasd` |
| `  └ can_extend_valid_count` | body | mixed | 否 | 可延期次数 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/syncV2?app_key=your_appkey_here&method=coupons.syncV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `40004` | 非法的参数 / 履约单为空（sub_code: isv.parameter-invalid:020010） | 履约单为空，请检查 |
| `50002` | 业务处理失败 / 010013:并发请求,请稍后重试（sub_code: isv.business-failed:010013） | 010013:并发请求,请稍后重试 |
| `50002` | 业务处理失败 / 010023:校验发放卡券数量错误（sub_code: isv.business-failed:010023） | 010023:校验发放卡券数量错误 |
| `50002` | 业务处理失败 / 010020:卡券映射信息重入错误（sub_code: isv.business-failed:010020） | 010020:卡券映射信息重入错误 |
| `50002` | 业务处理失败 / 010012:卡券同步超出24小时（sub_code: isv.business-failed:010012） | 010012:卡券同步超出24小时 |
| `50002` | 业务处理失败 / 000006:类型转换错误（sub_code: isv.business-failed:000006） | 000006:类型转换错误 |
| `50002` | 业务处理失败 / 020007:履约单查询异常（sub_code: isv.business-failed:020007） | 020007:履约单查询异常 |
| `50002` | 业务处理失败 / 030004:系统繁忙,请稍后重试（sub_code: isv.business-failed:030004） | 030004:系统繁忙,请稍后重试 |
| `50002` | 业务处理失败 / 010008:非卡券中心业务（sub_code: isv.business-failed:10008） | 请检查订单业务类型 |
| `50002` | 业务处理失败 / 000008:请求已处理（sub_code: isv.business-failed:000008） | 请求已处理 |
| `50002` | 业务处理失败 / 000008:请求已处理（sub_code: isv.business-failed:8） | 请求已处理 |
| `50002` | 业务处理失败 / 009999:系统繁忙,请稍后重试（sub_code: isv.business-failed:9999） | 009999:系统繁忙,请稍后重试 |
| `50002` | 业务处理失败 / 020008:券码重复（sub_code: isv.business-failed:20008） | 020008:券码重复 |
| `50002` | 业务处理失败 / 020011:ByteScheduler处理失败（sub_code: isv.business-failed:20011） | 系统繁忙,请稍后重试 |
| `50002` | 业务处理失败 / 010081:订单在退款流程中，不允许发码（sub_code: isv.business-failed:10081） | 订单在退款流程中，不允许发码 |
| `50002` | 业务处理失败 / 020005:查询订单失败（sub_code: isv.business-failed:20005） | 系统繁忙,请稍后重试 |
| `50002` | 业务处理失败 / 010024:该订单状态下无法同步卡券（sub_code: isv.business-failed:10024） | 该订单状态下无法同步卡券，请检查订单状态 |
| `50002` | 业务处理失败 / 010010:履约订单不包含资源信息（sub_code: isv.business-failed:10010） | 010010:履约订单不包含资源信息 |
| `50002` | 业务处理失败 / 030002:数据处理失败（sub_code: isv.business-failed:30002） | 030002:数据处理失败 |
| `50002` | 业务处理失败 / 040021:券码或卡密字段不允许包含中文字符（sub_code: isv.business-failed:40021） | 券码或卡密字段不允许包含中文字符 |
| `50002` | 业务处理失败 / 010029:并发请求,请稍后重试（sub_code: isv.business-failed:10029） | 并发请求,请稍后重试 |
| `50002` | 业务处理失败 / 000009:不支持的操作类型（sub_code: isv.business-failed:9） | 不支持的操作类型 |
| `40004` | 非法的参数 / 040022:三方卡券订单只需回传卡券券码字段，不支持回传卡密字段（sub_code: isv.parameter-invalid:040022） | 三方卡券订单只需回传卡券券码字段，不支持回传卡密字段 |

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
