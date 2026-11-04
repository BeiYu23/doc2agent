# recycle.sms.sendIndustrySms

> 发送短信

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.recycle.sms.sendIndustrySms` |
| 中文名 | 发送短信 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/sms/sendIndustrySms` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7835 |
| 更新日期 | `2025-11-03` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 否 | 渠道账号 | `123s212` |
| `template_id` | body | string | 否 | 模版id | `ST_XXX` |
| `sms_test_verification` | body | object | 否 | 测试发送验证码 | `` |
| `  └ post_tel` | body | string | 否 | 明文手机号 | `12323412312` |
| `  └ code` | body | string | 否 | 验证码 | `912044` |
| `order_info` | body | object | 否 | 服务店铺单id | `` |
| `  └ service_order_no` | body | string | 否 | 服务单号 | `123123` |
| `  └ lp_code` | body | string | 否 | lp code | `sfasd` |
| `sign` | body | string | 否 | 签名 | `测试` |
| `template_param` | body | string | 否 | 模版参数, map[string]string类型json序列化之后的字符串 | `"{}"` |
| `tag` | body | string | 否 | 透传字段，调用call_back的时候原样返回 | `{}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/sms/sendIndustrySms?app_key=your_appkey_here&method=recycle.sms.sendIndustrySms&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
