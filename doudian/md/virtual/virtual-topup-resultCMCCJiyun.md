# topup.resultCMCCJiyun

> 中国移动话费充值结果回传-50面额

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.virtual.topup.resultCMCCJiyun` |
| 中文名 | 中国移动话费充值结果回传-50面额 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/resultCMCCJiyun` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/7711 |
| 更新日期 | `2025-08-21` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `amount` | body | mixed | 否 | 充值金额（单位：分） | `1` |
| `chargeTime` | body | string | 否 | 充值时间，格式：yyyyMMddHHmmss | `1` |
| `payNo` | body | string | 否 | 金科返回的交易流水号 | `1` |
| `requestId` | body | string | 否 | 抖音电商订单号 | `1` |
| `returnCode` | body | string | 否 | 返回码：00000-成功，其他-失败 | `1` |
| `status` | body | string | 否 | 充值状态：SUCCESS-成功，FAILED-失败 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/resultCMCCJiyun?app_key=your_appkey_here&method=topup.resultCMCCJiyun&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
