# logistics.overSize.reportException

> 上报大件上门取件履约过程中的异常

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.pickup.logistics.overSize.reportException` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1526/6706 |
| 更新日期 | `2026-01-09` |

## 接口说明

- 文档书: 上门取件API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 订单号（下单给到的orderId） | `LBF00000000009102090287540` |
| `reason` | body | string | 否 | 报备原因；详情请参考https://bytedance.feishu.cn/docx/doxcnFoMDormTOfXuG05n4NFpNf的接口18的「报备原因」 UNABLE_TO_CONTACT_CONSUMER——无法联系上消费者。 AGREEMENT_WITH_CONSUMER——与消费者达成一致后取消。 TIMEOUT_NO_PAID——消费者超时未支付运费。 DISAGREEMENT_WITH_FEE——费用无法达成一致。 NO_MEET_CRITERIA——物品不符合寄递标准。 USER_NO_AUTH——用户不接受实名认证。 TIMEOUT_NO_SEND——上门取件订单超时。 | `UNABLE_TO_CONTACT_CONSUMER` |
| `report_status` | body | string | 否 | 上报状态；CANCELED——取消，INTERCEPTED——拦截 | `CANCELED` |
| `call_info` | body | array | 否 | 每次电联明细；电联信息明细（核销前需要电联明细，核销后不需要） | `` |
| `  └ call_time` | body | string | 否 | 电联时间 | `2021-01-19 10:00:00` |
| `  └ receive_number` | body | string | 否 | 用户号码 | `15161052777` |
| `  └ call_duration` | body | string | 否 | 电联时长（单位秒） | `10` |
| `  └ caller_name` | body | string | 否 | 电联人姓名（快递员） | `张三` |
| `  └ is_connected` | body | boolean | 否 | 是否接通 | `true` |
| `  └ call_number` | body | string | 否 | 电联号码（快递员） | `15161052777` |
| `need_connect` | body | boolean | 否 | 是否需要电联 | `false` |
| `waybill_code` | body | string | 否 | 运单号 | `47320781736` |
| `express` | body | string | 否 | 物流商编码 | `zhongtong` |
| `images` | body | array | 否 | 上传联系照片 | `` |
| `  └ name` | body | string | 否 | 照片name | `xxx` |
| `  └ url` | body | string | 否 | 照片下载url | `xxx.com/xxx/xxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.overSize.reportException&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 请求成功必填，返回定义的字段信息 | `` |
| `result` | boolean | 请求是否成功 | `true` |
| `return_code` | string | 请求成功/失败错误码 | `10000` |
| `message` | string | 请求失败必填，业务逻辑失败原因描述 | `参数错误` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 必传参数没传（sub_code: isv.missing-parameter:10000） | 检查参数正确性 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:10001） | 寻找对接研发同学排查相关问题 |
| `40004` | 非法的参数 / 订单信息不存在（sub_code: isv.parameter-invalid:10002） | 检查参数正确性 |
| `40004` | 非法的参数 / 物流商错误（sub_code: isv.parameter-invalid:10003） | 检查参数正确性 |
| `40004` | 非法的参数 / 运单号错误（sub_code: isv.parameter-invalid:10004） | 检查参数正确性 |
| `50002` | 业务处理失败 / 当前状态不支持上报“无法联系上消费者”（sub_code: isv.business-failed:10005） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 当前状态不支持上报“费用无法达成一致”（sub_code: isv.business-failed:10006） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 当前状态不支持上报“消费者超时未支付运费”（sub_code: isv.business-failed:10007） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 当前状态不支持上报“物品不符合寄递标准”（sub_code: isv.business-failed:10008） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 当前状态不支持上报“不接受实名认证”（sub_code: isv.business-failed:10009） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 不满足电联要求（sub_code: isv.business-failed:10010） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 当前状态不支持二次发起滞留或者取消（sub_code: isv.business-failed:10011） | 检查是否二次发起滞留或取消 |
| `50002` | 业务处理失败 / 当前状态不支持上报“超时未寄件”（sub_code: isv.business-failed:10012） | 检查当前订单状态和电联记录 |
| `50002` | 业务处理失败 / 当前状态不支持取消（sub_code: isv.business-failed:10013） | 检查当前订单状态 |
| `50002` | 业务处理失败 / 用户未还款不允许取消（sub_code: isv.business-failed:10016） | 用户未还款不允许取消 |
| `50002` | 业务处理失败 / 包裹图片不满足要求（sub_code: isv.business-failed:10021） | 包裹图片不满足要求 |
| `50002` | 业务处理失败 / 当前状态不支持上报“物品不可揽-包装问题（无原包装/破损等）”（sub_code: isv.business-failed:10022） | 检查当前订单状态 |
| `50002` | 业务处理失败 / 当前状态不支持上报“物品不可揽-物品需拆卸/复原”（sub_code: isv.business-failed:10023） | 检查当前订单状态 |
| `50002` | 业务处理失败 / 当前状态不支持上报“物品不可揽-影响二次销售”（sub_code: isv.business-failed:10024） | 检查当前订单状态 |
| `50002` | 业务处理失败 / 当前状态不支持上报“物品不可揽-尺寸/重量超规”（sub_code: isv.business-failed:10025） | 检查当前订单状态 |
| `50002` | 业务处理失败 / 当前状态不支持上报“地址不对外开放，无法上门”（sub_code: isv.business-failed:10026） | 检查当前订单状态 |
| `50002` | 业务处理失败 / 当前状态不支持上报“订单不在服务区域内”（sub_code: isv.business-failed:10027） | 检查当前订单状态 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "cur_order_status": "STRANDED",
      "tip_info": {
        "tip_code": "10000",
        "tip_message": "待用户支付"
      }
    },
    "message": "参数错误",
    "result": "true",
    "return_code": "10000"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:10000",
  "sub_msg": "必传参数没传"
}
```

## 备注
