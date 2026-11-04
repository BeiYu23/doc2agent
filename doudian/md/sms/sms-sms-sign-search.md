# 查看短信签名

> sms.sign.search — 查看短信签名

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查看短信签名 |
| 文档地址 | `/docs/doudian/sms/sms-sms-sign-search` |
| 接口 ID | `doudian.sms.sms.sign.search` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sign/search` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1515 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `like` | body | string | 否 | 模糊搜索串 | `abc` |
| `size` | body | mixed | 否 | 每页大小，默认10 | `10` |
| `page` | body | mixed | 否 | 页码，默认0 | `0` |
| `version` | body | string | 否 | 版本号 v2则走新链路 | `v2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/search?app_key=your_appkey_here&method=sms.sign.search&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sign_search_list` | array | 签名列表 | `` |
| `total` | mixed | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 628004205:Redis Get错误（sub_code: isp.service-error:628004205） | 系统内部错误，请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "sign_search_list": [
      {
        "sign": "abc",
        "sms_account": "1234"
      }
    ],
    "total": "100"
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
  "sub_code": "isp.service-error:628004205",
  "sub_msg": "628004205:Redis Get错误"
}
```

## 备注
