# 服务商回传保单信息

> maintenance.fulfill.supplierPolicyChange — 服务商回传保单信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商回传保单信息 |
| 文档地址 | `/docs/doudian/industry/industry-maintenance-fulfill-supplierPolicyChange` |
| 接口 ID | `doudian.industry.maintenance.fulfill.supplierPolicyChange` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8581 |
| 更新日期 | `2026-09-04` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `policy_info_list` | body | array | 否 | 保单信息列表 | `` |
| `  └ insured_person` | body | string | 否 | 被保险人名称 | `xxx` |
| `  └ insurance_company` | body | string | 否 | 投保保司名称 | `xxx` |
| `  └ insurance_days` | body | mixed | 否 | 投保年限（天） | `365` |
| `  └ insured_time` | body | string | 否 | 投保时间，格式："yyyy-MM-dd HH:mm:ss" | `2026-01-01 10:00:00` |
| `  └ policy_status` | body | mixed | 否 | 保单状态：1 生效中，2 已退保，3 已终止，4 已理赔； 无状态传 0； | `1` |
| `  └ actual_insured_amount` | body | mixed | 否 | 订单实际投保金额，单位分 | `199900` |
| `  └ insured_amount` | body | mixed | 否 | 保额，单位分 | `199900` |
| `  └ policy_end_time` | body | string | 否 | 保单失效时间，格式："yyyy-MM-dd HH:mm:ss" | `2026-12-31 23:59:59` |
| `  └ order_id` | body | string | 否 | 服务店铺订单号 | `6930810465707234468` |
| `  └ policy_start_time` | body | string | 否 | 保单生效时间，格式："yyyy-MM-dd HH:mm:ss" | `2026-01-02 00:00:00` |
| `  └ policy_holder` | body | string | 否 | 投保人名称 | `xxx` |
| `  └ insurance_product` | body | string | 否 | 投保产品名称 | `两年笔记本全保换新服务` |
| `  └ policy_id` | body | string | 否 | 保单号 | `xxx` |
| `  └ policy_operate_time` | body | string | 否 | 保单操作时间，格式："yyyy-MM-dd HH:mm:ss" | `2026-01-01 10:00:00` |
| `  └ policy_event` | body | mixed | 否 | 保单事件：1 发起投保，2 发起退保； | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=maintenance.fulfill.supplierPolicyChange&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 10000000:请求参数错误（sub_code: isv.parameter-invalid:10000000） | 10000000:请求参数错误 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |

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
  "sub_code": "isv.parameter-invalid:10000000",
  "sub_msg": "10000000:请求参数错误"
}
```

## 备注
