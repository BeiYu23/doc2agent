# yunc.reflow.inboundCallback

> 翻仓入库单回告接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.reflow.inboundCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/reflow/inboundCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2279 |
| 更新日期 | `2022-08-01` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W1009` |
| `inbound_order_no` | body | string | 是 | 入库单号 | `IB123456` |
| `order_type` | body | string | 是 | 单据类型（CGRK-采购入库，XTRK-销退入库，DBRK-调拨入库，SCRK-生产入库，QTRK-其他入库） | `CGRK` |
| `event_type` | body | string | 是 | 事件类型（1-已创建，2-分批收货，3-收货完成，4-已取消，6-上架完成，22-已登记） | `3` |
| `extend` | body | string | 否 | 扩展字段 | `` |
| `slip_no` | body | string | 是 | 幂等号（唯一流水号） | `123456` |
| `occur_time` | body | number | 否 | 事件发生时间 | `1658198430` |
| `details` | body | array | 是 | 入库单明细 | `` |
| `  └ line_no` | body | string | 是 | 行号 | `1` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7072665065857597721` |
| `  └ total_qty` | body | number | 是 | 累计实收 | `10` |
| `  └ received_qty` | body | number | 是 | 本次实收 | `10` |
| `  └ inventory_type` | body | string | 是 | 库存类型（1-正品，2-残品） | `1` |
| `  └ inventory_status` | body | string | 是 | 库存状态（1-正常，2-质检，3-冻结） | `1` |
| `  └ batch_info` | body | object | 否 | 批次信息 | `` |
| `    └ batch_number` | body | string | 否 | 批次号 | `123456` |
| `    └ product_date` | body | number | 否 | 生产日期 | `1658198430` |
| `    └ expire_date` | body | number | 否 | 失效日期 | `1658198430` |
| `    └ receipt_date` | body | number | 否 | 入库日期 | `1658198430` |
| `    └ supplier_id` | body | string | 否 | 供应商ID | `123456` |
| `    └ scm_inbound_order` | body | string | 否 | SCM入库单号 | `SC123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/reflow/inboundCallback?app_key=your_appkey_here&method=yunc.reflow.inboundCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `50002` | 业务处理失败 / 1207:入库单号不存在（sub_code: isv.business-failed:1207） | 1207:入库单号不存在 |
| `50002` | 业务处理失败 / 1001:入库单[IB7437109344049987840]下明细不存在, 货品编码为[RL-KQ500D03], 行号为[521839041]（sub_code: isv.business-failed:1001） | 1001:入库单[IB7437109344049987840]下明细不存在, 货品编码为[RL-KQ500D03], 行号为[521839041] |
| `50002` | 业务处理失败 / 12000:获取仓库信息失败，请检查编码是否有效（sub_code: isv.business-failed:12000） | 12000:获取仓库信息失败，请检查编码是否有效 |

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
  "sub_code": "isv.business-failed:1207",
  "sub_msg": "1207:入库单号不存在"
}
```

## 备注
