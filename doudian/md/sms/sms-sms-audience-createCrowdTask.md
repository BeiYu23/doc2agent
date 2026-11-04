# 创建种子人群任务

> sms.audience.createCrowdTask — 创建种子人群任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建种子人群任务 |
| 文档地址 | `/docs/doudian/sms/sms-sms-audience-createCrowdTask` |
| 接口 ID | `doudian.sms.sms.audience.createCrowdTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/createCrowdTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7659 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `crowd_task` | body | object | 否 | 种子人群任务 | `` |
| `  └ id_type` | body | mixed | 否 | ID类型：2-MD5 32位小写加密手机号 | `2` |
| `  └ lookalike_count` | body | mixed | 是 | 预期放大人群数量 | `10000` |
| `  └ cate_ids` | body | array | 是 | 类目id | `` |
| `    └ first_cid` | body | mixed | 否 | 一级类目 | `200001` |
| `    └ second_cid` | body | mixed | 否 | 二级类目 | `210001` |
| `  └ crowd_name` | body | string | 是 | 人群包任务名称, 对应唯一一个人群包，不允许重复 | `订购高转人群` |
| `  └ seed_source` | body | string | 否 | 种子来源，见listSeedMeta接口SeedSourceList的取值，取英文赋值 | `PDD` |
| `  └ tos_url` | body | string | 否 | 人群包TOS地址，格式参考接入文档 | `http://xxx.com` |
| `  └ seed_rule_type` | body | string | 否 | 人群规则类型，见listSeedMeta接口SeedRuleTypes的取值，取英文赋值 | `PURCHASE_USERS` |
| `  └ liveroom_data` | body | string | 否 | 透传的直播间参数 | `<"live_room_id":"123">` |
| `  └ target_type` | body | string | 否 | 业务目标，见listSeedMeta接口TargetTypes的取值，取英文赋值 | `NEW_BUY` |
| `  └ seed_type` | body | string | 否 | 种子类型，见listSeedMeta接口SeedTypes的取值，取英文赋值 | `MEMBERSHIP` |
| `  └ crowd_type` | body | mixed | 是 | 人群包信息 2-公域种子人群 3-规则圈选种子人群，4-行为圈选，5-直播间人群 | `2` |
| `  └ exclude_seed` | body | boolean | 是 | 是否剔除种子 | `false` |
| `  └ seed_rule_period` | body | string | 否 | 种子人群规则周期，见listSeedMeta接口SeedRulePeriods的取值 | `30` |
| `  └ target_type_period` | body | string | 否 | 目标类型周期，取值1/7/15，见listSeedMeta接口TargetTypePeriods的取值 | `7` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.audience.createCrowdTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `crowd_task_id` | mixed | 人群任务id | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "crowd_task_id": "10"
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
