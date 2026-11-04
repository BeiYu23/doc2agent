# sms.GetLabelParamList

> 标签参数获取

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.GetLabelParamList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/GetLabelParamList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/6728 |
| 更新日期 | `2024-07-26` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `label_id` | body | mixed | 否 | 标签id | `73` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/GetLabelParamList?app_key=your_appkey_here&method=sms.GetLabelParamList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `param_list` | array | 参数列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628002001） | 请校验输入参数 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628004001） | 请校验输入参数 |

## 响应示例

成功：

```json
{
  "data": {
    "param_list": [
      {
        "param_id": "0",
        "param_name": "颜值",
        "sub_param_list": [
          {
            "param_id": "颜值",
            "param_name": "0"
          }
        ]
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "参数错误"
}
```

## 备注
