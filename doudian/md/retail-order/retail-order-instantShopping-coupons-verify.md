# instantShopping.coupons.verify

> 即时零售验券

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-order.instantShopping.coupons.verify` |
| 中文名 | 即时零售验券 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1531/7692 |
| 更新日期 | `2025-08-11` |

## 接口说明

- 文档书: 订单管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `batch_no` | body | string | 否 | 请求唯一编号，防重入，默认当前时间戳 | `xxxx` |
| `frozen_id` | body | string | 否 | 冻结id | `xxxx` |
| `cert_type` | body | mixed | 否 | 卡券类型（0，1 - 三方卡券，平台卡券） | `xxx` |
| `check_verify_order_id` | body | boolean | 否 | 是否校验订单id | `true` |
| `cert_key` | body | string | 否 | 卡密 | `xxxx` |
| `verify_time` | body | mixed | 否 | 核销时间,0则用当前时间 | `xxxx` |
| `verify_count` | body | mixed | 否 | 核销次数，默认1 | `xxxx` |
| `verify_id` | body | string | 否 | 核销userid | `xxxxx` |
| `verify_order_id` | body | string | 否 | 核销订单id | `6943171580507722926` |
| `store_id` | body | mixed | 否 | 门店Id（提货券核销必传） | `155317660` |
| `cert_no` | body | string | 是 | 卡号券码 | `69519975504849` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.coupons.verify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 请传入正确的参数（sub_code: isv.missing-parameter:000002） | 传入正确的StoreId |
| `50002` | 业务处理失败 / 010002:非未使用状态电子凭证禁止核销（sub_code: isv.business-failed:010002） | 010002:非未使用状态电子凭证禁止核销 |
| `50002` | 业务处理失败 / 核销码与订单不匹配，请重新核对订单（sub_code: isv.business-failed:010021） | 核销码与订单不匹配，请重新核对订单 |
| `50002` | 业务处理失败 / 010017:未在有效期内禁止核销（sub_code: isv.business-failed:010017） | 010017:未在有效期内禁止核销 |
| `50002` | 业务处理失败 / 010006:找不到该电子凭证（sub_code: isv.business-failed:010006） | 010006:找不到该电子凭证 |
| `50002` | 业务处理失败 / 009999:系统内部错误（sub_code: isv.business-failed:009999） | 009999:系统内部错误 |
| `50002` | 业务处理失败 / 020005:查询订单失败（sub_code: isv.business-failed:020005） | 020005:查询订单失败 |
| `50002` | 业务处理失败 / 订单与核销码不匹配，请重新核对订单（sub_code: isv.business-failed:020014） | 订单与核销码不匹配，请重新核对订单 |
| `50002` | 业务处理失败 / 020027:门店查询失败（sub_code: isv.business-failed:020027） | 020027:门店查询失败 |

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
  "sub_msg": "请传入正确的参数"
}
```

## 备注
