# 预估公域标签圈选人群包人群数量

> sms.getPreviewUserAmount — 预估公域标签圈选人群包人群数量

| 元信息 | 值 |
| --- | --- |
| 中文名 | 预估公域标签圈选人群包人群数量 |
| 文档地址 | `/docs/doudian/sms/sms-sms-getPreviewUserAmount` |
| 接口 ID | `doudian.sms.sms.getPreviewUserAmount` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getPreviewUserAmount` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7502 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `audience_id` | body | string | 否 | 人群包ID | `123111` |
| `node_list` | body | array | 否 | 规则圈选 | `` |
| `  └ condition` | body | string | 否 | 符号，nodeType =2 时必填：AND交集 OR并集 EXCEPT差集 LEFTPARENS左括号 RIGHTPARENS右括号 | `AND` |
| `  └ produce_id` | body | string | 否 | 生产包id，nodeType=1时必填 | `123` |
| `  └ node_type` | body | number | 否 | 1值 2运算符 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/logisticsEditByPack?app_key=your_appkey_here&method=order.logisticsEditByPack&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `preview_user_amount` | number | 预估人群包数量 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
