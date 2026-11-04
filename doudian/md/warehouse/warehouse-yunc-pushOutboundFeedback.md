# yunc.pushOutboundFeedback

> 给外部WMS调用的推送出库信息回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.pushOutboundFeedback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/pushOutboundFeedback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1868 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 仓库作业API（版本 V7.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_type` | body | mixed | 否 | 单据类型，必传，销售出库= 1 调拨出库= 2 退仓出库= 3,生产出库=5，其他出库=6 | `1` |
| `outbound_order_no` | body | string | 否 | 字段长度(64):出库单号，必传 | `6543` |
| `event_type` | body | mixed | 否 | 事件类型，必传，拣选完成-4、发货完成-10、部分发货-11、重新发货-15、缺货异常-21 | `1` |
| `event_description` | body | string | 否 | 字段长度(200):事件描述 | `出库完成` |
| `warehouse_code` | body | string | 否 | 字段长度(16):仓编码，必传 | `W001` |
| `extend` | body | string | 否 | 字段长度(2048):扩展字段 | `{}` |
| `slip_no` | body | string | 否 | 字段长度(64):单据变化的流水号,必传，需要保证唯一 | `11` |
| `occur_time` | body | mixed | 否 | 事件发生时间（秒级时间戳），必传 | `654345654` |
| `owner_code` | body | string | 否 | 字段长度(32):货主编码，必传 | `11` |
| `package_infos` | body | array | 否 | 包裹信息，订单类型=1时必传 | `` |
| `  └ create_time` | body | mixed | 否 | 包裹创建时间（秒级时间戳） | `5456545` |
| `  └ height` | body | mixed | 否 | 高，单位cm | `44` |
| `  └ logistics` | body | object | 否 | 运输信息 | `` |
| `    └ track_no` | body | string | 否 | 运字段长度(64):单号/面单号，必传 | `65434654` |
| `    └ delivery_mode` | body | mixed | 否 | 运输方式：物流-1；快递-2；自提-3 | `1` |
| `    └ logistics_code` | body | string | 否 | 字段长度(64):快递公司/物流公司，必传 | `jd` |
| `    └ parent_track_no` | body | string | 否 | 母单号（针对子母件场景） | `JDAZ20551556217` |
| `    └ express_product_type_name` | body | string | 否 | 物流产品类型名称 | `JD` |
| `    └ express_product_type` | body | string | 否 | 字段长度(64):物流产品类型编码 | `default` |
| `    └ origin_logistics` | body | array | 否 | 原运单信息，重新发货场景使用 | `` |
| `      └ logistics_code` | body | string | 否 | 原快递商Code，重新发货时必传 | `jd` |
| `      └ track_no` | body | string | 否 | 原运单号，重新发货时必传 | `JDAZ20551556217-1-1-` |
| `  └ width` | body | mixed | 否 | 宽，单位cm | `44` |
| `  └ extra_package` | body | mixed | 否 | 是否为补发包裹，1-是，补发包裹场景使用，用于区分是否为补发包裹 | `1` |
| `  └ shipped_time` | body | mixed | 否 | 发货时间（秒级时间戳） | `5456545` |
| `  └ package_no` | body | string | 否 | 字段长度(64):必传，且不能重复，实操层复核打包完即将发快递时,实操层生成的包裹号 | `6434565` |
| `  └ expect_weight` | body | mixed | 否 | 理论重量，单位g，必传，20220715增加 | `100` |
| `  └ weight_unit` | body | string | 否 | 字段长度(32):重量单位，20220715增加 | `g` |
| `  └ weight` | body | mixed | 否 | 重量，单位g，必传 | `555` |
| `  └ package_type` | body | mixed | 否 | 子母件类型 1-母件包裹 2-子件包裹 | `2` |
| `  └ packed_time` | body | mixed | 否 | 打包时间（秒级时间戳） | `6545654` |
| `  └ volume_unit` | body | string | 否 | 体积单位，默认cm3 | `cm3` |
| `  └ length_unit` | body | string | 否 | 字段长度(32):长宽高单位，20220715增加 | `cm` |
| `  └ composition_mode` | body | mixed | 否 | 0-普通件、1-子母件、2-独立件，20220715增加 | `1` |
| `  └ volume` | body | mixed | 否 | 体积，单位cm3 | `555` |
| `  └ package_items` | body | array | 否 | 货品编码 | `` |
| `    └ line_no` | body | string | 否 | 字段长度(64):出库单行号，建议必传，20220715增加 | `1` |
| `    └ inventory_type` | body | mixed | 否 | 库存类型，必传,正品-1，残次-2 | `1` |
| `    └ inventory_status` | body | mixed | 否 | 库存状态,正常-1，质检-2，冻结-3 | `1` |
| `    └ quantity` | body | mixed | 否 | 数量，必传 | `1` |
| `    └ unit` | body | string | 否 | 字段长度(32):包装单位 | `个` |
| `    └ batch_info` | body | object | 否 | 批次信息，20220715增加 | `` |
| `      └ product_date` | body | mixed | 否 | 生产日期，20220715增加 | `6545654` |
| `      └ scm_inbound_order` | body | string | 否 | 字段长度(64):scm入库单号，20220715增加 | `IB493954395` |
| `      └ supplier_id` | body | string | 否 | 字段长度(64):供应商，20220715增加 | `12334` |
| `      └ receipt_date` | body | mixed | 否 | 入库日期，20220715增加 | `6545654` |
| `      └ batch_number` | body | string | 否 | 字段长度(64):批次号，20220715增加 | `133` |
| `      └ expire_date` | body | mixed | 否 | 失效日期，20220715增加 | `6545654` |
| `      └ specify_batch_info` | body | object | 否 | 指定批次信息 | `` |
| `        └ expire_date_end` | body | mixed | 否 | 过期日期结束 | `1732868611` |
| `        └ expire_date_start` | body | mixed | 否 | 过期日期开始 | `1732868611` |
| `        └ product_date_start` | body | mixed | 否 | 生产日期开始，秒级时间戳 | `1732868611` |
| `        └ product_date_end` | body | mixed | 否 | 生产日期结束 | `1732868611` |
| `      └ batch_extend` | body | string | 否 | 字段长度(2048):批次扩展字段，json格式 | `{"batch_number": "123"}` |
| `      └ lot_id` | body | string | 否 | 字段长度(64):批次id | `133133` |
| `    └ cargo_name` | body | string | 否 | 字段长度(200):货品名称 | `苹果` |
| `    └ cargo_code` | body | string | 否 | 字段长度(64):货品编码，必传 | `545` |
| `    └ sn_infos` | body | array | 否 | SN码列表 | `` |
| `      └ imei_list` | body | array | 否 | imei信息 | `["89686799678","989798780"]` |
| `      └ additional_sn_infos` | body | array | 否 | 附加SN信息；主要针对空调品类场景需要区分内机和外机的SN，空调品类国补场景内机和外机SN都必传。 | `` |
| `        └ sn_type` | body | mixed | 是 | 1-内机SN  2-外机SN | `1` |
| `        └ sn_code` | body | string | 是 | 附加SN码 | `S7986868580867` |
| `      └ bar_code` | body | string | 是 | 货品条码(69码) | `6978968686` |
| `      └ sn_code` | body | string | 是 | SN码 | `S7986868580867` |
| `  └ pm_infos` | body | array | 否 | 包裹绑定的包耗材信息 | `` |
| `    └ cargo_code` | body | string | 否 | 包耗材对应货主编码 | `131237284` |
| `    └ order_code` | body | string | 否 | 订单码，qic行业 | `1732868611` |
| `    └ barcode` | body | string | 否 | 包耗材条码 | `12435` |
| `    └ pm_type` | body | mixed | 否 | 包耗材类型 0-包材 1-耗材 | `1` |
| `    └ num` | body | mixed | 否 | 包耗材数量 | `12` |
| `    └ owner_id` | body | mixed | 否 | 包耗材所属货主ID | `112324244` |
| `    └ owner_name` | body | string | 否 | 包耗材所属货主名称 | `测试货主` |
| `    └ owner_code` | body | string | 否 | 包耗材所属货主编码 | `214355` |
| `    └ pm_code` | body | string | 否 | 包耗材编码 | `pm1324` |
| `    └ price` | body | mixed | 否 | 包耗材单价 | `15` |
| `    └ name` | body | string | 否 | 包耗材名称 | `测试包材` |
| `    └ pm_category` | body | mixed | 否 | 包耗材类别 0-实际 1-推荐 | `1` |
| `    └ source` | body | mixed | 否 | 包耗材来源 1-自建 2-货品中心 | `1` |
| `    └ service_type` | body | mixed | 否 | 服务类型 | `1` |
| `  └ length` | body | mixed | 否 | 长，单位cm | `44` |
| `order_lines` | body | array | 否 | 订单明细，必传 | `` |
| `  └ sn_list` | body | string | 否 | 字段长度(2048):序列号，以英文逗号分隔 | `生产批次号` |
| `  └ multi_package` | body | mixed | 否 | 是否一件多包裹，1-是，0-否，补发包裹场景使用，用于区分补发的哪个货品。 | `1` |
| `  └ shipped_qty` | body | mixed | 否 | 实际发货数量，必传 | `生产批次号` |
| `  └ inventory_type` | body | mixed | 否 | 库存类型，必传，1-正品 2-残次 | `1` |
| `  └ line_no` | body | string | 否 | 字段长度(64):出库单行号，必传 | `544` |
| `  └ batch_info` | body | object | 否 | 批属性信息，20220715增加 | `` |
| `    └ scm_inbound_order` | body | string | 否 | 字段长度(64):SCM入库单号，20220715增加 | `12345` |
| `    └ product_date` | body | mixed | 否 | 生产日期，为了和老逻辑兼容  BatchInfo内外都要传此字段，20220715增加 | `1627622591` |
| `    └ expire_date` | body | mixed | 否 | 过期时间，为了和老逻辑兼容  BatchInfo内外都要传此字段，20220715增加 | `1627622591` |
| `    └ specify_batch_info` | body | object | 否 | 指定批次信息 | `` |
| `      └ product_date_end` | body | mixed | 否 | 生产日期结束 | `1627622591` |
| `      └ expire_date_start` | body | mixed | 否 | 过期日期开始 | `1627622591` |
| `      └ product_date_start` | body | mixed | 否 | 生产日期开始，秒级时间戳 | `1627622591` |
| `      └ expire_date_end` | body | mixed | 否 | 过期日期结束 | `1627622591` |
| `    └ batch_number` | body | string | 否 | 字段长度(64):批次号，20220715增加 | `12345` |
| `    └ supplier_Id` | body | string | 否 | 字段长度(64):供应商，20220715增加 | `12345` |
| `    └ batch_extend` | body | string | 否 | 字段长度(2048):批次扩展字段，json格式 | `{"batch_number": "123"}` |
| `    └ lot_id` | body | string | 否 | 字段长度(64):批次id | `12345` |
| `    └ receipt_date` | body | mixed | 否 | 入库日期，20220715增加 | `1627622591` |
| `  └ package_no` | body | string | 否 | 包裹号，分批发货事件必传 | `PKG1234567890` |
| `  └ inventory_status` | body | mixed | 否 | 库存状态，必传，1-正常 2-质检 3-冻结 | `2` |
| `  └ batch_code` | body | string | 否 | 字段长度(64):生产批次号 | `55` |
| `  └ cargo_name` | body | string | 否 | 字段长度(200):货品名称 | `苹果` |
| `  └ cargo_code` | body | string | 否 | 字段长度(64):货品编码，必传 | `545` |
| `  └ expire_date` | body | mixed | 否 | 过期日期 | `553454` |
| `  └ product_date` | body | mixed | 否 | 生产日期 | `生产批次号` |
| `event_extend_body` | body | array | 否 | 事件扩展结构体，回传缺货异常事件的时候需要填充该字段，20220715增加 | `` |
| `  └ num` | body | mixed | 否 | 数量，20220715增加 | `544` |
| `  └ line_no` | body | string | 否 | 字段长度(64):出库单行号，必传，20220715增加 | `544` |
| `  └ cargo_code` | body | string | 否 | 字段长度(64):货品编码，必传，20220715增加 | `544` |
| `current_package_no` | body | string | 否 | 当前包裹号，分批发货事件必传 | `PKG1234567890` |
| `manual_outbound` | body | mixed | 否 | 手动出库 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/pushOutboundFeedback?app_key=your_appkey_here&method=yunc.pushOutboundFeedback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 4001:outbound order not found（sub_code: isv.business-failed:4001） | 请核实出库单号 |
| `50002` | 业务处理失败 / 8000:inventory service sys error（sub_code: isv.business-failed:8000） | 请重试 |
| `50002` | 业务处理失败 / 4007:出库单已经取消（sub_code: isv.business-failed:4007） | 请重新回传 |
| `40004` | 非法的参数 / ParamIllegal（sub_code: isv.parameter-invalid:1004） | 请检查ExpireDate后重试 |
| `40004` | 非法的参数 / orderType 类型只能是123（sub_code: isv.parameter-invalid:4010） | 请检查orderType后重试 |
| `50002` | 业务处理失败 / 不支持的仓系统类型（sub_code: isv.business-failed:1001） | 请检查仓库信息后重试 |
| `50002` | 业务处理失败 / warehouse not found or disable（sub_code: isv.business-failed:12001） | 请检查仓库信息后重试 |
| `50002` | 业务处理失败 / invoke remote failed（sub_code: isv.business-failed:1005） | 请重试 |
| `50002` | 业务处理失败 / invoke remote failed（sub_code: isv.business-failed:1003） | 请重试 |
| `50002` | 业务处理失败 / 货品数量不一致（sub_code: isv.business-failed:1071） | 请核实orderLines和包裹中货品数量是否一致 |
| `50002` | 业务处理失败 / 1204:RPCError（sub_code: isv.business-failed:1204） | 请重试 |
| `50002` | 业务处理失败 / 单据状态异常（sub_code: isv.business-failed:4004） | 核实单据状态以及回告事件类型是否正常，并重试 |
| `50002` | 业务处理失败 / 风险订单，禁止回传，请联系平台同学（sub_code: isv.business-failed:4022） | 联系平台处理 |

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
  "sub_code": "isv.business-failed:4001",
  "sub_msg": "4001:outbound order not found"
}
```

## 备注
