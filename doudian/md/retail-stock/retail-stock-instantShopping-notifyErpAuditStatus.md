# instantShopping.notifyErpAuditStatus

> Erp商家开仓审核通过

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-stock.instantShopping.notifyErpAuditStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1594/7535 |
| 更新日期 | `2025-06-24` |

## 接口说明

- 文档书: 库存管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `org_shop_id` | body | string | 否 | 抖音货主id | `抖音货主id` |
| `audit_status` | body | mixed | 否 | 审核状态 | `1` |
| `warehouse_id` | body | string | 否 | 提报合作的抖音侧仓ID | `22233331` |
| `warehouse_code` | body | string | 否 | 提报合作的服务商侧仓ID | `HZ-SS101` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.notifyErpAuditStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
