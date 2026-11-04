# sms.uploadAudience

> 上传人群

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.uploadAudience` |
| 中文名 | 上传人群 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/uploadAudience` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6680 |
| 更新日期 | `2024-10-14` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `file_uri` | body | string | 是 | 手机号hash文件地址uri | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `audience_name` | body | string | 是 | 人群名称 | `自定义人群` |
| `upload_data_type` | body | mixed | 否 | 上传数据的类型：0默认手机号；1为openId | `1` |
| `temporary_audience` | body | boolean | 否 | 是否临时人群，临时人群有效期30天 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/uploadAudience?app_key=your_appkey_here&method=sms.uploadAudience&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `audience_id` | mixed | 人群id | `22074278516698983` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "audience_id": "22074278516698983"
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
