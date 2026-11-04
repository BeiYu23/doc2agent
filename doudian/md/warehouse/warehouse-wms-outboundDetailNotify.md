# wms.outboundDetailNotify

> WMS出库明细回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.wms.outboundDetailNotify` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/wms/outboundDetailNotify` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/941 |
| 更新日期 | `2021-09-08` |

## 接口说明

- 文档书: 仓库作业API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `business_no` | body | string | 是 | 业务通知单号 | `12wq` |
| `reciept_no` | body | string | 是 | wms出库单号 | `123w` |
| `operate_time` | body | string | 是 | 出库时间 | `2021-09-08:00 19:58` |
| `warehouse_no` | body | string | 是 | 仓库编码 | `wsw` |
| `logistics_list` | body | array | 是 | 物流信息 | `` |
| `  └ weight` | body | string | 否 | 重量 | `1.2` |
| `  └ length` | body | string | 否 | 长 | `1.2` |
| `  └ width` | body | string | 否 | 宽 | `1.2` |
| `  └ height` | body | string | 否 | 高 | `1.2` |
| `  └ logistics_company_no` | body | string | 否 | 物流公司编码 | `asdw` |
| `  └ logistics_service` | body | string | 否 | 物流产品编码 | `122` |
| `  └ waybill_no` | body | string | 否 | 运单号 | `123` |
| `  └ sku_list` | body | array | 是 | sku信息 | `` |
| `    └ sku_no` | body | string | 是 | sku编码 | `wqwq` |
| `    └ sku_name` | body | string | 否 | sku名称 | `大力` |
| `    └ quantity` | body | number | 是 | 数量 | `1` |
| `    └ sn_list` | body | array | 否 | sn列表 | `["wq2"]` |
| `    └ quality_level` | body | string | 否 | 品质等级：1 良品，2 不良品 | `1` |
| `    └ line_no` | body | string | 否 | 行号 | `1` |
| `business_type` | body | string | 否 | 业务类型，10采购退货，20调拨，30 销售订单，40 其他出库 | `10` |
| `sub_type` | body | string | 否 | 子类型，1配货结果通知，2，发货通知，3，仓库签收通知。如果business_type=30,此字段必填。 | `1` |
| `order_line_list` | body | array | 否 | 明细行 | `` |
| `  └ sku_no` | body | string | 是 | sku编码 | `1` |
| `  └ quality_level` | body | string | 否 | 质量等级  1正品2次品 | `1` |
| `  └ line_no` | body | number | 否 | 行号 | `1` |
| `  └ quantity` | body | string | 是 | 数量 | `1` |
| `  └ batchs` | body | array | 否 | 批次 | `` |
| `    └ batch_no` | body | string | 是 | 批次号 | `5` |
| `    └ production_date` | body | string | 是 | 生产日期 | `4` |
| `    └ expiration_date` | body | string | 否 | 过期日期 | `3` |
| `    └ origin_area` | body | string | 否 | 原产地 | `2` |
| `    └ quantity` | body | string | 是 | 数量 | `1` |
| `box_list` | body | array | 否 | 箱单 | `` |
| `  └ sku_no` | body | string | 是 | sku | `5` |
| `  └ box_id` | body | string | 是 | boxid | `4` |
| `  └ origin_area` | body | string | 是 | 生产日期 | `3` |
| `  └ quantity` | body | string | 是 | 数量 | `2` |
| `  └ data_code` | body | string | 是 | 生产日期 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/wms/outboundDetailNotify?app_key=your_appkey_here&method=wms.outboundDetailNotify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 服务不可用 / 查询WMS物流产品信息失败，编号=u003eSE0136：java.net.SocketException: Connection reset（sub_code: isp.service-error:-1） | 按 sub_code 定位问题后处理 |

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
  "msg": "服务不可用",
  "sub_code": "isp.service-error:-1",
  "sub_msg": "查询WMS物流产品信息失败，编号=u003eSE0136：java.net.SocketException: Connection reset"
}
```

## 备注
