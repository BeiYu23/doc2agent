# 销退单入库

> yunc.cloudCreateInboundOrder — 销退单入库

| 元信息 | 值 |
| --- | --- |
| 中文名 | 销退单入库 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-cloudCreateInboundOrder` |
| 接口 ID | `doudian.warehouse.yunc.cloudCreateInboundOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/cloudCreateInboundOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/872 |
| 更新日期 | `2022-10-12` |

## 接口说明

- 文档书: 仓库作业API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trade_return_no` | body | string | 否 | 交易退货单号 | `S00002` |
| `biz_order_no` | body | string | 是 | 入库单号 必传 | `IB00001` |
| `shop_id` | body | number | 否 | 店铺id 必传 | `12345` |
| `biz_order_id` | body | string | 否 | 原交易单号 必传 | `S001` |
| `s_express_no` | body | string | 否 | 原运单号 | `IB00001` |
| `s_express_name` | body | string | 否 | 原快递公司编码 | `shunfeng` |
| `r_express_no` | body | string | 否 | 退货运单号 必传 | `SF002` |
| `r_express_name` | body | string | 否 | 退货快递公司编码 必传 | `shunfeng` |
| `return_type` | body | string | 否 | 退货类型  1：部分，2：整单 | `1` |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W001` |
| `remark` | body | string | 否 | 备注 | `轻拿轻放` |
| `extend` | body | string | 否 | 扩展字段 | `{key:val}` |
| `order_details` | body | array | 是 | 商品列表 | `` |
| `  └ line_no` | body | string | 是 | 行号 | `1` |
| `  └ biz_order_no` | body | string | 是 | 入库单号 | `IB00001` |
| `  └ cargo_code` | body | string | 否 | 平台货品编码 平台货品编码/商品编码两者必填其一，建议优先填写平台货品编码 | `123` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品编码 平台货品编码/商品编码两者必填其一，建议优先填写平台货品编码 | `123` |
| `  └ expect_qty` | body | string | 是 | 应收数量 | `12` |
| `  └ purchase_price` | body | string | 否 | 采购价 | `100` |
| `  └ currency` | body | string | 否 | 币种 | `CNY` |
| `  └ sn_list` | body | string | 否 | 唯一码 | `SN01,SN02` |
| `  └ inventory_type` | body | string | 是 | 库存类型 1--ZP：正品，2--CP：残品 | `1` |
| `  └ inventory_status` | body | string | 是 | 库存状态 1--ZC：正常，3：冷结，2：质检 | `1` |
| `  └ is_batch_assigned` | body | string | 是 | 是否强制收货批次 0:否 1:是 | `0` |
| `  └ product_date` | body | number | 否 | 生产日期 时间戳 秒 | `16000128398398389` |
| `  └ expire_date` | body | number | 否 | 过期日期 时间戳 秒 | `16000128398398389` |
| `  └ batch_code` | body | string | 否 | 批次号 | `1` |
| `  └ extend` | body | string | 否 | 扩展字段 | `{key:val}` |
| `owner_code` | body | string | 否 | 货主编码 | `11` |
| `shop_name` | body | string | 否 | 店铺名称 | `测试店铺` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/cloudCreateInboundOrder?app_key=your_appkey_here&method=yunc.cloudCreateInboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 62303009:下发仓储单据失败（sub_code: isv.business-failed:62303009） | 联系erp确认配置 |
| `50002` | 业务处理失败 / 100200:r_express_no字段缺失（sub_code: isv.business-failed:100200） | 联系erp确认配置 |
| `50002` | 业务处理失败 / 62303002:接收订单异常，商家未入驻（sub_code: isv.business-failed:62303002） | 联系erp确认配置 |
| `50002` | 业务处理失败 / 62302630:货品不存在（sub_code: isv.business-failed:62302630） | 联系erp确认配置 |
| `50002` | 业务处理失败 / 100100:erpSkuId字段缺失（sub_code: isv.business-failed:100100） | 请检查erp_sku_id字段 |
| `50002` | 业务处理失败 / 1249:该订单已存在，无需重复下发（sub_code: isv.business-failed:1249） | 该订单已存在，无需重复下发 |
| `50002` | 业务处理失败 / 62302617:查询条件不能为空（sub_code: isv.business-failed:62302617） | 查询条件不能为空，请检查参数信息 |
| `50002` | 业务处理失败 / 500:500（sub_code: isv.business-failed:500） | 业务处理失败 |
| `20001` | 内部服务超时 / 服务超时，请重试（sub_code: isp.service-timeout-error:1103） | 请重试 |
| `50002` | 业务处理失败 / 1001:相同LFO已在创建中（sub_code: isv.business-failed:1001） | 业务处理中 |
| `50002` | 业务处理失败 / 1271:手工单号重复，请更换（sub_code: isv.business-failed:1271） | 手工单号重复，请更换 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "logistics_no": "LB0001"
    }
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
  "sub_code": "isv.business-failed:62303009",
  "sub_msg": "62303009:下发仓储单据失败"
}
```

## 备注
