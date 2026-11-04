# 人群灰产判断使用

> mini.riskCheck — 人群灰产判断使用

| 元信息 | 值 |
| --- | --- |
| 中文名 | 人群灰产判断使用 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-riskCheck` |
| 接口 ID | `doudian.miniapp.mini.riskCheck` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/riskCheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7619 |
| 更新日期 | `2025-07-31` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `union_id` | body | string | 是 | 抖音unionid | `77414dfb-7489-5f9d-befb-313e9810e1e2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/riskCheck?app_key=your_appkey_here&method=mini.riskCheck&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_risk` | boolean | true为有风险 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "is_risk": "true"
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
