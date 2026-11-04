# 服务商回传仓储

> crossBorder.orderOperate — 服务商回传仓储

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商回传仓储 |
| 文档地址 | `/docs/doudian/logistics/logistics-crossBorder-orderOperate` |
| 接口 ID | `doudian.logistics.crossBorder.orderOperate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/orderOperate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/526 |
| 更新日期 | `2023-05-19` |

## 接口说明

- 文档书: 物流发货API（版本 V12.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 字节电商平台的交易订单号 | `1234` |
| `vendor` | body | string | 是 | 字节给供应链服务商定义的编码 | `QKQTEST` |
| `status` | body | number | 是 | 仓储作业状态：1入库 2打包 3 发货成功 4出库失败 6订单开始拣货 7订单拣货完成 9接单成功 10接单失败 | `1` |
| `occurrence_time` | body | string | 是 | 物流状态的真实发生时间，时间戳，单位秒 | `1656473755` |
| `transportation` | body | object | 否 | 国内物流信息(注意：如果提供了这块信息，domestic_carrier/domestic_trans_no/domestic_ship_address是必传的；对于接单成功事件，集货场景下必传，备货场景下可不传；对于出库完成事件，快递公司编码domestic_carrier和运单号domestic_trans_no必填且必须匹配，4PL=T时快递公司编码必须与下发时一致或者在兜底公司列表，4PL=T&仓配分拆=T时快递公司编码和运单号必须与下发时一致) | `` |
| `  └ domestic_carrier` | body | string | 否 | 国内快递公司编码 按字节定义的编码推送 | `JD` |
| `  └ domestic_trans_no` | body | string | 否 | 国内运单号（BBC/BC/CC/UPU） | `JD12345` |
| `  └ domestic_ship_address` | body | string | 否 | 国内发货地址（国内快递揽收地址） | `北京市海淀区太阳镇街道` |
| `  └ product_num` | body | number | 否 | 商品件数 | `1` |
| `  └ mark` | body | string | 否 | 快递公司大头笔，便于快速识别地址 | `LD` |
| `  └ waybill` | body | string | 否 | PDF格式的电子面单URL | `https://ww.werwer.com/werwer` |
| `  └ delivery_name` | body | string | 否 | 发货人name | `张三` |
| `  └ delivery_tel` | body | string | 否 | 发货人电话 | `1123123123` |
| `package` | body | object | 否 | 包裹信息 | `` |
| `  └ packing_materials` | body | array | 是 | 包材信息，原则上只需回传1个 | `` |
| `    └ packing_material_code` | body | string | 是 | 包材编码 | `SA` |
| `    └ packing_material_name` | body | string | 是 | 包材名称 | `名称` |
| `    └ packing_material_num` | body | number | 是 | 包材数量 | `1` |
| `  └ consumables_materials` | body | array | 否 | 耗材信息 | `` |
| `    └ consumables_code` | body | string | 否 | 耗材编码 | `SA` |
| `    └ consumables_name` | body | string | 否 | 耗材名称 | `名称` |
| `    └ consumables_num` | body | number | 否 | 耗材数量 | `1` |
| `  └ package_weight` | body | number | 是 | 包裹重量,单位g | `12` |
| `  └ package_items` | body | array | 否 | 包裹明细信息 | `` |
| `    └ item_id` | body | string | 否 | 货品编码 | `7074780` |
| `    └ sku_id` | body | number | 否 | 平台sku编号 | `123456` |
| `    └ item_no` | body | string | 否 | 外部服务商货品编码 | `123456` |
| `    └ inventory_type` | body | number | 否 | 库存类型,正品-1，残次-2 | `1` |
| `    └ quantity` | body | number | 否 | 数量 | `1` |
| `    └ batch_info` | body | object | 否 | 批属性 | `` |
| `      └ batch_number` | body | string | 否 | 批次号 | `12345` |
| `      └ product_date` | body | number | 否 | 生产日期 秒级时间戳 | `1640966400` |
| `      └ expire_date` | body | number | 否 | 失效日期 秒级时间戳 | `1640966400` |
| `      └ receipt_date` | body | number | 否 | 入库日期 秒级时间戳 | `1640966400` |
| `      └ supplier_id` | body | string | 否 | 供应商 | `hfkg` |
| `      └ scm_inbound_order` | body | string | 否 | SCM入库单号 | `23456` |
| `      └ lot_id` | body | string | 否 | 批次id | `12345` |
| `      └ batch_extend` | body | string | 否 | 批次扩展字段，json格式 | `{"extend":"info"}` |
| `    └ line_no` | body | string | 否 | 行号 | `123` |
| `error_info` | body | object | 否 | 异常信息（【发货失败】状态时，必须提供） | `` |
| `  └ error_code` | body | string | 否 | 发货失败或者接单失败异常码 | `123` |
| `  └ error_msg` | body | string | 否 | 详细失败原因 | `仓储我败了` |
| `warehouse_code` | body | string | 否 | 仓库编码 | `101` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/orderOperate?app_key=your_appkey_here&method=crossBorder.orderOperate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2018:此订单已开始拦截，请核实订单状态（sub_code: isv.business-failed:2018） | 先回传拦截状态 |
| `50002` | 业务处理失败 / 2019:此订单处于拦截中，请核实订单状态（sub_code: isv.business-failed:2019） | 先回传拦截状态 |
| `50002` | 业务处理失败 / 2020:订单已拦截成功，请核实订单状态（sub_code: isv.business-failed:2020） | 核实订单状态 |
| `50002` | 业务处理失败 / 1004:节点时序状态有误（sub_code: isv.business-failed:1004） | 节点时序状态有误，请核实订单状态 |
| `50002` | 业务处理失败 / 1005:参数不合法（sub_code: isv.business-failed:1005） | 请核实请求参数 |
| `40004` | 非法的参数 / 2013:包耗材信息错误（sub_code: isv.parameter-invalid:2013） | 核实包耗材信息 |
| `40004` | 非法的参数 / 1002:参数不合法（sub_code: isv.parameter-invalid:1002） | 请核实请求参数 |
| `50002` | 业务处理失败 / 2022:biz error code [2022] message 时间格式错误（sub_code: isv.business-failed:2022） | 时间格式错误,请修改时间格式 |
| `50002` | 业务处理失败 / 2021:biz error code [2021] message 接单失败异常编码不符合平台规范，请核实后重试（sub_code: isv.business-failed:2021） | 接单失败异常编码不符合平台规范，请核实后重试 |
| `50002` | 业务处理失败 / 1234:biz error code [1234] message 相同LO已在处理中（sub_code: isv.business-failed:1234） | 重试 |
| `50002` | 业务处理失败 / 1204:系统内部错误（sub_code: isv.business-failed:1204） | 系统内部错误 |
| `50002` | 业务处理失败 / 1003:当前订单为自研单据，不允许回传【订单开始拣货】（sub_code: isv.business-failed:1003） | 自研单据不允许回传 |
| `50002` | 业务处理失败 / 1001:服务商鉴权失败（sub_code: isv.business-failed:1001） | 服务商鉴权失败 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2018",
  "sub_msg": "2018:此订单已开始拦截，请核实订单状态"
}
```

## 备注
