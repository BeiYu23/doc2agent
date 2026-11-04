# medicine.sendSpecifyMessage

> 当医生拒绝开处方单，需要将理由同步到医药行业平台

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.hospital.medicine.sendSpecifyMessage` |
| 中文名 | 当医生拒绝开处方单，需要将理由同步到医药行业平台 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/sendSpecifyMessage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1451/6211 |
| 更新日期 | `2024-02-29` |

## 接口说明

- 文档书: 互联网医院（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `consult_id` | body | mixed | 是 | 问诊id | `6926895034630739235` |
| `content` | body | string | 否 | 拒方理由 | `患者未响应` |
| `type` | body | mixed | 是 | 消息类型 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/medicine/sendSpecifyMessage?app_key=your_appkey_here&method=medicine.sendSpecifyMessage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:-1） | check |
| `50002` | 业务处理失败 / 参数异常（sub_code: isv.business-failed:100001） | 传入必填参数 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "系统错误"
}
```

## 备注
