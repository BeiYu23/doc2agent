# sms.getAccurateUserAmount

> 预估人群大小

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.getAccurateUserAmount` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getAccurateUserAmount` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6684 |
| 更新日期 | `2024-07-30` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `from_cache` | body | boolean | 否 | 是否查询缓存 | `false` |
| `audience_id` | body | string | 否 | 条件二选一 ,直接用人群包id预估人数 | `1221` |
| `query_type` | body | mixed | 否 | 查询条件 1: 全部, 12 isv可发送人数(会员+已购365) | `12` |
| `and_content` | body | object | 否 | 人群包内容(交) | `` |
| `  └ label_list` | body | array | 否 | 需要保存/返回的标签结构体 | `` |
| `    └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"source_audience_id": "6637613407932301612"}` |
| `    └ label_id` | body | mixed | 否 | 标签id | `标签id` |
| `    └ logic_operation` | body | mixed | 否 | 嵌套的下层的逻辑操作符(1交集 2并集 3差集) | `1` |
| `    └ label_list` | body | array | 否 | 嵌套的下层标签 | `` |
| `      └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"source_audience_id": "6637613407932301612"}` |
| `      └ param_list` | body | array | 否 | 标签参数 | `` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_desc` | body | string | 否 | 参数描述 | `""` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `      └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `      └ param_id` | body | mixed | 否 | 参数id | `1` |
| `      └ param_name` | body | string | 否 | 参数名称 | `""` |
| `      └ sub_param_list` | body | array | 否 | 子参数列表，用于级联多选 | `` |
| `        └ param_id` | body | mixed | 否 | 标签id | `1` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_desc` | body | string | 否 | 参数描述 | `""` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `      └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `      └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `  └ logic_operation` | body | mixed | 否 | 逻辑操作符 | `1` |
| `  └ audience_type` | body | mixed | 否 | 人群查询类型 不传 | `1` |
| `or_content` | body | object | 否 | 人群包内容(并) | `` |
| `  └ logic_operation` | body | mixed | 否 | 逻辑操作符 | `1` |
| `  └ audience_type` | body | mixed | 否 | 人群查询类型 | `1` |
| `  └ label_list` | body | array | 否 | 需要保存/返回的标签结构体 | `` |
| `    └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `    └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ logic_operation` | body | mixed | 否 | 嵌套的下层的逻辑操作符 | `1` |
| `    └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `      └ param_id` | body | mixed | 否 | 参数id | `1` |
| `      └ param_name` | body | string | 否 | 参数名称 | `""` |
| `      └ sub_param_list` | body | array | 否 | 子参数列表，用于级联多选 | `` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `      └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `      └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `except_content` | body | object | 否 | 人群包内容(差) | `` |
| `  └ logic_operation` | body | mixed | 否 | 逻辑操作符 | `1` |
| `  └ audience_type` | body | mixed | 否 | 人群查询类型 | `1` |
| `  └ label_list` | body | array | 否 | 需要保存/返回的标签结构体 | `` |
| `    └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `    └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ logic_operation` | body | mixed | 否 | 嵌套的下层的逻辑操作符 | `1` |
| `    └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `      └ param_name` | body | string | 否 | 参数名称 | `""` |
| `      └ sub_param_list` | body | array | 否 | 子参数列表，用于级联多选 | `` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_desc` | body | string | 否 | 参数描述 | `""` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `      └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `      └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `      └ param_id` | body | mixed | 否 | 参数id | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/ebillInfoGet?app_key=your_appkey_here&method=power.ebillInfoGet&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `estimated_amount` | mixed | 预估人群总数量 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:628002001） | 请确认参数 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:628005600） | 请确认参数 |
| `50002` | 业务处理失败 / 服务超时,请稍后再试（sub_code: isv.business-failed:628004000） | 请联系管理员 |
| `50002` | 业务处理失败 / 人群生产错误（sub_code: isv.business-failed:628005601） | 请联系管理员 |
| `50002` | 业务处理失败 / 数据拉取失败（sub_code: isv.business-failed:628004630） | 请稍后再试 |
| `50002` | 业务处理失败 / 628004004:内部异常（sub_code: isv.business-failed:628004004） | 628004004:内部异常 |
| `50002` | 业务处理失败 / 628004002:RPC超时（sub_code: isv.business-failed:628004002） | 628004002:RPC超时 |
| `50002` | 业务处理失败 / 628004001:RPC通用错误（sub_code: isv.business-failed:628004001） | 628004001:RPC通用错误 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:628002001",
  "sub_msg": "缺少必要参数"
}
```

## 备注
