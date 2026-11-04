# recycle.sms.searchSmsTemplate

> 获取短信模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.recycle.sms.searchSmsTemplate` |
| 中文名 | 获取短信模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/sms/searchSmsTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7832 |
| 更新日期 | `2025-11-03` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_content` | body | string | 否 | 模板内容 | `sfesf` |
| `status` | body | mixed | 否 | 状态 | `0` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `size` | body | mixed | 否 | 页大小 | `10` |
| `template_name` | body | string | 否 | 模板名称 | `qweqwe` |
| `sms_account` | body | string | 否 | 渠道账号 | `sfwa` |
| `template_id` | body | string | 否 | 模板id | `sfes` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/sms/searchSmsTemplate?app_key=your_appkey_here&method=recycle.sms.searchSmsTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_search_list` | array | 11 | `` |
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
    "template_search_list": [
      {
        "channel_type": "CN_NTC",
        "sms_account": "sefasef",
        "template_content": "sefsefa",
        "template_id": "ST_Xxxx",
        "template_name": "模板"
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
