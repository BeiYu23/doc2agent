# topup.resultCMCC

> 中国移动话费充值结果回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.topup.resultCMCC` |
| 中文名 | 中国移动话费充值结果回传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/resultCMCC` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7620 |
| 更新日期 | `2025-07-22` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `type` | body | string | 否 | 接口类型，例如：PhoneOfflineNotifySM | `1` |
| `version` | body | string | 否 | 接口版本 | `1` |
| `bankAbbr` | body | string | 否 | 银行简称，例如：CMPAY | `1` |
| `mobileNo` | body | string | 否 | 手机号码 | `1` |
| `requestId` | body | string | 否 | 抖音电商订单号 | `1` |
| `accountDate` | body | string | 否 | 金科系统内订单日期，格式：yyyyMMdd | `1` |
| `merchantId` | body | string | 否 | 商户ID | `1` |
| `message` | body | string | 否 | 返回信息 | `1` |
| `amount` | body | mixed | 否 | 充值金额（单位：分） | `1` |
| `chargeTime` | body | string | 否 | 充值时间，格式：yyyyMMddHHmmss | `1` |
| `status` | body | string | 否 | 充值状态：SUCCESS-成功，FAILED-失败 | `1` |
| `payNo` | body | string | 否 | 金科返回的交易流水号 | `1` |
| `returnCode` | body | string | 否 | 返回码：00000-成功，其他-失败 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/resultCMCC?app_key=your_appkey_here&method=topup.resultCMCC&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
