# yunc.reflow.inventoryAdjust

> 库存调整接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.reflow.inventoryAdjust` |
| 中文名 | 库存调整 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/reflow/inventoryAdjust` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2277 |
| 更新日期 | `2022-08-01` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W1009` |
| `adjust_no` | body | string | 是 | 外部调整单号 | `ADJ20220801001` |
| `adjust_type` | body | string | 是 | 调整类型（1=库存盘点，2=库存转移） | `1` |
| `adjust_time` | body | number | 是 | 调整时间（业务发生时间） | `1658914474` |
| `remark` | body | string | 是 | 备注 | `备注内容` |
| `details` | body | array | 否 | 调整明细 | `` |
| `  └ line_no` | body | string | 是 | 行号 | `1` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7072665065857597721` |
| `  └ cargo_name` | body | string | 是 | 货品名称 | `测试货品` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品ID | `E123456` |
| `  └ owner_code` | body | string | 否 | 货主编码 | `BD10000028` |
| `  └ owner_name` | body | string | 否 | 货主名称 | `测试货主` |
| `  └ shopid` | body | number | 否 | 店铺ID | `123456` |
| `  └ shop_name` | body | string | 否 | 店铺名称 | `测试店铺` |
| `  └ adjust_list` | body | array | 是 | 调整列表 | `` |
| `    └ adjust_direction` | body | string | 是 | 调整方向（1-调增，2-调减） | `1` |
| `    └ adjust_qty` | body | number | 是 | 调整数量（正数） | `10` |
| `    └ inventory_type` | body | string | 是 | 库存类型（1-正品，2-残品） | `1` |
| `    └ inventory_status` | body | string | 是 | 库存状态（1-正常，2-质检，3-冻结） | `1` |
| `    └ batch_info` | body | object | 否 | 批次信息 | `` |
| `      └ batch_number` | body | string | 否 | 批次号 | `123456` |
| `      └ product_date` | body | number | 否 | 生产日期 | `1658914474` |
| `      └ expire_date` | body | number | 否 | 失效日期 | `1658914474` |
| `      └ receipt_date` | body | number | 否 | 入库日期 | `1658914474` |
| `      └ supplier_id` | body | string | 否 | 供应商ID | `123456` |
| `      └ scm_inbound_order` | body | string | 否 | SCM入库单号 | `SC123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/reflow/inventoryAdjust?app_key=your_appkey_here&method=yunc.reflow.inventoryAdjust&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `50002` | 业务处理失败 / 1001:库存调整数量必须大于0（sub_code: isv.business-failed:1001） | 1001:库存调整数量必须大于0 |

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
  "sub_code": "isv.business-failed:1001",
  "sub_msg": "1001:库存调整数量必须大于0"
}
```

## 备注
