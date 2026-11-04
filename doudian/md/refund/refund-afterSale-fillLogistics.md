# afterSale.fillLogistics

> 售后商家填写物流信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.fillLogistics` |
| 中文名 | 售后商家填写物流信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/fillLogistics` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/1908 |
| 更新日期 | `2024-03-22` |

## 接口说明

- 文档书: 售后退款API（版本 V3.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | string | 是 | 售后单ID | `7085126861562380588` |
| `send_type` | body | mixed | 是 | 发货类型；适用场景： send_type=1：用于补寄商家发货 send_type=3：超市预约上门取货；退货退款和换货场景下商家帮买家填写退货物流信息； send_type=4：维修场景下商家帮买家填写退货物流信息； | `1` |
| `company_code` | body | string | 是 | 物流公司编号 pick_up_type 2:线下取货;3:用户退回，无需物流公司，可传 - | `yuantong` |
| `tracking_no` | body | string | 是 | 物流单号 pick_up_type 2:线下取货;3:用户退回，无需快递单号，可传 - | `YT1231231231` |
| `book_time_begin` | body | mixed | 否 | 预约上门取货时间戳，单位：秒（目前抖超小时达店铺使用） | `1655955000` |
| `book_time_end` | body | mixed | 否 | 预约上门取货时间戳，单位：秒（目前抖超小时达店铺使用） | `1655955600` |
| `store_id` | body | string | 否 | 门店ID | `门店ID` |
| `pick_up_type` | body | mixed | 否 | 1:自行配送;2:线下取货;3:用户退回 ，不传默认自行配送；适用于send_type=3超市预约上门取货场景 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 12000:物流信息校验失败（sub_code: isv.business-failed:12000） | 填入有效物流信息 |
| `50002` | 业务处理失败 / 物流信息校验失败（sub_code: isv.business-failed:602001） | 填入有效物流信息 |
| `20000` | 系统错误 / 网络异常稍后重试（sub_code: isp.service-error:10000） | 重试 |
| `20000` | 系统错误 / 网络异常稍后重试（sub_code: isp.service-error:10002） | 重试 |
| `50002` | 业务处理失败 / 物流信息校验失败（sub_code: isv.business-failed:50002） | 填入有效物流信息 |
| `50002` | 业务处理失败 / 无效售后单（sub_code: isv.business-failed:11000） | 请检查售后单信息 |
| `50002` | 业务处理失败 / 12001:物流信息校验失败（sub_code: isv.business-failed:12001） | 检查物流信息，物流单号、地址等 |
| `50002` | 业务处理失败 / 19009:当前不支持此物流方式（sub_code: isv.business-failed:19009） | 请确认售后原因，用户责任场景才能发起到店退货；线下取货目前处于内测阶段，想要试用请联系抖音运营 |
| `50002` | 业务处理失败 / 19001:请求参数错误（sub_code: isv.business-failed:19001） | 19001:请求参数错误 |
| `50002` | 业务处理失败 / 19002:服务错误（sub_code: isv.business-failed:19002） | 19002:服务错误 |

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
  "sub_code": "isv.business-failed:12000",
  "sub_msg": "12000:物流信息校验失败"
}
```

## 备注
