# 入库明细回传

> wms.inboundDetailNotify — 入库明细回传，WMS回传入库数据时，使用该接口回传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 入库明细回传 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-wms-inboundDetailNotify` |
| 接口 ID | `doudian.warehouse.wms.inboundDetailNotify` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/wms/inboundDetailNotify` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1357 |
| 更新日期 | `2021-09-29` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `business_no` | body | string | 是 | 业务单据号 | `12w` |
| `reciept_no` | body | string | 是 | WMS入库单据号 | `q121` |
| `sku_list` | body | array | 是 | sku列表 | `` |
| `  └ sku_no` | body | string | 是 | sku编号 | `\"12213\"` |
| `  └ sku_name` | body | string | 否 | sku名称 | `大力台灯` |
| `  └ quantity` | body | number | 是 | 数量 | `1` |
| `  └ sn_list` | body | array | 否 | sn列表 | `[\"12w\",\"12\"]` |
| `  └ quality_level` | body | string | 否 | 品质等级：1 良品，2 不良品 | `1` |
| `  └ line_no` | body | string | 否 | 行号 | `1` |
| `  └ batchs` | body | array | 否 | 批次 | `` |
| `    └ batch_no` | body | string | 否 | 批次号 | `1` |
| `    └ production_date` | body | string | 否 | 生产日期 | `1` |
| `    └ expiration_date` | body | string | 否 | 过期日期 | `1` |
| `    └ origin_area` | body | string | 否 | 原产地 | `1` |
| `    └ quantity` | body | string | 否 | 数量 | `1` |
| `business_type` | body | string | 是 | 业务类型，10采购，20销售，30，其他入库，40调拨入库 | `10` |
| `warehouse_no` | body | string | 否 | 入库仓库编码，外部编码 | `qw23w` |
| `sub_type` | body | string | 否 | 子类型，暂不使用，保留字段 | `1` |
| `operate_time` | body | string | 是 | 入库时间 | `2021-09-08 00:00:00` |
| `box_list` | body | array | 否 | box | `` |
| `  └ sku_no` | body | string | 否 | sku编码 | `1` |
| `  └ box_id` | body | string | 否 | 箱单id | `1` |
| `  └ origin_area` | body | string | 否 | 原产地 | `1` |
| `  └ quantity` | body | string | 否 | 数量 | `1` |
| `  └ data_code` | body | string | 否 | 生产日期 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/wms/inboundDetailNotify?app_key=your_appkey_here&method=wms.inboundDetailNotify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
