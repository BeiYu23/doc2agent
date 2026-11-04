# yunc.syncInventoryLogFlowV2

> 外部同步库存流水V2

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.syncInventoryLogFlowV2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/syncInventoryLogFlowV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2400 |
| 更新日期 | `2022-11-04` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `idempotent_no` | body | string | 是 | (字段长度: 50)幂等键本次请求的唯一键 最大50个字符 | `BC1234567789` |
| `total_lines` | body | number | 是 | 总行数 | `123` |
| `current_page` | body | number | 是 | 当前页数 | `1` |
| `page_size` | body | number | 是 | 本页回传的实际总行数 | `9` |
| `warehouse_code` | body | string | 是 | (字段长度: 16)仓库编码 | `W0001` |
| `owner_code` | body | string | 是 | (字段长度: 32)货主编码 | `BD0029` |
| `snapshot_time` | body | string | 是 | 操作时间/发生时间 yyyy-MM-dd 对应库存快照业务时间,精确到天 | `2022-07-05` |
| `api_time` | body | number | 是 | 接口发送时间,秒级 | `1658880151` |
| `details` | body | array | 是 | 库存流水明细 | `` |
| `  └ occur_time` | body | number | 是 | 业务发生时间,秒级 | `1658880151` |
| `  └ cargo_code` | body | string | 是 | (字段长度：64)货品编码 | `7090525558416982316` |
| `  └ cargo_type` | body | number | 是 | 1-普通货品 2-包材 3-耗材 | `1` |
| `  └ inventory_type` | body | number | 是 | 库存类型 1-正品 2-残品 | `1` |
| `  └ inventory_status` | body | number | 是 | 库存状态 1-正常 2-质检 3-冻结 | `1` |
| `  └ lot_no` | body | string | 是 | (字段长度:26)批次号 | `Wa123459128` |
| `  └ product_date` | body | number | 是 | 生产日期 | `1658880151` |
| `  └ expire_date` | body | number | 是 | 失效日期 | `1658880151` |
| `  └ receipt_date` | body | number | 是 | 入库日期 | `1658880151` |
| `  └ supplier_id` | body | string | 是 | (字段长度：16)供应商 | `abc1127` |
| `  └ scm_inbound_order` | body | string | 是 | (字段长度：64)入库单号 | `SC0927366872622131` |
| `  └ order_type` | body | string | 是 | (字段长度：32)订单类型 采购入库:PURCHASE_IN; 销退入库:SALE_RETURN_IN; 调拨入库:TRANSFER_IN; 其他入库:OTHER_IN; 销售出库:SALE_OUT; 退仓出库:RTV_OUT; 调拨出库:TRANSFER_OUT; 加工出库:PROCESS_OUT; 加工入库:PROCESS_IN; 转移入库:TRANSFER_PLUS; 转移出库:TRANSFER_REDUCE; 库存调整:INVENTORY_ADJUST | `PURCHASE_IN` |
| `  └ wms_order_no` | body | string | 是 | (字段长度：64)本流水对应的WMS端的入库/出库/库调单号 | `IB01276612321111` |
| `  └ erp_order_no` | body | string | 是 | (字段长度：64)本流水对应的上游的单号,入库单号(erp_order_no)、出库单号(erp_order_no) | `RK01298736632` |
| `  └ change_qty` | body | number | 是 | 变更数量 可负 | `2` |
| `  └ unit` | body | string | 是 | (字段长度：8)单位, 现均默认"件" | `件` |
| `  └ lot_id` | body | string | 否 | 字段长度(128):批次ID 唯一标识一组批次属性 batch_number + product_date + expire_date + receipt_date + supplier_id + scm_inbound_order + batch_extend | `1831341` |
| `  └ batch_extend` | body | string | 否 | 批属性扩展字段，json形式(仅接收规定key) | `{"batch_no": "123"}` |
| `vendor_no` | body | string | 是 | 服务商编码 | `NBFL` |
| `shop_id_out` | body | number | 是 | 店铺ID | `12361751` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/syncInventoryLogFlowV2?app_key=your_appkey_here&method=yunc.syncInventoryLogFlowV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:1000） | 请重试 |
| `40004` | 非法的参数 / 鉴权失败（sub_code: isv.parameter-invalid:1002） | 请核实服务商编码或仓库编码 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1001） | 请核对参数 |
| `50002` | 业务处理失败 / 业务错误（sub_code: isv.business-failed:1400） | 请重试 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:1006） | 请使用秒级时间戳 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1000",
  "sub_msg": "系统错误"
}
```

## 备注
