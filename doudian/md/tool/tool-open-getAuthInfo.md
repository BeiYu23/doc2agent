# 查询授权信息

> open.getAuthInfo — 查询授权信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询授权信息 |
| 文档地址 | `/docs/doudian/tool/tool-open-getAuthInfo` |
| 接口 ID | `doudian.tool.open.getAuthInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/getAuthInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/3582 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `auth_id` | body | string | 是 | 授权主体ID，这里为店铺ID | `12121321212` |
| `auth_subject_type` | body | string | 否 | 授权主体类型，默认为店铺授权，不需要填写。 其他类型枚举值如下：YunCang -云仓；WuLiuShang -物流商；WLGongYingShang -物流供应商；MiniApp -小程序 MCN-联盟MCN机构 DouKe-联盟抖客 Colonel-联盟团长 | `WuLiuShang` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/getAuthInfo?app_key=your_appkey_here&method=open.getAuthInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status` | string | 授权状态，1为正常。枚举为 0:待商家确认，1:正常，2:取消，3:过期。 授权状态为正常时，需额外判断auth_end_time | `1` |
| `auth_success_time` | number | 授权生效时间 | `1681351741` |
| `auth_end_time` | number | 授权截止时间 | `1681351741` |
| `auth_id` | string | 授权主体ID | `12121212` |
| `auth_update_time` | number | 授权最近一次更新时间 | `1681351741` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:100001） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / auth_subject_type值非法（sub_code: isv.parameter-invalid:100003） | 请填写正确的auth_subject_type |

## 响应示例

成功：

```json
{
  "data": {
    "auth_end_time": "1681351741",
    "auth_id": "12121212",
    "auth_success_time": "1681351741",
    "auth_update_time": "1681351741",
    "status": "1"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:100001",
  "sub_msg": "系统异常，请稍后重试"
}
```

## 备注
