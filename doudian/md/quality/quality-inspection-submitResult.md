# inspection.submitResult

> 外部服务商上传质检结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.quality.inspection.submitResult` |
| 中文名 | 外部服务商上传质检结果 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/submitResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1582/7265 |
| 更新日期 | `2025-02-12` |

## 接口说明

- 文档书: 质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_type` | body | string | 是 | 业务身份参数，前置质检：machine_pre_inspection | `machine_pre_inspection` |
| `targets` | body | array | 是 | 质检对象列表，批量上传数量不能超过100个 | `` |
| `  └ collection_code` | body | string | 是 | 质检对象匹配的质检标准集标识 | `7460063059139674403_1` |
| `  └ result_detail` | body | object | 是 | 质检结果详情 | `` |
| `    └ result` | body | number | 是 | 质检结果, 1-合格，2-不合格，目前仅支持上传合格 | `1` |
| `    └ img_urls` | body | array | 否 | 质检结果图片url,最多上传30张，图片大小不超过2MB | `["https://xxx"]` |
| `    └ remark` | body | string | 否 | 备注 | `备注信息` |
| `    └ item_results` | body | array | 否 | 质检项结果列表 | `` |
| `      └ item_name` | body | string | 否 | 非必填，可以填空字符串 | `""` |
| `      └ material_info` | body | object | 否 | 材料信息 | `` |
| `        └ text` | body | string | 否 | 文本形式结果 | `轻微划痕` |
| `      └ item_code` | body | string | 否 | 标准项code | `7460064458699129088_1` |
| `      └ result` | body | number | 否 | 1-合格，2-不合格，3-无法检测 | `1` |
| `  └ target_type` | body | string | 是 | 质检对象类型，如果为手机，请传phone | `phone` |
| `  └ target_code` | body | string | 是 | 质检对象标识，如果为手机，请传IMEI号 | `356303485265827` |
| `  └ target_info` | body | string | 否 | 质检对象信息，非必填 | `nil` |
| `extra` | body | string | 否 | 额外信息，非必填 | `nil` |
| `biz_code` | body | string | 是 | 业务身份参数，二手：second_hand_inspection | `second_hand_inspection` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 不支持的业务线（sub_code: isv.parameter-invalid:601） | 传入正确的业务身份biz_code |
| `40004` | 非法的参数 / 不支持的质检任务类型（sub_code: isv.parameter-invalid:602） | 传入正确的业务身份task_type |
| `40004` | 非法的参数 / 质检对象数量超出限制（sub_code: isv.parameter-invalid:617） | 批量上传的手机一次不能超过100 |
| `40004` | 非法的参数 / 质检对象不能为空（sub_code: isv.parameter-invalid:616） | 质检对象不能为空 |
| `40004` | 非法的参数 / 质检项校验失败（sub_code: isv.parameter-invalid:615） | 检查质检项填写是否正确 |
| `40004` | 非法的参数 / 不支持的质检对象类型（sub_code: isv.parameter-invalid:1001a） | 传入正确的质检对象类型 |
| `40004` | 非法的参数 / targetCode不能为空（sub_code: isv.parameter-invalid:1001b） | 传入正确的IMEI号 |
| `40004` | 非法的参数 / 质检结果不能为空（sub_code: isv.parameter-invalid:1001c） | 质检结果不能为空 |
| `40004` | 非法的参数 / 质检结果非法（sub_code: isv.parameter-invalid:1001d） | 只支持合格的质检结果 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:601",
  "sub_msg": "不支持的业务线"
}
```

## 备注
