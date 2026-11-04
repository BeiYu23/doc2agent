# appMessage.send

> 发送服务市场应用消息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.appMessage.send` |
| 中文名 | 发送服务市场应用消息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/appMessage/send` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/3644 |
| 更新日期 | `2023-05-17` |

## 接口说明

- 文档书: 工具API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | number | 是 | 模板id | `1` |
| `msg_param` | body | string | 是 | 模板参数，jump_url是跳转链接，是必传参数。如果跳转web，需包含http或者https协议头 | `{     "warning_title":"物流异常",     "warning_content":"您的728笔订单，物流出现异常情况，请及时查看。",     "jump_url":"https://www.baidu.com/" }` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/appMessage/send?app_key=your_appkey_here&method=appMessage.send&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `rid` | string | 业务key | `ee726838-f44b-34c3-528f-fa5451c46226` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 发送消息失败（sub_code: isp.service-error:301200） | 检查消息模板 |
| `50002` | 业务处理失败 / 消息重复发送（sub_code: isv.business-failed:301201） | 3秒内不要发送重复消息 |
| `50002` | 业务处理失败 / 没有模板权限（sub_code: isv.business-failed:301202） | 申请模板权限 |
| `40004` | 非法的参数 / 消息参数解析失败（sub_code: isv.parameter-invalid:500002） | 检查参数 |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:100002） | 检查参数 |
| `40004` | 非法的参数 / 消息内容解析失败（sub_code: isv.parameter-invalid:301203） | 检查消息模板参数 |
| `50002` | 业务处理失败 / 安全检查错误（sub_code: isv.business-failed:200000） | 重试 |
| `80000` | 风控拦截 / 安全检查不通过（sub_code: isv.risk-control-failed:301204） | 检查消息模板参数 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:100） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "rid": "ee726838-f44b-34c3-528f-fa5451c46226"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:301200",
  "sub_msg": "发送消息失败"
}
```

## 备注
