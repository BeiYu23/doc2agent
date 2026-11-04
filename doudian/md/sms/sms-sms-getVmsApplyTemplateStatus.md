# sms.getVmsApplyTemplateStatus

> 查询视频短信模板申请状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.getVmsApplyTemplateStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getVmsApplyTemplateStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/4015 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信account | `12345` |
| `template_id` | body | string | 是 | 申请的模板id | `VT_1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/getVmsApplyTemplateStatus?app_key=your_appkey_here&method=sms.getVmsApplyTemplateStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | array | 响应结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:628005100） | 业务处理失败，请检查请求参数 |
| `40004` | 非法的参数 / 请求入参非法（sub_code: isv.parameter-invalid:628002001） | 请检查请求入参 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "approve_time": "1697610232",
        "carrier": "China Mobile",
        "expire_time": "1697610232",
        "reason": "有敏感词",
        "rest_valid_days": "30",
        "status": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:628005100",
  "sub_msg": "业务处理失败"
}
```

## 备注
