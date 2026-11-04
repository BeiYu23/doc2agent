# sms.getTemplateBizType

> 获取模板类型

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.getTemplateBizType` |
| 中文名 | 获取模板类型 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getTemplateBizType` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/8219 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/getTemplateBizType?app_key=your_appkey_here&method=sms.getTemplateBizType&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_biz_type_list` | array | 模板类型 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "template_biz_type_list": [
      {
        "template_biz_sub_types": [
          {
            "template_biz_sub_type": "10000",
            "template_biz_sub_type_name": "订单发货"
          }
        ],
        "template_biz_type": "1",
        "template_biz_type_name": "订单管理"
      }
    ]
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
