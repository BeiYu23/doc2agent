# crossborder.warehouseInOutboundEvent

> 入库和提货出库回告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossborder.warehouseInOutboundEvent` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossborder/warehouseInOutboundEvent` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/1205 |
| 更新日期 | `2023-05-19` |

## 接口说明

- 文档书: 跨境API（版本 V15.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `in_outbound_event_type` | body | number | 是 | 200:入库单仓库已接单 210:入库单接单异常 300:货物到仓 310:货物到仓异常 400:开始理货 410:理货异常 420:理货完成 500:上架完成 510:上架异常 600:入库单取消 1200:出库单已接单 1210:出库单接单异常 1300:提货完成 1310:提货异常 1400:出库单取消 1250:出库理货开始 1260:出库理货异常 1270:出库理货完成 | `200` |
| `source_order_no` | body | string | 是 | 来源单据号 | `9876` |
| `sp_order_no` | body | string | 否 | 服务商单据编号 | `7052523800093065516` |
| `occurrence_time` | body | number | 是 | 实操时间戳 单位：s | `1656547563` |
| `tally_report_url` | body | array | 否 | 理货报告附件url，当回告节点为理货完成时，必传 | `` |
| `  └ url` | body | string | 是 | 附件url | `https://xxx` |
| `  └ name` | body | string | 是 | 附件名称 | `标题` |
| `inbound_cargo_infos` | body | array | 否 | 入库货品信息，回传“上架完成”时，必传 | `` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7004810808521818412` |
| `  └ actual_stack_count` | body | string | 是 | 实际上架数量 | `10` |
| `  └ good_cargo_count` | body | string | 是 | 良品数量 | `10` |
| `  └ defective_cargo_count` | body | string | 是 | 次品数量 | `0` |
| `  └ expiry_date` | body | string | 是 | 失效日期 yyyy-MM-dd HH:mm:ss | `2021-08-24 20:00:00` |
| `outbound_cargo_infos` | body | array | 否 | 出库货品信息，回传“提货完成”时，必传 | `` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7004810808521818412` |
| `  └ quality_grade` | body | number | 是 | 质量等级 1:良品 2:次品 | `1` |
| `  └ quantity` | body | string | 是 | 货品数量 | `10` |
| `  └ extend` | body | string | 否 | 扩展信息 | `{"key":"value"}` |
| `error_reason` | body | string | 否 | 异常原因 | `异常` |
| `vendor` | body | string | 是 | 服务商编码 | `GZJS` |
| `tally_report` | body | object | 否 | 理货报告 | `` |
| `  └ tally_order_id` | body | string | 是 | 理货单id | `1524215` |
| `  └ customs_order_id` | body | string | 否 | 报关单号 | `415` |
| `  └ tally_total_qty` | body | string | 是 | 理货总件数 | `2` |
| `  └ customs_qty` | body | string | 否 | 报关数量 | `2` |
| `  └ outbound_tally_date` | body | number | 否 | 出库理货日期，秒 | `2` |
| `  └ arrival_date` | body | number | 否 | 到库日期，秒 | `2` |
| `  └ tally_completed_time` | body | number | 是 | 理货完成日期，秒 | `2351` |
| `  └ tally_report_cargo_details` | body | array | 是 | 理货货品明细 | `` |
| `    └ cargo_code` | body | string | 是 | 货品编码 | `2351` |
| `    └ origin_country` | body | string | 是 | 原产国代码（海关原产国代码） | `502` |
| `    └ cargo_name` | body | string | 是 | 货品名称 | `货品1` |
| `    └ length` | body | string | 是 | 长 | `2` |
| `    └ width` | body | string | 是 | 宽 | `2` |
| `    └ height` | body | string | 是 | 高 | `2` |
| `    └ volume` | body | number | 是 | 体积 | `8` |
| `    └ length_unit` | body | string | 否 | 长度单位，默认mm，可填mm，m，MM，M | `mm` |
| `    └ weight` | body | string | 是 | 重量 | `4` |
| `    └ weight_unit` | body | string | 否 | 重量单位，默认g，可填g，kg，G，KG | `g` |
| `    └ barcode` | body | string | 是 | 商品条码 | `435` |
| `    └ good_qty` | body | string | 是 | 理货件数（良品） | `2` |
| `    └ defective_qty` | body | string | 是 | 理货件数（次品） | `2` |
| `    └ customs_qty` | body | string | 否 | 报关数量 | `2` |
| `    └ receive_qty` | body | string | 是 | 实收数量 | `2` |
| `    └ product_batch_no` | body | string | 否 | 生产批次 | `3452` |
| `    └ product_date` | body | number | 是 | 生产日期，秒 | `325` |
| `    └ expiration_date` | body | number | 否 | 失效日期，秒 | `535` |
| `    └ difference` | body | string | 是 | 该货品ID，xx产国，总预约到货数为XX，实际理货件数为XX，差异为XX ，若遇同品多行需在表述中注明商品存在多条理货明细，需商家关注 | `无` |
| `    └ remark` | body | string | 否 | 备注 | `无` |
| `warehouse_code` | body | string | 否 | 仓库编码 | `101` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/warehouseInOutboundEvent?app_key=your_appkey_here&method=crossborder.warehouseInOutboundEvent&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 响应状态码 | `0` |
| `msg` | string | 响应信息 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 理货报告已存在（sub_code: isv.business-failed:16002） | 无需重试 |
| `50002` | 业务处理失败 / 1005:接口调用异常，请重试，多次失败请人工反馈（sub_code: isv.business-failed:1005） | 暂无 |
| `40004` | 非法的参数 / 1002:参数错误（sub_code: isv.parameter-invalid:1002） | 核实参数 |
| `50002` | 业务处理失败 / 7000:查询不到货品信息（sub_code: isv.business-failed:7000） | 理货报告中的货品编码错误 |
| `50002` | 业务处理失败 / 1004:回告事件类型不正确，请核实后重试（sub_code: isv.business-failed:1004） | 正确回传事件顺序 |
| `50002` | 业务处理失败 / 9001:调用货品中心有误（sub_code: isv.business-failed:9001） | 货品编码错误 |
| `40004` | 非法的参数 / 16003:理货报告url为空（sub_code: isv.parameter-invalid:16003） | 填写理货报告url |
| `50002` | 业务处理失败 / 2022:请回传毫秒级别时间戳（sub_code: isv.business-failed:2022） | 请回传毫秒级别时间戳 |
| `50002` | 业务处理失败 / 14003:unsupported status change, current status is :[OutboundOrderStatusAccepted OutboundOrderCompleteOk], next event status is :%!s(MISSING)（sub_code: isv.business-failed:14003） | 状态异常，请检查后重试 |
| `50002` | 业务处理失败 / 1001:服务商鉴权失败（sub_code: isv.business-failed:1001） | 服务商鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "success"
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
  "sub_code": "isv.business-failed:16002",
  "sub_msg": "理货报告已存在"
}
```

## 备注
