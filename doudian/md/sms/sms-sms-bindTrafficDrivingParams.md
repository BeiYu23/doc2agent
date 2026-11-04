# sms.bindTrafficDrivingParams

> 绑定引流链接

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.bindTrafficDrivingParams` |
| 中文名 | 绑定引流链接 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/bindTrafficDrivingParams` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/8548 |
| 更新日期 | `2026-09-03` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | string | 否 | 一级模板id | `S1T_xxxx` |
| `second_template_id` | body | string | 否 | 二级模板id | `S2T_yyy` |
| `template_traffic_driving_groups` | body | array | 否 | 引流信息 | `` |
| `  └ params` | body | array | 否 | 引流变量 | `` |
| `    └ param_type` | body | mixed | 否 | 变量类型 1普通变量 2链接 | `2` |
| `    └ name` | body | string | 否 | 变量名 | `url` |
| `    └ content` | body | string | 否 | 变量内容 | `z.douyin.com/iw` |
| `sub_account` | body | string | 否 | 消息组id | `sfije` |
| `signature` | body | string | 否 | 签名 | `北京基石泰来` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/bindTrafficDrivingParams?app_key=your_appkey_here&method=sms.bindTrafficDrivingParams&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | string | 绑定结果 | `failed` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result": "failed"
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
