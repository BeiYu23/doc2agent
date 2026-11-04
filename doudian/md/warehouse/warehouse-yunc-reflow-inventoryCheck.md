# yunc.reflow.inventoryCheck

> 库存对账接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.reflow.inventoryCheck` |
| 中文名 | 库存对账 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/reflow/inventoryCheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2274 |
| 更新日期 | `2022-08-01` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W1009` |
| `audit_date` | body | string | 是 | 对账日期（yyyyMMDD） | `20220801` |
| `remark` | body | string | 否 | 备注 | `备注内容` |
| `audit_details` | body | array | 否 | 单据对账明细 | `` |
| `  └ reflow_order_type` | body | string | 是 | 翻仓单据类型（1-入库单，2-出库单，3-库调单） | `1` |
| `  └ shopid` | body | number | 是 | 店铺ID | `123456` |
| `  └ order_qty` | body | number | 是 | 单据数量 | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/reflow/inventoryCheck?app_key=your_appkey_here&method=yunc.reflow.inventoryCheck&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 错误码 | `0` |
| `msg` | string | 错误信息 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
