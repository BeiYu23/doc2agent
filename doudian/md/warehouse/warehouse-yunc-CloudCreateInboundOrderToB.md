# yunc.CloudCreateInboundOrderToB

> erp创建入库单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.CloudCreateInboundOrderToB` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/CloudCreateInboundOrderToB` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1197 |
| 更新日期 | `2024-06-05` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `action_type` | body | mixed | 是 | 操作类型 | `IB1001` |
| `biz_order_no` | body | string | 是 | 入库单号 | `CGSH` |
| `shop_id` | body | mixed | 是 | 店铺id | `11234` |
| `order_type` | body | string | 是 | 操作类型 | `1` |
| `related_orders` | body | string | 否 | 关联单据类型 | `{}` |
| `plan_arr_time` | body | string | 否 | 计划到达时间 | `1627622162` |
| `late_arr_time` | body | string | 否 | 最晚到达时间 | `1627622162` |
| `supplier_code` | body | string | 否 | 供应商编码 | `S001` |
| `supplier_name` | body | mixed | 否 | 供应商名称 | `供应商1` |
| `delivery_mode` | body | mixed | 是 | 配送模式 | `3` |
| `delivery_extend` | body | string | 否 | 配送扩展字段 | `1` |
| `remark` | body | string | 否 | 备注 | `轻拿轻放` |
| `extend` | body | string | 否 | 扩展字段 | `{}` |
| `warehouse_code` | body | string | 是 | 仓编码 | `99` |
| `order_details` | body | array | 否 | 明细 | `` |
| `  └ line_no` | body | mixed | 是 | 行号 | `1` |
| `  └ biz_order_no` | body | string | 是 | 单号 | `IB1001` |
| `  └ cargo_code` | body | string | 否 | 货品code | `23432` |
| `  └ erp_sku_id` | body | string | 否 | erp货品数据 | `234324` |
| `  └ expect_qty` | body | mixed | 是 | 预计收货数量 | `3` |
| `  └ purchase_price` | body | mixed | 否 | 采购价格 | `3` |
| `  └ currency` | body | string | 否 | 币种 | `CNY` |
| `  └ sn_list` | body | string | 否 | 唯一码 | `23423` |
| `  └ inventory_type` | body | mixed | 是 | 库存类型 | `1` |
| `  └ inventory_status` | body | mixed | 是 | 库存状态 | `1` |
| `  └ is_batch_assigned` | body | mixed | 是 | 是否指定批次 | `1` |
| `  └ extend` | body | string | 否 | 扩展字段 | `{}` |
| `owner_code` | body | string | 否 | 货主编码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/CloudCreateInboundOrderToB?app_key=your_appkey_here&method=yunc.CloudCreateInboundOrderToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20001` | 内部服务超时 / 1103:服务超时，请重试（sub_code: isp.service-timeout-error:1103） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "code": 20001,
  "msg": "内部服务超时",
  "sub_code": "isp.service-timeout-error:1103",
  "sub_msg": "1103:服务超时，请重试"
}
```

## 备注
