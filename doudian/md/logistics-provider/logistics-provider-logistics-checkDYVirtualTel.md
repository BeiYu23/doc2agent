# logistics.checkDYVirtualTel

> 查询虚拟号是否抖音平台

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.checkDYVirtualTel` |
| 中文名 | 查询虚拟号是否抖音平台 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/checkDYVirtualTel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8157 |
| 更新日期 | `2026-03-23` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `system_source` | body | string | 否 | 系统来源，根据物流公司内部系统的代号传值，比如CRM系统，网点操作系统、小件员APP等，区分系统唯一性 | `xx系统` |
| `virtual_tel_number` | body | string | 否 | 虚拟号 | `700001010100` |
| `extra` | body | string | 否 | 扩展信息 | `{}` |
| `user_type` | body | string | 否 | 请求用户类型，1-系统；2-业务员（快递员）；3-客服；4-总部业务人员；5-网点业务人员 | `1` |
| `net_code` | body | string | 否 | 查询用户的所属机构编码 | `1234` |
| `net_name` | body | string | 否 | 查询用户的所属机构名称 | `1234` |
| `user_id` | body | string | 否 | 若userType≠1时，则必须传入具体用户的系统ID，可以结合systemSource中的系统的用户ID | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/checkDYVirtualTel?app_key=your_appkey_here&method=logistics.checkDYVirtualTel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_dy_virtual_tel` | mixed | 是否抖音电商虚拟号 1 是抖音电商虚拟号，0-不是 | `1` |
| `is_active` | mixed | 当前虚拟号是否生效中 1 生效中，0 已过期 | `1` |
| `request_id` | string | 唯一id，用于区分每次请求 | `2024321321321321` |
| `code` | mixed | 0表示成功 | `0` |
| `message` | string | 成功是""，失败包含失败原因 | `""` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "is_active": "1",
    "is_dy_virtual_tel": "1",
    "message": "\"\"",
    "request_id": "2024321321321321"
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
