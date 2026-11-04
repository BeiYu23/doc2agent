# pigeon.updatePushUser

> 飞鸽消息推送店铺设置

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.updatePushUser` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/updatePushUser` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/6016 |
| 更新日期 | `2024-01-17` |

## 接口说明

- 文档书: 飞鸽API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `valid` | body | boolean | 是 | 是否开通，true开通，false关闭 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/updatePushUser?app_key=your_appkey_here&method=pigeon.updatePushUser&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否开通成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常，请重试（sub_code: isp.service-error:605090001） | 系统异常，请重试 |
| `50002` | 业务处理失败 / 店铺授权失效（sub_code: isv.business-failed:605010102） | 请重新引导店铺完成授权 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "isp.service-error:605090001",
  "sub_msg": "系统异常，请重试"
}
```

## 备注
