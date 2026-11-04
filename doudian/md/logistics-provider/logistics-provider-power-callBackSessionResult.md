# power.callBackSessionResult

> 会话创建响应

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.power.callBackSessionResult` |
| 中文名 | 会话创建响应 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/callBackSessionResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2994 |
| 更新日期 | `2023-02-27` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sessionId` | body | string | 是 | 字节会话ID | `111111122334` |
| `bpSessionId` | body | string | 否 | 物流商会话ID | `23444` |
| `actionTime` | body | string | 是 | 操作时间 | `1677478601` |
| `sessionType` | body | string | 是 | 会话状态：1已分配、2排队中、3分配异常 | `1` |
| `dealerId` | body | string | 否 | 物流商客服ID，sessionType为1时为必填 | `1111` |
| `exceptionCode` | body | string | 否 | 异常编码，sessionType为3时为必填 | `eee` |
| `exceptionMsg` | body | string | 否 | 异常描述，sessionType为3时为必填 | `服务异常` |
| `company` | body | string | 否 | 服务商编码 | `powertestexpress` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/callBackSessionResult?app_key=your_appkey_here&method=power.callBackSessionResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:10000） | 必填项校验失败或未按文档要求传参数 |
| `50002` | 业务处理失败 / 签名异常（sub_code: isv.business-failed:10001） | 签名异常 |
| `50002` | 业务处理失败 / 会话id不存在（sub_code: isv.business-failed:10002） | 会话id不存在 |
| `50002` | 业务处理失败 / 物流商会话id不存在（sub_code: isv.business-failed:10003） | 物流商会话id不存在 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:10004） | 服务内部异常 |

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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "参数错误"
}
```

## 备注
