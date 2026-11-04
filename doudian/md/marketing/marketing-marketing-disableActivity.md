# 失效营销玩法

> marketing.disableActivity — 失效营销玩法

| 元信息 | 值 |
| --- | --- |
| 中文名 | 失效营销玩法 |
| 文档地址 | `/docs/doudian/marketing/marketing-marketing-disableActivity` |
| 接口 ID | `doudian.marketing.marketing.disableActivity` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/disableActivity` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7780 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 否 | 玩法活动id | `7542839217882202406` |
| `common_ctx_info` | body | object | 否 | 通用信息 | `` |
| `  └ operator_id` | body | mixed | 否 | 1 | `1` |
| `  └ source_type` | body | mixed | 否 | 1 | `1` |
| `  └ operator_type` | body | mixed | 否 | 1 | `1` |
| `  └ isv_info` | body | object | 否 | 第三方应用信息 | `` |
| `    └ app_key` | body | mixed | 否 | isv应用id | `1` |
| `    └ app_name` | body | string | 否 | ISV应用名称 | `1` |
| `  └ shop_info` | body | object | 否 | 1 | `` |
| `    └ shop_id` | body | mixed | 否 | 1 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/disableActivity?app_key=your_appkey_here&method=marketing.disableActivity&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_id` | mixed | 活动id | `7542839217882202406` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 失效活动太频繁，请稍后重试~（sub_code: isv.business-failed:510020003） | 重试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:-100001） | 调整传参 |
| `20000` | 系统错误（sub_code: isp.service-error:510050002） | 联系技术人员排查 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_id": "7542839217882202406"
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
  "sub_code": "isv.business-failed:510020003",
  "sub_msg": "失效活动太频繁，请稍后重试~"
}
```

## 备注
