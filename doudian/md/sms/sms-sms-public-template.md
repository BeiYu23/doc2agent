# sms.public.template

> 公共模版查询接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.public.template` |
| 中文名 | 公共模版查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/public/template` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1526 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 短信API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | mixed | 否 | 每页数据大小 | `10` |
| `page` | body | mixed | 否 | 第几页，从0开始 | `0` |
| `template_id` | body | string | 否 | 模版id | `ST_90251` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/public/template?app_key=your_appkey_here&method=sms.public.template&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 数据总量 | `100` |
| `public_template_list` | array | 列表页数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "public_template_list": [
      {
        "channel_type": "CN_OTP",
        "template_content": "你的验证码是${code},3分钟内有效",
        "template_id": "ST_0000",
        "template_name": "验证码"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
