# sms.bulkCreateTobTrafficDrivingLink

> 批量创建引流链接

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.bulkCreateTobTrafficDrivingLink` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/bulkCreateTobTrafficDrivingLink` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/8438 |
| 更新日期 | `2026-07-28` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `data` | body | array | 否 | 数据 | `` |
| `  └ link_domain_icp_body` | body | string | 否 | 文案链接域名备案主体，不使用火山短链时必填，使用火山短链时不可填 | `test-icpBody` |
| `  └ jump_link` | body | string | 否 | 跳转链接 | `https://test-xxx.com/demo` |
| `  └ protocol` | body | string | 否 | 协议，参考：https://docs.volcengine.com/docs/6361/1856289?lang=zh | `https` |
| `  └ link` | body | string | 否 | 链接，参考：https://docs.volcengine.com/docs/6361/1856289?lang=zh | `https://test-xxx.com/demo` |
| `  └ jump_link_domain_icp` | body | string | 否 | 跳转链接域名备案 | `test-icp` |
| `  └ jump_link_domain_icp_body` | body | string | 否 | 文案链接域名备案主体，不使用火山短链时必填，使用火山短链时不可填 | `test-icpBody` |
| `  └ use_volc_link` | body | boolean | 否 | 是否使用火山链接 | `false` |
| `  └ link_domain_icp` | body | string | 否 | 文案链接域名备案号，不使用火山短链时必填，使用火山短链时不可填 | `test-icp` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/bulkCreateTobTrafficDrivingLink?app_key=your_appkey_here&method=sms.bulkCreateTobTrafficDrivingLink&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
