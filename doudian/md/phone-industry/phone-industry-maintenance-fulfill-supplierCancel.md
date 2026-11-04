# maintenance.fulfill.supplierCancel

> 维修服务商取消履约过程

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.phone-industry.maintenance.fulfill.supplierCancel` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1520/7895 |
| 更新日期 | `2025-11-27` |

## 接口说明

- 文档书: 手机行业管理（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_entity_code` | body | string | 否 | 服务实体编码，与平台对接的服务商枚举值，由平台约定后给出 | `nanjingxingcan` |
| `fulfill_order_id` | body | string | 否 | 一次履约发起行为的唯一标识 | `BSO117077558018` |
| `fulfill_operation_type` | body | string | 否 | 履约操作类型：履约申请不通过 / 检测不通过 / 服务商触发履约终止 | `SupplierCancel` |
| `cancel_reason_type` | body | string | 否 | 取消原因枚举值（需按表格中约定值回传） | `201` |
| `cancel_reason_desc` | body | string | 否 | 取消原因描述 | `商品检测无故障` |
| `operation_time` | body | string | 否 | 数据回传时间 | `2025-11-27 12:30:00` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=maintenance.fulfill.supplierCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
