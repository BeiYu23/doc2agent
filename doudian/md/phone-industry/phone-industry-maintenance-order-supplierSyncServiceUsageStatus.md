# maintenance.order.supplierSyncServiceUsageStatus

> 服务使用状态同步

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.phone-industry.maintenance.order.supplierSyncServiceUsageStatus` |
| 中文名 | 服务使用状态同步 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1520/6646 |
| 更新日期 | `2024-07-04` |

## 接口说明

- 文档书: 手机行业管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 服务店铺订单号 | `"6930810465707234468"` |
| `sku_order_id` | body | string | 是 | 服务商品订单号 | `"6930810465707234468"` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `"test"` |
| `item_usage_info_map` | body | string | 是 | 每个item的使用详情，key为item id，value为服务状态结构体 | `` |
| `  └ service_usage_status` | body | mixed | 否 | 服务状态枚举，1-已激活未使用，2-已使用，已使用过不支持退款，3-已完成，已完成不允许再次发起，4-已注销 | `1` |
| `  └ activated_period` | body | string | 否 | 已激活状态必传，生效周期（起止时间），格式："yyyy-MM-dd HH:mm:ss~yyyy-MM-dd HH:mm:ss" | `"2024-06-06 12:00:00~2026-06-06 12:00:00"` |
| `operation_time` | body | string | 否 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `"2024-06-06 12:00:00"` |
| `version` | body | mixed | 否 | 全量服务资源状态版本，只允许新的版本(大的版本号)覆盖旧的版本 | `34` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=maintenance.order.supplierSyncServiceUsageStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
