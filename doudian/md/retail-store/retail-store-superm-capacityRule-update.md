# superm.capacityRule.update

> 门店时段容量更新

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.capacityRule.update` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/capacityRule/update` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/3591 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `rule_operate_param` | body | object | 是 | 产能规则实体 | `` |
| `  └ rule_dto` | body | object | 否 | 产能规则 | `` |
| `    └ rule_id` | body | string | 是 | 规则id | `Rule-32154` |
| `    └ rule_name` | body | string | 是 | 规则名 | `test` |
| `    └ rule_entity_type` | body | string | 是 | 规则归属类型 ，本期只有 1: 企业 | `1` |
| `    └ date_limit_enable` | body | string | 是 | 是否启用单日限制，1启用2不启用 | `1` |
| `    └ date_limit_bound` | body | number | 否 | 单日限制上限（如果启用单日限制，则必填） | `1` |
| `    └ all_store` | body | string | 是 | 是否勾选全部门店（1是，2否） | `1` |
| `    └ status` | body | string | 是 | 规则状态，1启用，2不启用 | `1` |
| `  └ relations` | body | array | 否 | 关联的门店信息 | `` |
| `    └ capacity_target_type` | body | string | 是 | 作业产能类型 本期只有 1:门店 | `1` |
| `    └ capacity_target_code` | body | string | 是 | 仓编码\门店编码等 本期只有门店ID | `3215435` |
| `  └ details` | body | array | 否 | 规则详情 | `` |
| `    └ start_date` | body | string | 是 | 开始日期(2022-06-17) | `2022-06-17` |
| `    └ end_date` | body | string | 是 | 结束日期(2022-06-17) | `2022-06-17` |
| `    └ start_time` | body | string | 是 | 开始时间(19:00) | `19:00` |
| `    └ end_time` | body | string | 是 | 结束时间(23:00) | `23:00` |
| `    └ time_interval` | body | string | 是 | 产能限单时段，目前仅支持60 | `60` |
| `    └ time_limit_bound` | body | string | 是 | 产能限制单量 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/capacityRule/update?app_key=your_appkey_here&method=superm.capacityRule.update&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 获取组织关系失败（sub_code: isv.business-failed:20232） | 获取组织关系失败 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 门店查询服务失败（sub_code: isv.business-failed:20233） | 门店查询服务失败 |
| `50002` | 业务处理失败 / 数据转换错误（sub_code: isv.business-failed:50202） | 数据转换错误 |

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
  "sub_code": "isv.business-failed:20232",
  "sub_msg": "获取组织关系失败"
}
```

## 备注
