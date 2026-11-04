# yunc.cancelOutboundOrderToB

> toB场景取消出库单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.cancelOutboundOrderToB` |
| 中文名 | toB场景取消出库单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/cancelOutboundOrderToB` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/745 |
| 更新日期 | `2023-01-30` |

## 接口说明

- 文档书: 仓库作业API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `erp_order_no` | body | string | 是 | erp出库单号 | `1` |
| `op_type` | body | number | 是 | 操作类型 枚举值：0【取消】、1【拦截】 | `1` |
| `cancel_tag` | body | number | 是 | 取消标记，枚举值：0【整单取消】 | `1` |
| `cancel_reason` | body | string | 是 | 取消原因 | `no want` |
| `owner_code` | body | string | 否 | 货主编码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/cancelOutboundOrderToB?app_key=your_appkey_here&method=yunc.cancelOutboundOrderToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单状态不允许取消（sub_code: isv.business-failed:62302623） | 订单不允许取消 |
| `50002` | 业务处理失败 / 100102:取消指令实操取消失败（sub_code: isv.business-failed:100102） | 取消指令实操取消失败 |
| `50002` | 业务处理失败 / 4004:warehouse outbound operation error（sub_code: isv.business-failed:4004） | 出库操作失败 |
| `20001` | 内部服务超时 / 1103:服务超时，请重试（sub_code: isp.service-timeout-error:1103） | 请重试 |
| `50002` | 业务处理失败 / 500:500（sub_code: isv.business-failed:500） | 500 |
| `50002` | 业务处理失败 / 9023:取消指令实操取消失败（sub_code: isv.business-failed:9023） | 取消指令实操取消失败 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "logistics_no": "lo111111"
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
  "sub_code": "isv.business-failed:62302623",
  "sub_msg": "订单状态不允许取消"
}
```

## 备注
