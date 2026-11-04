# yunc.reflow.inboundCreate

> 翻仓入库单创建接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.reflow.inboundCreate` |
| 中文名 | 翻仓入库单创建 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/reflow/inboundCreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2278 |
| 更新日期 | `2022-10-11` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码（仅允许仓库类型为翻仓） | `W1009` |
| `inbound_order_no` | body | string | 是 | 入库单号 | `IO123456` |
| `biz_order_no` | body | string | 是 | 上游业务单号 | `CG123456` |
| `owner_code` | body | string | 否 | 货主编码 | `BD10000028` |
| `owner_name` | body | string | 否 | 货主名称 | `3PL翻仓测试货主` |
| `order_type` | body | string | 是 | 单据类型（CGRK-采购入库，XTRK-销退入库，DBRK-调拨入库，SCRK-生产入库，QTRK-其他入库） | `CGRK` |
| `status` | body | string | 是 | 单据状态 | `1` |
| `supplier_code` | body | string | 否 | 供应商编码 | `123456` |
| `supplier_name` | body | string | 否 | 供应商名称 | `供应商名称` |
| `shopid` | body | number | 否 | 店铺ID | `1111235707` |
| `shop_name` | body | string | 否 | 店铺名称 | `店铺名称` |
| `remark` | body | string | 否 | 备注 | `备注内容` |
| `sale_outbound_order_no` | body | string | 否 | 销售出库单号 | `OB123456` |
| `sale_way_bill_no` | body | string | 否 | 销售运单号 | `123456` |
| `sale_express` | body | string | 否 | 销售快递商编码 | `zhongtong` |
| `sale_express_name` | body | string | 否 | 销售快递商名称 | `中通速递` |
| `sale_return_way_bill_no` | body | string | 否 | 销退运单号 | `123456` |
| `sale_return_express` | body | string | 否 | 销退快递商编码 | `中通速递` |
| `sale_return_express_name` | body | string | 否 | 销退快递商名称 | `zhongtong` |
| `order_details` | body | array | 是 | 入库单明细 | `` |
| `  └ line_no` | body | string | 是 | 行号（同一入库单下行号唯一） | `1` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7072665065857597721` |
| `  └ cargo_name` | body | string | 是 | 货品名称 | `货品名称` |
| `  └ barcode` | body | string | 否 | 货品条码 | `123456` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品ID | `E123456` |
| `  └ expect_qty` | body | string | 是 | 预计入库数量 | `10` |
| `  └ actual_qty` | body | string | 否 | 实际入库数量 | `10` |
| `order_create_time` | body | number | 否 | wms系统单据创建时间 | `1665460015` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/reflow/inboundCreate?app_key=your_appkey_here&method=yunc.reflow.inboundCreate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 错误码 | `0` |
| `msg` | string | 错误信息 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1001） | 联系系统负责人处理 |
| `50002` | 业务处理失败 / 货主、店铺信息不合法（sub_code: isv.business-failed:13001） | 确定店铺和货主的有效性 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "成功"
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
  "sub_code": "isv.business-failed:1001",
  "sub_msg": "业务处理失败"
}
```

## 备注
