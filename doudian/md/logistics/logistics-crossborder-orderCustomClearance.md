# 服务商回告清关状态

> crossborder.orderCustomClearance — 服务商回告清关状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商回告清关状态 |
| 文档地址 | `/docs/doudian/logistics/logistics-crossborder-orderCustomClearance` |
| 接口 ID | `doudian.logistics.crossborder.orderCustomClearance` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossborder/orderCustomClearance` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/527 |
| 更新日期 | `2021-05-18` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vendor` | body | string | 是 | 字节给供应链服务商定义的编码 | `QS` |
| `order_id` | body | string | 是 | 字节电商平台的交易订单号 | `1232` |
| `status` | body | number | 是 | 清关状态：1开始清关 2清关成功 3清关失败（需要平台接入的异常） | `1` |
| `occurrence_time` | body | string | 是 | 物流状态的真实发生时间，yyyy-MM-dd hh:mi:ss | `2020-11-22 11:22:33` |
| `customs_code` | body | string | 是 | 申报口岸【口岸代码】 | `QS` |
| `customs_name` | body | string | 是 | 申报口岸【口岸名称】 | `QS` |
| `error_info` | body | object | 否 | 异常信息（【清关失败/异常】状态时，必须提供） | `-` |
| `  └ error_code` | body | string | 是 | 发货失败异常码 | `210` |
| `  └ error_msg` | body | string | 是 | 详细失败原因 | `失败` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/orderCustomClearance?app_key=your_appkey_here&method=crossborder.orderCustomClearance&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 1000: 非法的参数（sub_code: isv.parameter-invalid:1000） | 检查参数是否正确，若确认参数正确请联系工作人员 |
| `50002` | 业务处理失败 / 1005:接口调用异常，请重试，多次失败请人工反馈（sub_code: isv.business-failed:1005） | 重试，多次失败联系工作人员 |
| `50002` | 业务处理失败 / 1004:回告节点时序有误，当前节点为【交易订单已关闭】（sub_code: isv.business-failed:1004） | 检查当前单据状态，回告正确的状态 |
| `50002` | 业务处理失败 / 1002:参数错误（sub_code: isv.business-failed:1002） | 检查参数是否正确，若确认参数正确请联系工作人员 |
| `50002` | 业务处理失败 / 3002:参数错误：暂时不支持（sub_code: isv.business-failed:3002） | 检查参数是否正确，若确认参数正确请联系工作人员 |

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
  "sub_code": "isv.parameter-invalid:1000",
  "sub_msg": "1000: 非法的参数"
}
```

## 备注
