# yunc.reflow.outboundCallback

> 翻仓出库单回告接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.reflow.outboundCallback` |
| 中文名 | 翻仓出库单回告 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/reflow/outboundCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2275 |
| 更新日期 | `2022-11-03` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W1009` |
| `outbound_order_no` | body | string | 是 | 出库单号 | `OB123456` |
| `order_type` | body | string | 是 | 出库单类型（XSCK-销售出库，TCCK-退仓出库，DBCK-调拨出库，QTCK-其他出库，SCCK-生产出库） | `XSCK` |
| `event_type` | body | string | 是 | 事件类型（1-创单成功，2-波次组建完成，3-拣货中，4-拣选完成，5-集货完成，6-分拣完成，7-复核中，8-打包完成，9-称重，21-缺货异常，10-发货完成，20-单据取消） | `3` |
| `extend` | body | string | 否 | 扩展字段 | `` |
| `slip_no` | body | string | 否 | 幂等号（唯一流水号，必填） | `123456` |
| `occur_time` | body | number | 否 | 事件发生时间（必填） | `1658914474` |
| `package_infos` | body | array | 否 | 包裹明细（event_type=10 & order_type=XSCK时必填） | `` |
| `  └ package_no` | body | string | 否 | 包裹号（必填） | `123456` |
| `  └ length` | body | number | 否 | 长（必填，可为0） | `100` |
| `  └ width` | body | number | 否 | 宽（必填，可为0） | `100` |
| `  └ height` | body | number | 否 | 高（必填，可为0） | `100` |
| `  └ length_unit` | body | string | 否 | 长度单位（必填，mm,cm,m） | `cm` |
| `  └ volume` | body | number | 否 | 体积（必填，可为0） | `100` |
| `  └ volume_unit` | body | string | 否 | 体积单位（必填，mm3,cm3,m3） | `cm3` |
| `  └ actual_weight` | body | number | 否 | 称重重量（必填，可为0） | `100` |
| `  └ expect_weight` | body | number | 否 | 理论重量（必填，可为0） | `100` |
| `  └ weight_unit` | body | string | 否 | 重量单位（必填，mg,g,kg） | `g` |
| `  └ packed_time` | body | number | 否 | 打包时间（必填） | `1658914474` |
| `  └ shipped_time` | body | number | 否 | 发货时间（必填） | `1658914474` |
| `  └ create_time` | body | number | 否 | 包裹创建时间（必填） | `1658914474` |
| `  └ logistics` | body | object | 否 | 运输信息 | `` |
| `    └ express` | body | string | 否 | 快递公司/物流公司（必填） | `zhongtong` |
| `    └ track_no` | body | string | 否 | 运单号/面单号（必填） | `123456` |
| `    └ delivery_mode` | body | string | 否 | 运输方式（1-物流，2-快递，3-自提） | `1` |
| `  └ package_items` | body | array | 否 | 货品信息（必填） | `` |
| `    └ line_no` | body | string | 否 | 行号（必填） | `1` |
| `    └ cargo_code` | body | string | 否 | 货品编码（必填） | `7072665065857597721` |
| `    └ cargo_name` | body | string | 否 | 货品名称（必填） | `测试货品` |
| `    └ unit` | body | string | 否 | 包装单位（必填） | `个` |
| `    └ inventory_type` | body | string | 否 | 库存类型（必填，1-正品，2-残品） | `1` |
| `    └ inventory_status` | body | string | 否 | 库存状态（必填，1-正常，2-质检，3-冻结） | `1` |
| `    └ quantity` | body | number | 否 | 数量（必填） | `10` |
| `    └ batch_info` | body | object | 否 | 批属性 | `` |
| `      └ batch_number` | body | string | 否 | 批次号 | `123456` |
| `      └ product_date` | body | number | 否 | 生产日期 | `1658914474` |
| `      └ expire_date` | body | number | 否 | 失效日期 | `1658914474` |
| `      └ receipt_date` | body | number | 否 | 入库日期 | `1658914474` |
| `      └ supplier_id` | body | string | 否 | 供应商ID | `123456` |
| `      └ scm_inbound_order` | body | string | 否 | SCM入库单号 | `SC123456` |
| `  └ pm_infos` | body | array | 否 | 包耗材信息 | `` |
| `    └ code` | body | string | 否 | 包耗材编码 | `123456` |
| `    └ name` | body | string | 否 | 包耗材名称 | `气泡柱` |
| `    └ type` | body | string | 否 | 包耗材类型（0-包材，1-耗材） | `1` |
| `    └ category` | body | string | 否 | 包耗材类别（0-实际，1-推荐） | `1` |
| `    └ num` | body | string | 否 | 数量 | `10` |
| `    └ cargo_code` | body | string | 否 | 对应货品编码 | `7072665065857597721` |
| `    └ bar_code` | body | string | 否 | 包耗材条码 | `123456` |
| `    └ owner_code` | body | string | 否 | 所属货主编码 | `BD10000028` |
| `    └ owner_name` | body | string | 否 | 所属货主名称 | `测试货主` |
| `  └ composition_mode` | body | string | 否 | 包裹组成方式（必填，0-普通件，1-子母件，2-独立件） | `1` |
| `details` | body | array | 否 | 出库单明细（event_type=10时必填） | `` |
| `  └ line_no` | body | string | 否 | 行号（必填） | `1` |
| `  └ cargo_code` | body | string | 否 | 货品编码（必填） | `7072665065857597721` |
| `  └ inventory_type` | body | string | 否 | 库存类型（必填，1-正品，2-残品） | `1` |
| `  └ inventory_status` | body | string | 否 | 库存状态（必填，1-正常，2-质检，3-冻结） | `1` |
| `  └ shipped_qty` | body | number | 否 | 实际出库数量（必填） | `10` |
| `  └ batch_info` | body | object | 否 | 批属性 | `` |
| `    └ batch_number` | body | string | 否 | 批次号 | `123456` |
| `    └ product_date` | body | number | 否 | 生产日期 | `1658914474` |
| `    └ expire_date` | body | number | 否 | 失效日期 | `1658914474` |
| `    └ receipt_date` | body | number | 否 | 入库日期 | `1658914474` |
| `    └ supplier_id` | body | string | 否 | 供应商ID | `123456` |
| `    └ scm_inbound_order` | body | string | 否 | SCM入库单号 | `SC123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/reflow/outboundCallback?app_key=your_appkey_here&method=yunc.reflow.outboundCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `50002` | 业务处理失败 / 1000:内部异常（sub_code: isv.business-failed:1000） | 内部异常，请联系系统人员处理 |
| `50002` | 业务处理失败 / 13002:单据正在处理中（sub_code: isv.business-failed:13002） | 请求正在处理，请稍候重试 |
| `50002` | 业务处理失败 / 1202:数据库记录不存在，请确认后重试（sub_code: isv.business-failed:1202） | 确认单据是否已创建 |
| `50002` | 业务处理失败 / 1001:参数异常（sub_code: isv.business-failed:1001） | 请检查参数是否合法 |
| `50002` | 业务处理失败 / 12000:获取仓库信息失败，请检查编码是否有效（sub_code: isv.business-failed:12000） | 检查仓库信息 |

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
  "sub_code": "isv.business-failed:1000",
  "sub_msg": "1000:内部异常"
}
```

## 备注
