# 销退入库取消

> yunc.cloudCancelInboundOrder — 销退入库取消

| 元信息 | 值 |
| --- | --- |
| 中文名 | 销退入库取消 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-cloudCancelInboundOrder` |
| 接口 ID | `doudian.warehouse.yunc.cloudCancelInboundOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/cloudCancelInboundOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1867 |
| 更新日期 | `2022-10-12` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_order_no` | body | string | 是 | 入库单号 | `IB001` |
| `action_type` | body | string | 是 | 固定传1:取消 | `1` |
| `cancel_reason` | body | string | 是 | 取消原因 | `订单取消` |
| `shop_id` | body | number | 否 | 店铺ID | `45364567456` |
| `owner_code` | body | string | 否 | 货主编码 | `11` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/cloudCancelInboundOrder?app_key=your_appkey_here&method=yunc.cloudCancelInboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 62303015:调用仓储失败（sub_code: isv.business-failed:62303015） | 调用仓储失败 |
| `50002` | 业务处理失败 / 623023011:订单状态不允许取消（sub_code: isv.business-failed:623023011） | 订单状态不允许取消 |
| `50002` | 业务处理失败 / 内部错误（sub_code: isv.business-failed:500） | 内部错误 |
| `50002` | 业务处理失败 / 100100:货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！（sub_code: isv.business-failed:100100） | 货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！ |
| `50002` | 业务处理失败 / 1001:调用wms取消单据出错（sub_code: isv.business-failed:1001） | 取消单据出错 |
| `20001` | 内部服务超时 / 超时，请重试（sub_code: isp.service-timeout-error:1103） | 请重试 |

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
  "sub_code": "isv.business-failed:62303015",
  "sub_msg": "62303015:调用仓储失败"
}
```

## 备注
