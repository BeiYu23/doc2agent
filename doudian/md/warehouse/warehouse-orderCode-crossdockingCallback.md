# orderCode.crossdockingCallback

> 仓储中心越库单状态回告接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.orderCode.crossdockingCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/crossdockingCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6758 |
| 更新日期 | `2025-07-22` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cross_docking_order_no` | body | string | 是 | 越库单号，必填 | `"CD739774441779845xxxx"` |
| `outbound_param` | body | object | 否 | 出库参数 eventType= 600（已出库）时，必传 | `` |
| `  └ film_count` | body | mixed | 否 | 为空表示没有贴膜服务 0 表示未贴膜 **如果下发单据时携带了是否贴膜标识，则贴膜数量不能为空** | `0` |
| `  └ express_info` | body | object | 否 | 快递信息 | `` |
| `    └ logistis_source` | body | mixed | 否 | 通过平台取号，回传的快递单号以及快递公司编码，应与从平台取的面单号保持一致。  线下取号，平台不会对快递单号和快递公司编码做平台取号一致性校验。但是需要注意快递商Code只能回传指定类型（目前支持：jd/shunfeng，如需新增可以联系平台配置） | `0-平台取号 1-线下取号` |
| `    └ logistics_no` | body | string | 否 | 物流单号 | `"75530161931237"` |
| `    └ logistics_code` | body | string | 否 | 快递公司编码 | `"zhongtong"` |
| `  └ outbound_details` | body | array | 否 | 出库单明细 | `` |
| `    └ product_id` | body | string | 否 | 商品ID | `"3697741457885666185"` |
| `    └ pm_info` | body | object | 否 | 包材信息，选填 | `` |
| `      └ pm_id` | body | mixed | 否 | 包材id | `305468` |
| `      └ pm_name` | body | string | 否 | 包材名称 | `"机构内包装盒"` |
| `      └ pm_num` | body | mixed | 否 | 包材数量 | `1` |
| `inbound_param` | body | object | 否 | 入库参数 eventType= 801（入库拒收）时，必传 | `` |
| `  └ rejection_reason` | body | object | 否 | 拒收原因 | `` |
| `    └ rejection_reason_code` | body | string | 否 | 拒收原因Code | `枚举值参考： E301：货不对版\商品信息不一致 E302：无货\少件 E303：空包裹` |
| `    └ rejection_reason_desc` | body | string | 否 | 拒收原因描述 | `枚举值参考： E301：货不对版\商品信息不一致 E302：无货\少件 E303：空包裹` |
| `warehouse_code` | body | string | 是 | 仓code，必填 | `"501"` |
| `event_type` | body | mixed | 是 | 越库事件类型，必填 300-入库(收货)完成 801-入库拒收，退回商家 600-发货完成（已出仓） 350-质检通过 750-质检不通过，退回商家 | `300` |
| `order_code` | body | string | 是 | 订单码，必填 | `"0520254260"` |
| `qualify_param` | body | object | 否 | 质检参数 eventType= 750（质检不通过）时，必传 | `` |
| `  └ fail_reason` | body | string | 否 | 质检不通过原因 | `"货不对板"` |
| `event_time` | body | mixed | 是 | 事件发生时间 秒级时间戳 | `1722515548` |
| `remark` | body | string | 否 | 备注 | `"这是备注信息"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/orderCode/crossdockingCallback?app_key=your_appkey_here&method=orderCode.crossdockingCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 失败异常码 | `1004` |
| `msg` | string | 详细失败原因 | `参数非法` |
| `data` | string | 越库单回告事件结果 | `""` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1004） | 参数异常，根据错误信息调整参数后重试 |
| `20000` | 系统错误 / 内部错误-可重试（sub_code: isp.service-error:1001） | 重试 |
| `20001` | 内部服务超时 / 接口超时（sub_code: isp.service-timeout-error:1204） | 重试 |
| `60000` | 触发限流，请稍后重试 / 接口限流（sub_code: isp.traffic-limited:1604） | 重试 |
| `40004` | 非法的参数 / 单据状态校验失败（sub_code: isv.parameter-invalid:4004） | 核实回告的事件类型，并重新回告 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "1004",
    "data": "\"\"",
    "msg": "参数非法"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1004",
  "sub_msg": "参数错误"
}
```

## 备注
