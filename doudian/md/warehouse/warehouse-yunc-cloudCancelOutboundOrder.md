# yunc.cloudCancelOutboundOrder

> 云仓出库取消

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.cloudCancelOutboundOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/cloudCancelOutboundOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/873 |
| 更新日期 | `2023-05-18` |

## 接口说明

- 文档书: 仓库作业API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `erp_order_no` | body | string | 是 | ERP出库单号 | `1231232` |
| `op_type` | body | string | 是 | 操作类型 0:取消 1：拦截 | `0` |
| `cancel_tag` | body | string | 是 | 操作类型 | `0` |
| `cancel_reason` | body | string | 是 | 取消原因 | `不想要` |
| `cancel_details` | body | array | 否 | 取消列表 | `` |
| `  └ line_no` | body | string | 否 | 出库单行号 | `12` |
| `  └ cargo_code` | body | string | 否 | 货品编码 | `1` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品编码 | `1` |
| `  └ cancel_amount` | body | string | 否 | 取消数量 | `1` |
| `platform_order_no` | body | string | 是 | 平台交易单号 | `34672374623674` |
| `owner_code` | body | string | 否 | 货主编码 | `11` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/cloudCancelOutboundOrder?app_key=your_appkey_here&method=yunc.cloudCancelOutboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 调用仓储失败（sub_code: isv.business-failed:62302615） | 重试 |
| `50002` | 业务处理失败 / 500（sub_code: isv.business-failed:500） | 订单已取消，主键冲突导致，会优化 |
| `50002` | 业务处理失败 / 601:601（sub_code: isv.business-failed:601） | 参数错误,请检查 |
| `50002` | 业务处理失败 / 62302623:订单状态不允许取消（sub_code: isv.business-failed:62302623） | 订单状态不允许取消 |
| `50002` | 业务处理失败 / 62303013:取消状态跃迁失败（sub_code: isv.business-failed:62303013） | 取消状态跃迁失败 |
| `50002` | 业务处理失败 / 1001:业务处理失败（sub_code: isv.business-failed:1001） | 业务处理失败 |
| `50002` | 业务处理失败 / 4004:已经出库，仓库无法取消，若需要取消发货，请发起快递拦截！（sub_code: isv.business-failed:4004） | 请发起快递拦截 |
| `50002` | 业务处理失败 / 4001:outbound order not found（sub_code: isv.business-failed:4001） | 出库单未找到 |
| `50002` | 业务处理失败 / 14000:已经出库，仓库无法取消，若需要取消发货，请发起快递拦截！（sub_code: isv.business-failed:14000） | 请发起快递拦截 |
| `20001` | 内部服务超时 / 1103:调用接口超时，请重试！（sub_code: isp.service-timeout-error:1103） | 请重试 |
| `50002` | 业务处理失败 / 4005:unsupported outbound operation error（sub_code: isv.business-failed:4005） | 不支持的出库操作 |
| `50002` | 业务处理失败 / 62302628:取消异常,订单下不存在此erp单号，请确认（sub_code: isv.business-failed:62302628） | 确认erp单号 |
| `50002` | 业务处理失败 / 100100:货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！（sub_code: isv.business-failed:100100） | 货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！ |
| `50002` | 业务处理失败 / 1005:invoke remote failed（sub_code: isv.business-failed:1005） | invoke remote failed |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "logistics_no": "LB00001"
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
  "sub_code": "isv.business-failed:62302615",
  "sub_msg": "调用仓储失败"
}
```

## 备注
