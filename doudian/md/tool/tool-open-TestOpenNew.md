# open.TestOpenNew

> 测试使用的API

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.TestOpenNew` |
| 中文名 | 测试使用的 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/TestOpenNew` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/2273 |
| 更新日期 | `2022-08-01` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `req_not_must` | body | number | 否 | 1 | `1` |
| `req_int64` | body | number | 是 | 1 | `1` |
| `req_string` | body | string | 是 | 1 | `1` |
| `req_bool` | body | boolean | 是 | 1 | `11` |
| `req_cons_int64` | body | number | 是 | 1 | `1` |
| `req_cons_string` | body | string | 是 | 1 | `1` |
| `req_cons_bool` | body | boolean | 是 | 1 | `1` |
| `req_int16` | body | string | 是 | 1 | `1` |
| `req_int32` | body | string | 是 | 1 | `1` |
| `req_list_int64` | body | array | 是 | 1 | `1` |
| `req_list_string` | body | array | 是 | 1 | `1` |
| `req_list_bool` | body | array | 是 | 1 | `1` |
| `req_list_int16` | body | array | 是 | 1 | `1` |
| `req_list_int32` | body | array | 是 | 1 | `1` |
| `req_list_struct` | body | array | 是 | 1 | `` |
| `  └ sub_int64` | body | number | 是 | 1 | `1` |
| `  └ sub_string` | body | string | 是 | 1 | `1` |
| `  └ sub_list` | body | array | 是 | 1 | `1` |
| `  └ sub_struct` | body | object | 是 | 1 | `` |
| `    └ sub_struct_int64` | body | number | 是 | 1 | `1` |
| `    └ sub_struct_string` | body | string | 是 | 1 | `1` |
| `    └ sub_struct_int32` | body | string | 是 | 1 | `1` |
| `    └ sub_struct_list` | body | array | 是 | 1 | `1` |
| `req_struct` | body | object | 是 | 1 | `` |
| `  └ struct_int64` | body | number | 是 | 1 | `1` |
| `  └ struct_string` | body | string | 是 | 1 | `1` |
| `  └ struct_bool` | body | boolean | 是 | 1 | `1` |
| `  └ struct_list` | body | array | 是 | 1 | `` |
| `    └ sub_int64` | body | number | 是 | 1 | `1` |
| `    └ sub_string` | body | string | 是 | 1 | `1` |
| `    └ sub_list` | body | array | 是 | 1 | `1` |
| `  └ struct_struct` | body | object | 是 | 1 | `` |
| `    └ struct_struct_int64` | body | number | 是 | 1 | `1` |
| `    └ struct_struct_string` | body | string | 是 | 1 | `1` |
| `    └ struct_struct_int32` | body | string | 是 | 1 | `1` |
| `    └ struct_struct_list` | body | array | 是 | 1 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/TestOpenNew?app_key=your_appkey_here&method=open.TestOpenNew&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `res_int64` | number | 1 | `1` |
| `res_string` | string | 1 | `1` |
| `res_bool` | boolean | 1 | `1` |
| `res_cons_int64` | number | 1 | `1` |
| `res_cons_string` | string | 1 | `1` |
| `res_cons_bool` | boolean | 1 | `1` |
| `res_int16` | string | 1 | `1` |
| `res_int32` | string | 1 | `1` |
| `res_list_int64` | array | 1 | `1` |
| `res_list_string` | array | 1 | `1` |
| `res_list_bool` | array | 1 | `1` |
| `res_list_int16` | array | 1 | `1` |
| `res_list_int32` | array | 1 | `1` |
| `res_list_struct` | array | 1 | `` |
| `res_struct` | object | 1 | `` |
| `shop_id` | number | 1 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "res_bool": "1",
    "res_cons_bool": "1",
    "res_cons_int64": "1",
    "res_cons_string": "1",
    "res_int16": "1",
    "res_int32": "1",
    "res_int64": "1",
    "res_list_bool": "1",
    "res_list_int16": "1",
    "res_list_int32": "1",
    "res_list_int64": "1",
    "res_list_string": "1",
    "res_list_struct": [
      {
        "sub_int64": "1",
        "sub_list": "1",
        "sub_string": "1",
        "sub_struct": {
          "sub_struct_int32": "1",
          "sub_struct_int64": "1",
          "sub_struct_list": "1",
          "sub_struct_string": "1"
        }
      }
    ],
    "res_string": "1",
    "res_struct": {
      "struct_bool": "1",
      "struct_int64": "1",
      "struct_list": [
        {
          "sub_int64": "1",
          "sub_list": "1",
          "sub_string": "1"
        }
      ],
      "struct_string": "1",
      "struct_struct": {
        "struct_struct_int32": "1",
        "struct_struct_int64": "1",
        "struct_struct_list": "1",
        "struct_struct_string": "1"
      }
    },
    "shop_id": "1"
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
