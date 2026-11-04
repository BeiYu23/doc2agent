# sms.saveUserAudience

> 保存(更新)人群

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.saveUserAudience` |
| 中文名 | 保存(更新)人群 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/saveUserAudience` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6682 |
| 更新日期 | `2024-10-22` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `content_desc` | body | string | 否 | 人群包描述 | `人群包描述` |
| `and_content` | body | object | 否 | 人群包内容(交) | `` |
| `  └ logic_operation` | body | mixed | 否 | 逻辑操作符 | `1` |
| `  └ audience_type` | body | mixed | 否 | 人群查询类型 | `1` |
| `  └ label_list` | body | array | 否 | 需要保存/返回的标签结构体 | `` |
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
| `    └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `    └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ logic_operation` | body | mixed | 否 | 嵌套的下层的逻辑操作符 | `1` |
| `    └ label_list` | body | array | 否 | 嵌套的下层标签 | `` |
| `      └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `        └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `        └ param_name` | body | string | 否 | 参数字名称 | `""` |
| `      └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `      └ label_id` | body | string | 否 | 标签id | `1` |
| `or_content` | body | object | 否 | 人群包内容(并) | `` |
| `  └ logic_operation` | body | mixed | 否 | 逻辑操作符 | `1` |
| `  └ audience_type` | body | mixed | 否 | 人群查询类型 | `1` |
| `  └ label_list` | body | array | 否 | 需要保存/返回的标签结构体 | `` |
| `    └ label_list` | body | array | 否 | 嵌套的下层标签 | `` |
| `      └ label_id` | body | mixed | 否 | 标签id | `1` |
| `      └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `      └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `    └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `      └ sub_param_list` | body | array | 否 | 子参数,以下是商品信息传递 | `` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `        └ param_name` | body | string | 否 | 参数名称 | `未使用  数码配件-键盘【2】` |
| `        └ param_str` | body | string | 否 | 参数 | `3697888078900363605` |
| `      └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `      └ param_id` | body | mixed | 否 | 参数id | `1` |
| `      └ param_name` | body | string | 否 | 参数名称 | `""` |
| `      └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `    └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `    └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ logic_operation` | body | mixed | 否 | 嵌套的下层的逻辑操作符 | `1` |
| `audience_id` | body | string | 否 | 不传值时为创建 | `"4354561721259311404"` |
| `audience_name` | body | string | 是 | 人群包名称 | `测试` |
| `except_content` | body | object | 否 | 人群包内容(差) | `` |
| `  └ logic_operation` | body | mixed | 否 | 逻辑操作符 | `4` |
| `  └ audience_type` | body | mixed | 否 | 人群查询类型 | `1` |
| `  └ label_list` | body | array | 否 | 需要保存/返回的标签结构体 | `` |
| `    └ label_list` | body | array | 否 | 嵌套的下层标签 | `` |
| `      └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `        └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `      └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ param_list` | body | array | 否 | 可选参数列表或已选参数列表 | `` |
| `      └ param_id` | body | mixed | 否 | 参数id | `1` |
| `      └ param_name` | body | string | 否 | 参数名称 | `""` |
| `      └ sub_param_list` | body | array | 否 | 子参数列表，用于级联多选 | `` |
| `        └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `        └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `        └ param_name` | body | string | 否 | 参数名称 | `""` |
| `        └ param_id` | body | mixed | 否 | 参数id | `1` |
| `      └ param_desc` | body | string | 否 | 标签描述 | `""` |
| `      └ param_str` | body | string | 否 | 参数字符串 | `""` |
| `    └ extra_map` | body | string | 否 | 额外参数，如区间值的>X minPrice, maxPrice | `{"key":"value"}` |
| `    └ label_id` | body | mixed | 否 | 标签id | `1` |
| `    └ logic_operation` | body | mixed | 否 | 嵌套的下层的逻辑操作符 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/saveUserAudience?app_key=your_appkey_here&method=sms.saveUserAudience&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `audience_id` | string | 人群id | `"4354561721259311404"` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:628002001） | 请确认参数是否合法 |
| `40004` | 非法的参数 / 请求资源非法（sub_code: isv.parameter-invalid:628005600） | 请求资源非法 |
| `50002` | 业务处理失败 / 内部异常（sub_code: isv.business-failed:628004004） | 若重试无法成功,请联系管理员排查 |
| `50002` | 业务处理失败 / 内部异常（sub_code: isv.business-failed:628004630） | 若重试无法成功,请联系管理员排查 |
| `80000` | 风控拦截 / 系统不可用拦截（sub_code: isv.risk-control-failed:628004410） | 待系统恢复 |
| `50002` | 业务处理失败 / 请求超时（sub_code: isv.business-failed:628004002） | 请求超时 |

## 响应示例

成功：

```json
{
  "data": {
    "audience_id": "\"4354561721259311404\""
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
