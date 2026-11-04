# 核销接口（无需授权

> coupons.verifyV3 — 核销接口（无需授权）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 核销接口（无需授权 |
| 文档地址 | `/docs/doudian/coupon/coupon-coupons-verifyV3` |
| 接口 ID | `doudian.coupon.coupons.verifyV3` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/verifyV3` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/52/7582 |
| 更新日期 | `2025-07-24` |

## 接口说明

- 文档书: 卡券API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `verify_count` | body | mixed | 是 | 核销次数，单次券传1，多次券按需传 | `1` |
| `verify_store_id` | body | string | 是 | 核销门店id | `112233` |
| `verify_shop_id` | body | mixed | 是 | 店铺id | `11223344` |
| `verify_time` | body | mixed | 否 | 核销时间（时间戳） | `1752658197` |
| `cert_no` | body | string | 是 | 卡号券码 | `112233` |
| `supplier_code` | body | string | 是 | 服务商Code | `112233` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/verifyV3?app_key=your_appkey_here&method=coupons.verifyV3&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 卡券查询失败（sub_code: isv.business-failed:20008） | 卡券查询失败 |
| `50002` | 业务处理失败 / 门店状态异常，无法核销，请联系商家（sub_code: isv.business-failed:020025） | 门店状态异常，无法核销，请联系商家 |
| `50002` | 业务处理失败 / 不允许跨城市核销，请联系商家（sub_code: isv.business-failed:020032） | 不允许跨城市核销，请联系商家 |
| `50002` | 业务处理失败 / 卡券不在有效期内（sub_code: isv.business-failed:010017） | 卡券不在有效期内 |
| `50002` | 业务处理失败 / 门店查询失败，请联系商家（sub_code: isv.business-failed:020024） | 门店查询失败，请联系商家 |
| `50002` | 业务处理失败 / 门店查询失败，请联系商家（sub_code: isv.business-failed:020026） | 门店查询失败，请联系商家 |
| `50002` | 业务处理失败 / 门店查询失败，请联系商家（sub_code: isv.business-failed:020031） | 门店查询失败，请联系商家 |
| `50002` | 业务处理失败 / 服务商信息不匹配，请核对信息（sub_code: isv.business-failed:020033） | 服务商信息不匹配，请核对信息 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:000002） | 参数错误 |
| `50002` | 业务处理失败 / 门店查询失败，请联系商家（sub_code: isv.business-failed:020027） | 门店查询失败，请联系商家 |
| `50002` | 业务处理失败 / 门店查询失败，请联系商家（sub_code: isv.business-failed:20027） | 门店查询失败，请联系商家 |
| `50002` | 业务处理失败 / 000009:不支持的操作类型（sub_code: isv.business-failed:9） | 不支持的操作类型 |
| `50002` | 业务处理失败 / 010017:未在有效期内（sub_code: isv.business-failed:10017） | 未在有效期内 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:20008",
  "sub_msg": "卡券查询失败"
}
```

## 备注
