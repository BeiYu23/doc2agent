# 退款成功回调

> fuwu.refundSuccessForVolc — 退款成功回调

| 元信息 | 值 |
| --- | --- |
| 中文名 | 退款成功回调 |
| 文档地址 | `/docs/doudian/tool/tool-fuwu-refundSuccessForVolc` |
| 接口 ID | `doudian.tool.fuwu.refundSuccessForVolc` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/refundSuccessForVolc` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/8381 |
| 更新日期 | `2026-08-17` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `account_id` | body | string | 否 | 火山账号 | `1212` |
| `instance_no` | body | string | 否 | 实例编码 | `sefe` |
| `type` | body | mixed | 否 | 退订类型 1:实例退订 2:未生效续费单退订 | `1` |
| `volc_order_ids` | body | array | 否 | 火山订单id列表(type=2 精确退订用) | `["Order123"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/refundSuccessForVolc?app_key=your_appkey_here&method=fuwu.refundSuccessForVolc&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

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
