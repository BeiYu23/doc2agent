# 国补SN校验

> recycle.checkSn — 国补SN校验

| 元信息 | 值 |
| --- | --- |
| 中文名 | 国补SN校验 |
| 文档地址 | `/docs/doudian/industry/industry-recycle-checkSn` |
| 接口 ID | `doudian.industry.recycle.checkSn` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/checkSn` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8576 |
| 更新日期 | `2026-09-02` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 是 | 订单号 | `6951204581989029326` |
| `bar_code` | body | string | 是 | 69码 | `6941764456945` |
| `user_id` | body | mixed | 是 | 用户id | `-` |
| `imei` | body | array | 否 | IMEI | `["123", "456"]` |
| `unique_code_list` | body | array | 是 | SN | `` |
| `  └ unique_code` | body | string | 否 | SN码 | `213123123` |
| `  └ unique_code_type` | body | mixed | 否 | SN类型 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/checkSn?app_key=your_appkey_here&method=recycle.checkSn&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status` | mixed | 当前SN状态  10未占用 20已占用 30已激活（占用订单已收货） | `0` |
| `occupy_available` | boolean | 是否可占用 | `true/false` |
| `occupy_available_msg` | string | 不可占用描述 | `不可占用描述` |
| `imei` | array | IMEI | `IMEI` |
| `unique_code` | string | SN | `SN` |
| `request_id` | string | 订单号 | `订单号` |
| `business_type` | mixed | 业务类型 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / SN 未入库（sub_code: isv.business-failed:400011002） | 联系品牌方/厂商将SN信息录入国家库或省库 |
| `50002` | 业务处理失败 / SN 已被占用 / 不可售（sub_code: isv.business-failed:400011003） | 更换其他未被占用的SN发货 |
| `50002` | 业务处理失败 / SN 被风控（sub_code: isv.business-failed:400011004） | 更换SN发货，或品牌方自行排查 |
| `50002` | 业务处理失败 / 未配置厂商社会信用代码（sub_code: isv.business-failed:400011005） | 国内品牌在商品上补充厂商信用代码；国外品牌联系行业运营配置 |
| `50002` | 业务处理失败 / IMEI 数量不匹配（sub_code: isv.business-failed:400011006） | 调整IMEI录入顺序使其与国家库一致，或确认是否少录 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:100000001） | 检查参数 |
| `20000` | 系统错误 / 鉴权失败（sub_code: isp.service-error:100000010） | 联系开发者 |

## 响应示例

成功：

```json
{
  "data": {
    "business_type": "1",
    "imei": "IMEI",
    "occupy_available": "true/false",
    "occupy_available_msg": "不可占用描述",
    "request_id": "订单号",
    "status": "0",
    "unique_code": "SN"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:400011002",
  "sub_msg": "SN 未入库"
}
```

## 备注
