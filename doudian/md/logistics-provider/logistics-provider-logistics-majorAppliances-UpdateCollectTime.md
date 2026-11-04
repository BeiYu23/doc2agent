# logistics.majorAppliances.UpdateCollectTime

> 服务商改约

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.majorAppliances.UpdateCollectTime` |
| 中文名 | 服务商改约 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8271 |
| 更新日期 | `2026-05-08` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pickup_order_id` | body | string | 否 | 取件单号 | `LBFxxxx` |
| `reason` | body | string | 否 | 改约原因，枚举值 1. UNABLE_TO_CONTACT_CONSUMER：无法联系上消费者 2: AGREEMENT_WITH_CONSUMER 与消费者达成一致后取消 | `AGREEMENT_WITH_CONSUMER` |
| `new_start_time` | body | string | 否 | 新上门开始时间 | `2026-05-01 10:00:00` |
| `new_end_time` | body | string | 否 | 新上门结束时间 | `2026-05-01 20:00:00` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.majorAppliances.UpdateCollectTime&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参错误（sub_code: isv.parameter-invalid:12004） | 检查入参 |
| `40002` | 缺少必选参数 / 必填参数缺少（sub_code: isv.missing-parameter:12005） | 检查入参 |
| `50002` | 业务处理失败 / 改约次数超过限制（sub_code: isv.business-failed:18001） | 按当天预约时间上门取件 |
| `50002` | 业务处理失败 / 改约时间不合法（sub_code: isv.business-failed:18002） | 检查改约时间是否在T+1～T+7时间段内 |
| `50002` | 业务处理失败 / 改约原因不合法（sub_code: isv.business-failed:18003） | 检查改约原因 |

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
  "sub_code": "isv.parameter-invalid:12004",
  "sub_msg": "入参错误"
}
```

## 备注
