# yunc.erpInboundCreate

> erp创建入库单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.erpInboundCreate` |
| 中文名 | erp创建入库单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/erpInboundCreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/899 |
| 更新日期 | `2023-01-17` |

## 接口说明

- 文档书: 仓库作业API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_order_no` | body | string | 是 | 入库单号 | `IB0001` |
| `shop_id` | body | number | 是 | 店铺id（不强校验，填0即可） | `1234` |
| `order_type` | body | string | 是 | "CGRK" 采购入库  "DBRK" 调拨入库 "QTRK"其它入库  "SCRK"生产入库 "2BXTRK" 2B销退入库 | `CGRK` |
| `action_type` | body | string | 是 | 操作类型 1：新增 | `1` |
| `related_orders` | body | string | 否 | 关联单据信息 | `{}` |
| `plan_arr_time` | body | number | 否 | 计划到达时间 | `1627622162` |
| `late_arr_time` | body | number | 否 | 最晚到达时间 | `1627622162` |
| `supplier_code` | body | string | 否 | 供应商编码 | `S001` |
| `supplier_name` | body | string | 否 | 供应商名称 | `供应商1` |
| `delivery_mode` | body | string | 是 | 配送模式（1：物流 2：快递 3：自送） | `3` |
| `delivery_extend` | body | string | 否 | 配送扩展字段 | `{}` |
| `warehouse_code` | body | string | 是 | 仓code | `W001` |
| `remark` | body | string | 否 | 备注 | `无` |
| `extend` | body | string | 否 | 扩展字段 | `{}` |
| `order_details` | body | array | 是 | 明细 | `` |
| `  └ line_no` | body | string | 是 | 行号 | `1` |
| `  └ biz_order_no` | body | string | 是 | 单号 | `IB001` |
| `  └ cargo_code` | body | string | 否 | 平台货品编码 平台货品编码/商品编码两者必填其一，建议优先填写平台货品编码 | `21342` |
| `  └ erp_sku_id` | body | string | 否 | 商品编码 平台货品编码/商品编码两者必填其一，建议优先填写平台货品编码 | `31425` |
| `  └ expect_qty` | body | string | 是 | 预计收货数量 | `2` |
| `  └ inventory_type` | body | string | 是 | 库存类型 1：正品 2：次品 | `1` |
| `  └ inventory_status` | body | string | 是 | 库存状态 1：正常 2：质检 3：冻结 | `1` |
| `  └ is_batch_assigned` | body | string | 是 | 是否指定批次 | `0` |
| `  └ sn_list` | body | string | 否 | 唯一码 | `SN001` |
| `  └ product_date` | body | number | 否 | 生产日期 | `1627622162` |
| `  └ expire_date` | body | number | 否 | 过期时间 | `1627622162` |
| `  └ batch_code` | body | string | 否 | 批次编码 | `B001` |
| `  └ purchase_price` | body | number | 否 | 采购价格 | `100` |
| `  └ currency` | body | string | 否 | 币种 | `CNY` |
| `  └ extend` | body | string | 否 | 扩展字段 | `{}` |
| `owner_code` | body | string | 否 | 货主编码 | `111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/erpInboundCreate?app_key=your_appkey_here&method=yunc.erpInboundCreate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 下发仓储单据失败（sub_code: isp.service-error:62303009） | 请稍后重试 |
| `50002` | 业务处理失败 / 部分货品不存在["BNS012-黑色踩脚"]（sub_code: isv.business-failed:62302630） | 货品信息校验不通过，按提示修改 |
| `50002` | 业务处理失败 / 62302617:查询条件不能为空（sub_code: isv.business-failed:62302617） | 查询条件不能为空 |
| `50002` | 业务处理失败 / 1249:该订单已存在，无需重复下发（sub_code: isv.business-failed:1249） | 该订单已存在，无需重复下发 |
| `50002` | 业务处理失败 / 100100:expectedQty字段缺失（sub_code: isv.business-failed:100100） | 请检查expect_qty字段 |
| `50002` | 业务处理失败 / 100102:库存异常（sub_code: isv.business-failed:100102） | 库存异常，请检查库存之后操作 |
| `50002` | 业务处理失败 / 9021:缺少必要参数：送仓明细（sub_code: isv.business-failed:9021） | 缺少必要参数：送仓明细 |

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
  "sub_code": "isp.service-error:62303009",
  "sub_msg": "下发仓储单据失败"
}
```

## 备注
