# 获取视频短信模板list

> sms.getVmsTemplateList — 获取视频短信模板list

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取视频短信模板list |
| 文档地址 | `/docs/doudian/sms/sms-sms-getVmsTemplateList` |
| 接口 ID | `doudian.sms.sms.getVmsTemplateList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getVmsTemplateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/4017 |
| 更新日期 | `2026-04-20` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信account | `12345` |
| `name` | body | string | 否 | 模板名称 | `618大促` |
| `signature` | body | string | 否 | 模板签名 | `测试旗舰店` |
| `template_id` | body | string | 否 | 模板id | `VT_1234` |
| `status` | body | array | 否 | 状态 1：字节审核中 2：字节审核拒绝 3：字节审核通过 4 ：字节审核关闭 5：字节审核免审 6：运营商审核中 7：运营商审核失败 8：运营商审核通过 | `1` |
| `page_index` | body | mixed | 否 | 分页页数，从1开始 | `1` |
| `page_size` | body | mixed | 否 | 分页大小 | `10` |
| `version` | body | string | 否 | 版本，v2是新版本 | `v2` |
| `template_biz_type` | body | mixed | 否 | 模板业务类型 | `1` |
| `template_biz_sub_type` | body | mixed | 否 | 模板业务子类型 | `100000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/getVmsTemplateList?app_key=your_appkey_here&method=sms.getVmsTemplateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | array | 结果 | `` |
| `total` | mixed | 数量 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:628005100） | 业务处理失败，请检查请求参数 |
| `40004` | 非法的参数 / 请求入参非法（sub_code: isv.parameter-invalid:628002001） | 请检查请求入参 |
| `50002` | 业务处理失败 / 628004702:HttpPost请求失败（sub_code: isv.business-failed:628004702） | 628004702:HttpPost请求失败 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "approve_time": "1697610232",
        "carrier_status": {
          "china_mobile": {
            "reason": "涉及敏感词",
            "status": "1"
          },
          "china_telecom": {
            "reason": "涉及敏感词",
            "status": "1"
          },
          "china_unicom": {
            "reason": "涉及敏感词",
            "status": "1"
          }
        },
        "channel_type": "CN_VMS",
        "content": "xxx",
        "create_time": "1677600000",
        "desc": "test",
        "expire_time": "1697610232",
        "rest_valid_days": "30",
        "signature": "测试旗舰店",
        "status": "1",
        "template_biz_sub_type": "1",
        "template_biz_type": "100000",
        "template_id": "VT_1234",
        "template_name": "618大促",
        "theme": "618大促主题"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:628005100",
  "sub_msg": "业务处理失败"
}
```

## 备注
