# 取消入库单

> yunc.erpInboundCancel — 取消入库单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 取消入库单 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-erpInboundCancel` |
| 接口 ID | `doudian.warehouse.yunc.erpInboundCancel` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/erpInboundCancel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1869 |
| 更新日期 | `2023-01-30` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_order_no` | body | string | 是 | 入库单号 | `IB0001` |
| `action_type` | body | string | 是 | 操作类型 | `1` |
| `cancel_reason` | body | string | 是 | 取消原因 | `计划取消` |
| `order_type` | body | string | 是 | 订单类型 | `CGSH` |
| `owner_code` | body | string | 否 | 货主编码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/erpInboundCancel?app_key=your_appkey_here&method=yunc.erpInboundCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 62303015:调用仓储失败（sub_code: isv.business-failed:62303015） | 62303015:调用仓储失败 |
| `50002` | 业务处理失败 / 500:500（sub_code: isv.business-failed:500） | 500:500 |
| `50002` | 业务处理失败 / 100102:取消送仓单失败，仓库可能已作业（sub_code: isv.business-failed:100102） | 100102:取消送仓单失败，仓库可能已作业 |
| `50002` | 业务处理失败 / 1001:调用wms取消入库单失败（sub_code: isv.business-failed:1001） | 1001:调用wms取消入库单失败 |
| `50002` | 业务处理失败 / 100100:ownerCode字段缺失（sub_code: isv.business-failed:100100） | 货主编码ownerCode必填，请补充后重试！ |
| `20001` | 内部服务超时 / 1103:内部服务超时，请重试（sub_code: isp.service-timeout-error:1103） | 请重试 |
| `50002` | 业务处理失败 / 9003:取消送仓单失败，仓库已作业（sub_code: isv.business-failed:9003） | 取消送仓单失败，仓库已作业 |
| `50002` | 业务处理失败 / 9023:500（sub_code: isv.business-failed:9023） | 500 |

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
  "sub_code": "isv.business-failed:62303015",
  "sub_msg": "62303015:调用仓储失败"
}
```

## 备注
