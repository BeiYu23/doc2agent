# topup.refundNoticeCMCC

> 中国移动订单退款通知

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.topup.refundNoticeCMCC` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/refundNoticeCMCC` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7621 |
| 更新日期 | `2026-01-26` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `merchantId` | body | string | 否 | 商户ID | `1` |
| `orderNo` | body | string | 否 | 金科侧订单号 | `1` |
| `type` | body | string | 否 | 接口类型 | `1` |
| `version` | body | string | 否 | 接口版本 | `1` |
| `amount` | body | mixed | 否 | 退款金额（单位：分） | `1` |
| `mobileNo` | body | string | 否 | 手机号码 | `1` |
| `requestId` | body | string | 否 | 抖音电商订单号 | `1` |
| `refundTime` | body | string | 否 | 退款时间，格式：yyyyMMddHHmmss | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/refundNoticeCMCC?app_key=your_appkey_here&method=topup.refundNoticeCMCC&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | string | 响应固定字符串："SUCCESS" | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result": "1"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
