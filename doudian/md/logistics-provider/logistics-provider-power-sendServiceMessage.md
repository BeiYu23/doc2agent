# 客服发消息

> power.sendServiceMessage — 客服发消息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 客服发消息 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-power-sendServiceMessage` |
| 接口 ID | `doudian.logistics-provider.power.sendServiceMessage` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/sendServiceMessage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2995 |
| 更新日期 | `2023-02-27` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sessionId` | body | string | 是 | 会话id | `11111112222` |
| `dealerId` | body | string | 否 | 客服id | `123` |
| `messageId` | body | string | 是 | 消息id | `45566` |
| `actionTime` | body | string | 是 | 操作时间 | `1677478601` |
| `messageType` | body | string | 是 | 消息类型，0是文本，1是图片 | `1` |
| `text` | body | string | 否 | 文本内容，当消息类型为0时为必填 | `欢迎进线` |
| `attachUrl` | body | string | 否 | 图片内容的url，当消息类型为1时为必填 | `-` |
| `company` | body | string | 否 | 服务商编码 | `powertestexpress` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/sendServiceMessage?app_key=your_appkey_here&method=power.sendServiceMessage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:10002） | 服务内部异常 |
| `50002` | 业务处理失败 / 会话id不存在（sub_code: isv.business-failed:10003） | 会话id不存在 |
| `50002` | 业务处理失败 / 图片大小超出阀值（sub_code: isv.business-failed:12001） | 图片大小超出阀值 |
| `50002` | 业务处理失败 / 图片格式不兼容（sub_code: isv.business-failed:12002） | - |
| `50002` | 业务处理失败 / 图片无法访问（sub_code: isv.business-failed:12003） | 根据图片url无法正确访问 |

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
