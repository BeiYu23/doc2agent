# yunc.wmsInboundCallback

> wms入库单回告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.wmsInboundCallback` |
| 中文名 | wms入库单回告 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/wmsInboundCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/929 |
| 更新日期 | `2025-12-09` |

## 接口说明

- 文档书: 仓库作业API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inbound_order_no` | body | string | 是 | 字段长度(64)：入库单号 | `IB01` |
| `order_type` | body | string | 是 | 字段长度(8)：单据类型，CGRK=采购入库 DBRK=调拨入库 QTRK=其他入库 SCRK=生产入库 XTRK=销退入库 | `XTRK` |
| `status` | body | mixed | 是 | 状态：22-包裹交接/到货登记 26-拆包质检（ToC） 2-部分收货 3-收货完成 6-上架完成  701-异常提报 30-复原项完结  其中3必填，其他状态可不传； | `2` |
| `operate_time` | body | mixed | 是 | 作业时间 | `1627622162` |
| `operator` | body | string | 是 | 字段长度(32)：操作人 | `C1` |
| `reamrk` | body | string | 否 | 字段长度(200)：备注 | `无` |
| `warehouse_code` | body | string | 是 | 字段长度(16)：仓库编码 | `99` |
| `details` | body | array | 是 | 明细 | `` |
| `  └ sn_list` | body | string | 否 | 字段长度(1024)：唯一码 | `SN01` |
| `  └ batch_code` | body | string | 否 | 字段长度(64)：批次编码 | `B01` |
| `  └ batch_info` | body | object | 否 | 批属性(20220715增加) | `` |
| `    └ scm_inbound_order` | body | string | 否 | 字段长度(64)：SCM入库单号 | `"12846128309281"` |
| `    └ specify_batch_info` | body | object | 否 | 指定批次信息 | `` |
| `      └ expire_date_end` | body | mixed | 否 | 过期日期结束 | `1763551337` |
| `      └ expire_date_start` | body | mixed | 否 | 过期日期开始 | `1763551337` |
| `      └ product_date_end` | body | mixed | 否 | 生产日期结束 | `1763551337` |
| `      └ product_date_start` | body | mixed | 否 | 生产日期开始，秒级时间戳 | `1763551337` |
| `    └ expire_date` | body | mixed | 否 | 失效日期 | `1657805905` |
| `    └ lot_id` | body | string | 否 | 字段长度(64): 批次id | `"122345566"` |
| `    └ receipt_date` | body | mixed | 否 | 入库日期 | `1657805905` |
| `    └ batch_extend` | body | string | 否 | 字段长度(2048): 批次扩展字段，json结构 | `{"batch_number": "1234"}` |
| `    └ batch_number` | body | string | 否 | 字段长度(64)：批次号 | `"122345566"` |
| `    └ product_date` | body | mixed | 否 | 生产日期 | `1657805905` |
| `    └ supplier_id` | body | string | 否 | 字段长度(64)：供应商ID | `"123"` |
| `  └ inventory_type` | body | mixed | 是 | 库存类型 1-正品,2-次品 | `1` |
| `  └ extend` | body | string | 否 | 字段长度(2048)：扩展字段 | `{}` |
| `  └ product_date` | body | mixed | 否 | 生产时间 | `1627622591` |
| `  └ total_qty` | body | mixed | 是 | 累计实收 | `10` |
| `  └ received_qty` | body | mixed | 是 | 本次实收 | `5` |
| `  └ expire_date` | body | mixed | 否 | 过期时间 | `1627622591` |
| `  └ defect_reason` | body | object | 否 | 残次品原因 | `` |
| `    └ desc_msg` | body | string | 是 | 描述信息 | `这是描述` |
| `    └ code` | body | string | 是 | 原因编码 | `CC1234` |
| `  └ owner_code` | body | string | 是 | 字段长度(32)：货主编码 | `O001` |
| `  └ inbound_order_no` | body | string | 是 | 字段长度(64)：单号 | `IB01` |
| `  └ inventory_status` | body | mixed | 是 | 库存状态，1 正常 2 质检 3 冻结 | `1` |
| `  └ remark` | body | string | 否 | 字段长度(1024)：备注 | `无` |
| `  └ line_no` | body | string | 是 | 字段长度(32)：行号  以推单下发的行号为准，用于定位对应的明细行 | `1` |
| `out_biz_code` | body | string | 否 | 字段长度(64)：幂等号（回传部分收货时，必传且需要保证唯一） | `12345` |
| `rejection_details` | body | array | 否 | 拒收明细(20220715增加) | `` |
| `  └ line_no` | body | string | 是 | 字段长度(32)：行号 | `"1"` |
| `  └ rejection_reason` | body | string | 否 | 字段长度(200)：拒收原因 | `"效期原因"` |
| `  └ rejection_qty` | body | mixed | 是 | 拒收数量 | `1` |
| `  └ rejection_remark` | body | string | 否 | 字段长度(200)：拒收说明 | `"生产日期xxx"` |
| `sign_detail` | body | object | 否 | 到货登记信息 | `` |
| `  └ plate_number` | body | string | 是 | 车牌号 | `"XXXX"` |
| `  └ express` | body | string | 是 | 快递公司 | `"XXX公司"` |
| `  └ contact_way` | body | string | 是 | 联系方式 | `"1XXXXXXX"` |
| `  └ way_bill_no` | body | string | 是 | 快递单号 | `"KDxxxx"` |
| `  └ driver` | body | string | 是 | 送货人 | `"XXX"` |
| `event_type_remark` | body | string | 否 | 字段长度(200)：作业节点说明 | `外箱完好` |
| `picture_list` | body | array | 否 | 销退入库时回传图片列表 | `["123","123"]` |
| `abnormal_info_list` | body | array | 否 | 异常信息列表 | `` |
| `  └ abnormal_source` | body | string | 是 | 字段长度(64)：来源，WMS，QMS | `WMS` |
| `  └ cargo_name` | body | string | 否 | 货品名称 | `测试货品名称` |
| `  └ cargo_bar_code` | body | string | 否 | 货品条码 | `6786789678` |
| `  └ abnormal_info_type` | body | string | 是 | 字段长度(64)：异常原因分类 | `实物与资料不符-效期异常` |
| `  └ video_list` | body | array | 否 | 视频列表 | `["http://xxxxx","http://xxxxx"]` |
| `  └ abnormal_info_code` | body | string | 否 | 异常原因编码 | `C0001` |
| `  └ line_no` | body | string | 否 | 行号 | `1` |
| `  └ abnormal_info_remark` | body | string | 是 | 字段长度(200)：异常原因说明 | `XXXX` |
| `  └ qty` | body | mixed | 是 | 数量 | `134` |
| `  └ cargo_type` | body | mixed | 否 | 货品类型 | `1` |
| `  └ cargo_code` | body | string | 是 | 字段长度(64)：货品编码 | `78912893813` |
| `  └ abnormal_picture_list` | body | array | 是 | 图片列表 | `["12313","123"]` |
| `recovery_info_list` | body | array | 否 | 复原信息 | `` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `798788678657657` |
| `  └ line_no` | body | string | 是 | 行号 | `1` |
| `  └ recovery_item_name` | body | string | 是 | 复原项名称 | `熨烫` |
| `  └ recovery_count` | body | mixed | 是 | 复原数量 | `2` |
| `  └ recovery_item_code` | body | string | 是 | 复原项Code | `305` |
| `  └ cargo_name` | body | string | 是 | 货品名称 | `测试货品名称` |
| `  └ package_material` | body | array | 否 | 复原使用的包材信息 | `` |
| `    └ name` | body | string | 是 | 包材名称 | `包装膜` |
| `    └ count` | body | mixed | 是 | 包材数量 | `2` |
| `    └ code` | body | string | 是 | 包材Code | `101` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/wmsInboundCallback?app_key=your_appkey_here&method=yunc.wmsInboundCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 错误码 | `0` |
| `msg` | string | 异常信息 | `"系统内部异常"` |
| `data` | string | data | `data` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 13003:更新库存失败（sub_code: isv.business-failed:13003） | 请重试 |
| `40002` | 缺少必选参数 / outBizCode is required（sub_code: isv.missing-parameter:13000） | 部分收货（分批次回传）的场景，OutBizCode需必传，请填充该字段后重试 |
| `50002` | 业务处理失败 / order not found（sub_code: isv.business-failed:13001） | 请检查入库单号后重试 |
| `50002` | 业务处理失败 / 仓库编码鉴权失败，操作仓和鉴权仓不一致（sub_code: isv.business-failed:1003） | 检查操作仓Code |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1004） | 检查报错 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:1001） | 检查参数重新回传 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": "data",
    "msg": "\"系统内部异常\""
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
  "sub_code": "isv.business-failed:13003",
  "sub_msg": "13003:更新库存失败"
}
```

## 备注
