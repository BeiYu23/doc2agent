# order.ReportVirtualMobile

> 主叫号码上报接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.order.ReportVirtualMobile` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/ReportVirtualMobile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8158 |
| 更新日期 | `2026-03-24` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_id` | body | string | 是 | BSO单号、订单号等 | `6922609697599159875` |
| `mobile_caller_list` | body | array | 是 | 主叫号码，可批量，最多20个 | `["1823333333"]` |
| `mobile_virtual` | body | string | 否 | 700虚拟号-15位 | `700001010100000` |
| `report_type` | body | mixed | 否 | 0非行业服务商 （默认） 1行业服务商（可以不传token） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/ReportVirtualMobile?app_key=your_appkey_here&method=order.ReportVirtualMobile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 行业服务商鉴权失败（sub_code: isv.business-failed:300113） | 检查是否为行业服务商/调用方式是否该为非店铺授权 |
| `50002` | 业务处理失败 / 鉴权失败，app不在申报加白名单（sub_code: isv.business-failed:300112） | 联系商家上报加白APP |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:100002） | 检查是否缺失参数 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:200000） | 1.若为行业，检查serviceId是否正确 2.其他场景请重试或提交工单咨询 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "isv.business-failed:300113",
  "sub_msg": "行业服务商鉴权失败"
}
```

## 备注
