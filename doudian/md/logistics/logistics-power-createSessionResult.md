# power.createSessionResult

> 物流商创建会话响应

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.createSessionResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/createSessionResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1564 |
| 更新日期 | `2023-02-24` |

## 接口说明

- 文档书: 物流发货API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sessionId` | body | string | 是 | - | `0` |
| `bpSessionId` | body | string | 否 | - | `0` |
| `actionTime` | body | string | 是 | - | `0` |
| `sessionType` | body | string | 是 | - | `0` |
| `dealerId` | body | string | 否 | - | `0` |
| `exceptionCode` | body | string | 否 | - | `0` |
| `exceptionMsg` | body | string | 否 | - | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/createSessionResult?app_key=your_appkey_here&method=power.createSessionResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10003:会话不存在（sub_code: isv.business-failed:10003） | 会话不存在 |

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
  "sub_code": "isv.business-failed:10003",
  "sub_msg": "10003:会话不存在"
}
```

## 备注
