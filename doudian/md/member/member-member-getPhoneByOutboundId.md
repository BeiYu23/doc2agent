# member.getPhoneByOutboundId

> 根据外呼id获取手机号（火山专用）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.member.getPhoneByOutboundId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/getPhoneByOutboundId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6062 |
| 更新日期 | `2024-01-12` |

## 接口说明

- 文档书: 会员中心API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outbound_id` | body | string | 是 | 外呼id | `1705042185-vIHAKNwhR` |
| `volc_account_id` | body | mixed | 是 | 火山账号id | `111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/getPhoneByOutboundId?app_key=your_appkey_here&method=member.getPhoneByOutboundId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `encrypt_phone` | string | 加密手机号 | `972cc1908c1c2ae452d4ee256761acafe7e7bb1955d8e2887a5a8b` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参错误（sub_code: isv.parameter-invalid:628002001） | 检查入参 |
| `50002` | 业务处理失败 / 火山账号与开发者账号不匹配（sub_code: isv.business-failed:628002004） | 火山账号与开发者账号不匹配 |
| `50002` | 业务处理失败 / 外呼id已过期（sub_code: isv.business-failed:628003201） | 外呼id已过期 |

## 响应示例

成功：

```json
{
  "data": {
    "encrypt_phone": "972cc1908c1c2ae452d4ee256761acafe7e7bb1955d8e2887a5a8b"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "入参错误"
}
```

## 备注
