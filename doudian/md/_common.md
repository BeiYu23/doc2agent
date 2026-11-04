# 抖店开放平台公共参数

> 所有接口调用都需要携带的公共参数与签名说明（来源: 文档站 publicParam）。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian._common` |
| 中文名 | 抖店开放平台公共参数 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/（网关公共参数）` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/guide-docs/10/23 |
| 更新日期 | `2026-11-04` |

## 接口说明

- 抽样自: 豆包工作 / /contentAIGC/createAIVideoTaskOpen

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `method` | query | string | 是 | 调用的API接口名称 | `contentAIGC.createAIVideoTaskOpen` |
| `app_key` | query | string | 是 | 应用创建完成后被分配的key | `6839996111118329223` |
| `access_token` | query | string | 是 | 用于调用 API 的 access_token | `edae7c30-8386-443b-88a1-031111596fdd` |
| `param_json` | query | string | 是 | 标准json类型，里面是业务参数按照参数名的字符串大小排序具体参数值，参考每个接口的参数表 | `{cid:12,page:1}` |
| `timestamp` | query | string | 是 | 时间戳，格式为yyyy-MM-dd HH:mm:ss，时区为GMT+8，例如：2016-01-01 12:00:00 | `2020-09-15 14:48:13` |
| `v` | query | string | 是 | API协议版本，当前版本为2 | `2` |
| `sign` | query | string | 是 | 输入参数签名结果，签名算法参照 [API调用指南](https://op.jinritemai.com/docs/guide-docs/10/23) | `796559d40beb08a1a1113c456c5c5a62` |
| `sign_method` | query | string | 否 | 签名算法类型推荐使用hmac-sha256后续会下线md5（不传则默认为"md5"）1. md5:表示用md5算法加密字符串 2. hmac-sha256:表示用hmac_sha_256算法加密字符串 | `hmac-sha256` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=xxx&app_key=xxx&access_token=xxx&param_json={}&timestamp=2026-01-01 12:00:00&v=2&sign=xxx&sign_method=hmac-sha256'
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
  "msg": "success"
}
```

失败：

```json
{
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
