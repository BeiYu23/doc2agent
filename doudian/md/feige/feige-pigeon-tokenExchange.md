# pigeon.tokenExchange

> 飞鸽token换取登录参数

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.tokenExchange` |
| 中文名 | 飞鸽token换取登录参数 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/tokenExchange` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/1971 |
| 更新日期 | `2022-06-01` |

## 接口说明

- 文档书: 飞鸽API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `token` | body | string | 是 | 密文token | `YOUR_SECRET_KEY` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/tokenExchange?app_key=your_appkey_here&method=pigeon.tokenExchange&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `login_param` | string | 登录态明文信息 | `{\"customer_service_id\":\"1%#YOUR_SECRET_KEY\",\"customer_service_name\":\"张三\",\"shop_id\":\"1111122233\"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 登录时间已过期（sub_code: isv.business-failed:33001） | 使用新的 token， 目前是 10 分钟过期 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:100002） | 稍等重试或提交工单 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:7） | 稍等重试或提交工单 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:100003） | 使用正确的鉴权信息 |

## 响应示例

成功：

```json
{
  "data": {
    "login_param": "{\\\"customer_service_id\\\":\\\"1%#YOUR_SECRET_KEY\\\",\\\"customer_service_name\\\":\\\"侯志鹏\\\",\\\"shop_id\\\":\\\"1111114035\\\"}"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:33001",
  "sub_msg": "登录时间已过期"
}
```

## 备注
