# superm.rejectReasonList

> 拒绝原因列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.rejectReasonList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/rejectReasonList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2958 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/rejectReasonList?app_key=your_appkey_here&method=superm.rejectReasonList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `reject_infos` | array | 拒绝原因列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20201） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "reject_infos": [
      {
        "reject_code": "12",
        "reject_reason": "联系不上用户"
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
  "sub_code": "isv.business-failed:20201",
  "sub_msg": "系统繁忙，请稍后重试"
}
```

## 备注
