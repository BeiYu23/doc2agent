# dutyFree.orderConfirm

> 商家接单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.dutyFree.orderConfirm` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/dutyFree/orderConfirm` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/1873 |
| 更新日期 | `2021-07-22` |

## 接口说明

- 文档书: 跨境API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单ID | `3214321413241` |
| `status` | body | string | 是 | 接单状态：0 接单成功， 1 接单失败 | `1` |
| `occurrence_time` | body | string | 是 | 物流状态的真实发生时间，yyyy-MM-dd hh:mi:ss（北京时间） | `2018-06-03 00:00:00` |
| `error_info` | body | object | 否 | 接单失败，status传入1时必填 | `-` |
| `  └ error_code` | body | string | 是 | 返回失败编码，商家只回传不可逆转的失败。 | `ERR_100` |
| `  └ error_msg` | body | string | 是 | 返回详细失败原因 | `库存不足` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/dutyFree/orderConfirm?app_key=your_appkey_here&method=dutyFree.orderConfirm&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:1005） | 请重试 |
| `50002` | 业务处理失败 / 推送的物流状态不对，请查证后重试, 当前状态是 服务商接单成功（sub_code: isv.business-failed:1004） | 物流状态不对，请查证后重试 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1005",
  "sub_msg": "系统错误"
}
```

## 备注
