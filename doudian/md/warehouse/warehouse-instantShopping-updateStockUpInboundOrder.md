# instantShopping.updateStockUpInboundOrder

> 更新备货入库子单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.instantShopping.updateStockUpInboundOrder` |
| 中文名 | 更新备货入库子单信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6754 |
| 更新日期 | `2025-01-13` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `stock_up_sub_order_id` | body | string | 否 | 备货入库子单id | `736478236482341` |
| `stock_up_sub_order_status` | body | mixed | 否 | 入库单当前状态 | `140` |
| `receive_count` | body | mixed | 否 | 实收数量  (当140情况下必填) | `8` |
| `total_count` | body | mixed | 否 | 残次+正品总和 (当200情况下必填) | `10` |
| `shelf_count` | body | mixed | 否 | 上架数量 (当200情况下必填) | `8` |
| `defective_count` | body | mixed | 否 | 残次数量 (当200情况下必填) | `2` |
| `remark` | body | string | 否 | 备注 | `备注信息` |
| `receive_time` | body | mixed | 否 | 入库时间，秒级时间戳(当200情况下必填) | `1722231519` |
| `production_time` | body | mixed | 否 | 生产日期，秒级时间戳(当200情况下必填) | `1722231519` |
| `expire_time` | body | mixed | 否 | 失效日期，秒级时间戳(当200情况下必填) | `1722231519` |
| `operator_id` | body | string | 否 | 操作人id | `1212512512` |
| `operator_name` | body | string | 否 | 操作人姓名 | `xyza` |
| `update_time` | body | mixed | 否 | 状态更新时间 | `1722231519` |
| `charging_unit` | body | object | 否 | 计费单元 | `` |
| `  └ throwing_weight` | body | string | 否 | 该子单实际入库抛重（g）；无则传0 | `123` |
| `  └ charging_weight` | body | string | 否 | 实际参与计费字段（g）； | `123` |
| `  └ total_volume` | body | string | 否 | 该子单实际入库总体积（CM³）；可根据业务精度需求传整数或带小数。 | `123` |
| `  └ total_box` | body | mixed | 否 | 该子单实际入库总箱数，整数 | `1` |
| `  └ total_weight` | body | string | 否 | 该子单实际入库总重量（g）； | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.updateStockUpInboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参错误（sub_code: isv.parameter-invalid:40001） | 研发盘查对应单据等请求是否异常 |
| `50002` | 业务处理失败 / 40010:（sub_code: isv.business-failed:40010） | 40010: |
| `50002` | 业务处理失败 / 40006:no permission（sub_code: isv.business-failed:40006） | 40006:no permission |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "入参错误"
}
```

## 备注
