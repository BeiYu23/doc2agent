# 维修服务商审核通过

> maintenance.fulfill.supplierAudit — 维修服务商审核通过

| 元信息 | 值 |
| --- | --- |
| 中文名 | 维修服务商审核通过 |
| 文档地址 | `/docs/doudian/phone-industry/phone-industry-maintenance-fulfill-supplierAudit` |
| 接口 ID | `doudian.phone-industry.maintenance.fulfill.supplierAudit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1520/7892 |
| 更新日期 | `2025-11-27` |

## 接口说明

- 文档书: 手机行业管理（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fulfill_operation_type` | body | string | 是 | 履约操作类型，如：服务商审核通过 | `AuditPass` |
| `supplier_receiver_info` | body | object | 是 | 服务商收货信息 | `` |
| `  └ receiver_tel` | body | string | 是 | 收货人电话 | `13712345678` |
| `  └ receiver_addr` | body | object | 是 | 收货人地址 | `` |
| `    └ district_code` | body | string | 是 | 区编码 | `440111` |
| `    └ province_code` | body | string | 是 | 省编码 | `44` |
| `    └ city_name` | body | string | 是 | 市名称 | `广州市` |
| `    └ district_name` | body | string | 是 | 区名称 | `白云区` |
| `    └ street_name` | body | string | 是 | 街道名称 | `白云湖街道` |
| `    └ province_name` | body | string | 是 | 省名称 | `广东省` |
| `    └ detail_address` | body | string | 是 | 详细地址 | `白云湖小区` |
| `    └ street_code` | body | string | 是 | 街道编码 | `440111018` |
| `    └ city_code` | body | string | 是 | 市编码 | `440100` |
| `  └ receiver_name` | body | string | 是 | 收货人姓名 | `张三` |
| `operation_time` | body | string | 是 | 服务申请审核通过的时间 | `2025-11-27 12:30:00` |
| `service_entity_code` | body | string | 是 | 服务实体编码，与平台对接的服务商枚举值 | `nanjingxingcan` |
| `fulfill_order_id` | body | string | 是 | 一次履约发起行为的唯一标识 | `BSO117077558018` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=maintenance.fulfill.supplierAudit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
