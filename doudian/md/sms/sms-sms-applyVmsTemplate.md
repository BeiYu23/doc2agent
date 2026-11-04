# sms.applyVmsTemplate

> 申请创建图文短信模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.applyVmsTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/applyVmsTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/4014 |
| 更新日期 | `2026-05-14` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信account | `123456` |
| `template_name` | body | string | 是 | 模板名称 | `618大促` |
| `template_theme` | body | string | 是 | 模板主题 | `营销视频短信` |
| `contents` | body | array | 是 | 短信模板内容 | `` |
| `  └ source_type` | body | string | 是 | 文本：text/string jpg图片：image/jpg png图片：image/png  gif图片：image/gif | `text/string` |
| `  └ content` | body | string | 否 | 文本类型：传string utf-8，其他类型传image_url字段。 文本内容结尾需要带上固定文案：TD退订、T退订或者N退订。 | `内容` |
| `  └ image_url` | body | string | 否 | 当sourceType为image/jpg   image/png image/gif时必填。总大小不超过1.9M。 | `image/gif` |
| `signature` | body | string | 是 | 短信签名 | `测试旗舰店` |
| `extra` | body | string | 否 | 模板描述 | `这是描述` |
| `template_biz_sub_type` | body | mixed | 否 | 模板业务子类型 | `100000` |
| `template_biz_type` | body | mixed | 否 | 模板业务类型 | `1` |
| `version` | body | string | 否 | 版本 | `v2` |
| `is_public` | body | boolean | 否 | 是否公域短信 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/applyVmsTemplate?app_key=your_appkey_here&method=sms.applyVmsTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_id` | string | 模板id | `VT_1234` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:628005100） | 业务处理失败，请检查请求参数 |
| `40004` | 非法的参数 / 请求入参非法（sub_code: isv.parameter-invalid:628002001） | 请检查请求入参 |
| `50002` | 业务处理失败 / 628004001:RPC通用错误（sub_code: isv.business-failed:628004001） | 检查参数并稍后重试 |
| `40004` | 非法的参数 / 暂不支持的内容类型（sub_code: isv.parameter-invalid:628003401） | 请检查sourceType入参是否满足平台要求 |
| `50002` | 业务处理失败 / 图文内容不合法（sub_code: isv.business-failed:628003400） | 图文内容不合法 |

## 响应示例

成功：

```json
{
  "data": {
    "template_id": "VT_1234"
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
  "sub_code": "isv.business-failed:628005100",
  "sub_msg": "业务处理失败"
}
```

## 备注
