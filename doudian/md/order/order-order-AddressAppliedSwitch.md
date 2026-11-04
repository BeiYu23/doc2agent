# order.AddressAppliedSwitch

> 支持调用后打开（或关闭）卖家针对买家收货地址变更的审核流程

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.AddressAppliedSwitch` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/AddressAppliedSwitch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/500 |
| 更新日期 | `2024-06-24` |

## 接口说明

- 文档书: 订单API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `is_allowed` | body | mixed | 是 | 0代表关闭，不需要审核 1代表开启审核，买家变更需要审核 | `1` |
| `review_type` | body | mixed | 否 | 0代表异步审核，1表示实时审核 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/AddressAppliedSwitch?app_key=your_appkey_here&method=order.AddressAppliedSwitch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统异常，请重试（sub_code: isv.business-failed:20003） | - |
| `50002` | 业务处理失败 / 开通失败，当前应用未接入spi接口（sub_code: isv.business-failed:30002） | - |
| `50002` | 业务处理失败 / 关闭失败，无权关闭该权限（sub_code: isv.business-failed:50044） | - |
| `50002` | 业务处理失败 / 开启失败，已存在有权限审核改地址的应用（sub_code: isv.business-failed:50045） | - |
| `50002` | 业务处理失败 / 服务器开小差了，请稍后重试（sub_code: isv.business-failed:20001） | 请稍后重试 |

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
  "sub_code": "isv.business-failed:20003",
  "sub_msg": "系统异常，请重试"
}
```

## 备注
