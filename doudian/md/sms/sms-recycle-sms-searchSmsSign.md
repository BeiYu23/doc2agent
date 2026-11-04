# recycle.sms.searchSmsSign

> 签名列表接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.recycle.sms.searchSmsSign` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/sms/searchSmsSign` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7833 |
| 更新日期 | `2025-11-03` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 否 | sms渠道账号 | `ssefse` |
| `like` | body | string | 否 | 搜索 | `1sdf` |
| `size` | body | mixed | 否 | 页大小 | `10` |
| `page` | body | mixed | 否 | 页码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/sms/searchSmsSign?app_key=your_appkey_here&method=recycle.sms.searchSmsSign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sign_search_list` | array | 11 | `` |
| `total` | mixed | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "sign_search_list": [
      {
        "apply_time": "111",
        "sign": "111",
        "sms_account": "111"
      }
    ],
    "total": "10"
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
