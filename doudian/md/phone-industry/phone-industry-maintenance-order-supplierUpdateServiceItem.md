# 服务item信息更新

> maintenance.order.supplierUpdateServiceItem — 服务item信息更新，如果之前未回传过此item则视为新增

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务item信息更新 |
| 文档地址 | `/docs/doudian/phone-industry/phone-industry-maintenance-order-supplierUpdateServiceItem` |
| 接口 ID | `doudian.phone-industry.maintenance.order.supplierUpdateServiceItem` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1520/6729 |
| 更新日期 | `2024-08-23` |

## 接口说明

- 文档书: 手机行业管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss"，使用时间递增保证新状态覆盖老状态 | `2024-06-06 12:00:00` |
| `item_service_item_update_info_map` | body | string | 是 | 每个item的使用详情，key为当前的item code | `` |
| `  └ new_item_code` | body | string | 否 | 更新后的item code，无更新时不传 | `SN2` |
| `  └ service_usage_status` | body | mixed | 否 | 更新后的服务状态，无更新时不传 | `1` |
| `  └ activated_period` | body | string | 否 | 更新后的服务生效周期（起止时间），无更新时不传，变更为已激活状态时必传，格式："yyyy-MM-dd HH:mm:ss~yyyy-MM-dd HH:mm:ss" | `2024-06-06 12:00:00~2026-06-06 12:00:00` |
| `order_id` | body | string | 是 | 服务店铺订单号 | `6930810465707234468` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `test` |
| `service_shop_id` | body | mixed | 是 | 服务店铺id | `113243254` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/orderCode/erpShopBindOrderCode?app_key=your_appkey_here&method=orderCode.erpShopBindOrderCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 操作时间乱序错误（sub_code: isv.parameter-invalid:101011） | 操作时间乱序错误 |
| `50002` | 业务处理失败 / 501:未查询到相关单据，请修改服务订单id或者服务店铺id后重试（sub_code: isv.business-failed:501） | 501:未查询到相关单据，请修改服务订单id或者服务店铺id后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "order_list": [
      {
        "agency_id": "101",
        "order_code": "0067108864",
        "order_id": "4817027636051904078",
        "warehouse_code": "02"
      }
    ]
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:101011",
  "sub_msg": "操作时间乱序错误"
}
```

## 备注
