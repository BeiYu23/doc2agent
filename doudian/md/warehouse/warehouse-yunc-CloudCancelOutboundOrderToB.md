# 云仓出库取消toB

> yunc.CloudCancelOutboundOrderToB — 云仓出库取消toB

| 元信息 | 值 |
| --- | --- |
| 中文名 | 云仓出库取消toB |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-CloudCancelOutboundOrderToB` |
| 接口 ID | `doudian.warehouse.yunc.CloudCancelOutboundOrderToB` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/CloudCancelOutboundOrderToB` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1196 |
| 更新日期 | `2021-09-17` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `erp_order_no` | body | string | 是 | ERP出库单号 | `1` |
| `op_type` | body | string | 是 | 操作类型 | `0` |
| `cancel_tag` | body | string | 是 | 取消标记 | `0` |
| `cancel_reason` | body | string | 是 | 取消原因 | `不想要了` |
| `cancel_details` | body | array | 否 | 取消列表 | `` |
| `  └ line_no` | body | string | 否 | 行号 | `1` |
| `  └ cargo_code` | body | string | 否 | 货品编码 | `1` |
| `  └ erp_sku_id` | body | string | 否 | 货品id | `1` |
| `  └ cancel_amount` | body | string | 否 | 数量 | `1` |
| `owner_code` | body | string | 否 | 货主编码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/CloudCancelOutboundOrderToB?app_key=your_appkey_here&method=yunc.CloudCancelOutboundOrderToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "logistics_no": "LB000001"
    }
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
