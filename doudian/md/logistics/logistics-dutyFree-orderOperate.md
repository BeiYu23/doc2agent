# dutyFree.orderOperate

> 海南项目服务商回传实操节点

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.dutyFree.orderOperate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/dutyFree/orderOperate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1850 |
| 更新日期 | `2022-12-14` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单id | `3214321413241` |
| `occurrence_time` | body | string | 是 | 物流状态的真实发生时间，yyyy-MM-dd hh:mm:ss | `2021-06-18 11:00:00` |
| `status` | body | number | 是 | 节点状态：1 出库异常，2 已出库 ， 3  提货公司揽收异常，4 提货公司已揽收，5 已送达自提点， 6 消费者已提货，7 提货异常，8已核销，9 核销异常 | `1` |
| `verification_info` | body | object | 否 | 核销信息，status传入8时必填 | `-` |
| `  └ leave_type` | body | number | 是 | 离岛工具：1 飞机，2 火车， 3 轮船 | `1` |
| `  └ leave_ticket_no` | body | string | 是 | 离岛工具票号 | `21413241` |
| `  └ leave_time` | body | string | 是 | 用户所填交通工具离岛时间 yyyy-MM-dd hh:mm:ss | `2021-06-18 11:00:00` |
| `transportation` | body | object | 否 | 发货信息，邮寄模式或会员购模式下，status传入2时必填 | `-` |
| `  └ domestic_carrier` | body | string | 是 | 国内快递公司编码 按字节定义的编码推送 | `JD` |
| `  └ domestic_trans_no` | body | string | 是 | 运单号 | `JD321413241` |
| `error_info` | body | object | 否 | 节点异常，status传入1、3、7、9时必填 | `-` |
| `  └ error_code` | body | string | 是 | 返回失败编码，商家只回传不可逆转的失败 | `1001` |
| `  └ error_msg` | body | string | 是 | 返回详细失败原因 | `核销失败` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/dutyFree/orderOperate?app_key=your_appkey_here&method=dutyFree.orderOperate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 接口调用异常，请重试，多次失败请人工反馈（sub_code: isv.business-failed:99999） | 请稍后重试 |
| `50002` | 业务处理失败 / 回告节点时序有误，当前节点为【出库完成】（sub_code: isv.business-failed:10002） | 请检查当前节点 |
| `50002` | 业务处理失败 / 订单不存在，请联系履约确认是否已推单成功（sub_code: isv.business-failed:10001） | 请核实订单信息 |
| `50002` | 业务处理失败 / 交易单已关闭，请核实交易单状态（sub_code: isv.business-failed:10003） | 请核实交易单状态 |

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
  "sub_code": "isv.business-failed:99999",
  "sub_msg": "接口调用异常，请重试，多次失败请人工反馈"
}
```

## 备注
