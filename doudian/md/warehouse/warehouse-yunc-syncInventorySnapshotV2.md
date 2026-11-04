# 库存快照回传V2

> yunc.syncInventorySnapshotV2 — 库存快照回传V2

| 元信息 | 值 |
| --- | --- |
| 中文名 | 库存快照回传V2 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-syncInventorySnapshotV2` |
| 接口 ID | `doudian.warehouse.yunc.syncInventorySnapshotV2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/syncInventorySnapshotV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2399 |
| 更新日期 | `2025-12-09` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `idempotent_no` | body | string | 是 | 字段长度(20):幂等键 | `123` |
| `total_lines` | body | mixed | 是 | 字段长度(10):总行数 | `20` |
| `current_page` | body | mixed | 是 | 字段长度(10):当前页，一次性回传的话，传1 | `1` |
| `page_size` | body | mixed | 是 | 字段长度(10):当前页数量，一次性回传的话，值等于总行数 | `20` |
| `occur_time` | body | mixed | 是 | 字段长度(10):发生时间，秒级时间戳；比如1.31凌晨2点回传前一天的快照，时间应该是1.30 23点59分59秒 | `1660752000` |
| `warehouse_code` | body | string | 是 | 字段长度(16):仓code | `W0001` |
| `owner_code` | body | string | 是 | 字段长度(16):仓code | `BD10000029` |
| `api_time` | body | mixed | 是 | 字段长度(10):接口请求时间，秒级时间戳 | `1660752000` |
| `details` | body | array | 是 | 明细 | `` |
| `  └ cargo_code` | body | string | 是 | 字段长度(64):货品code | `AD1234` |
| `  └ cargo_type` | body | mixed | 是 | 字段长度(2):货品类型，默认1 | `1` |
| `  └ inventory_type` | body | mixed | 是 | 字段长度(2):库存类型，1正品；2次品 | `1` |
| `  └ inventory_status` | body | mixed | 是 | 字段长度(2):库存状态，1正常；2质检；3冻结 | `1` |
| `  └ scm_inbound_order` | body | string | 是 | 字段长度(20):scm入库单号 | `123` |
| `  └ supplier_id` | body | string | 是 | 字段长度(20):供应商id | `123` |
| `  └ product_date` | body | mixed | 是 | 字段长度(10):生产日期，秒级时间戳 | `1660752000` |
| `  └ expire_date` | body | mixed | 是 | 字段长度(10):失效日期，秒级时间戳 | `1660752000` |
| `  └ receipt_date` | body | mixed | 是 | 字段长度(10):接收时间，秒级时间戳 | `1660752000` |
| `  └ batch_number` | body | string | 是 | 字段长度(26):批次号 | `123` |
| `  └ opening_inventory` | body | string | 是 | 字段长度(10):期初库存 | `123` |
| `  └ ending_inventory` | body | string | 是 | 字段长度(10):期末库存 | `123` |
| `  └ occupied_inventory` | body | mixed | 否 | 占用库存数量 | `10` |
| `  └ lot_id` | body | string | 否 | 字段长度(128):批次ID 唯一标识一组批次属性 batch_number + product_date + expire_date + receipt_date + supplier_id + scm_inbound_order + batch_extend | `1831341` |
| `  └ batch_extend` | body | string | 否 | 批属性扩展字段，json形式(仅接收规定key) | `{"batch_no": "123"}` |
| `vendor_no` | body | string | 是 | 服务商编码 | `NBFL` |
| `shop_id_out` | body | mixed | 是 | 店铺ID | `13614013` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/syncInventorySnapshotV2?app_key=your_appkey_here&method=yunc.syncInventorySnapshotV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1001） | 根据提示处理 |
| `50002` | 业务处理失败 / 鉴权失败（sub_code: isv.business-failed:1003） | 根据提示处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1004） | 根据提示处理 |

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
  "sub_code": "isv.business-failed:1001",
  "sub_msg": "业务处理失败"
}
```

## 备注
