# instantShopping.marketing.createShopFreightDiscount

> 创建配送费营销活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.createShopFreightDiscount` |
| 中文名 | 创建配送费营销活动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/7551 |
| 更新日期 | `2025-07-03` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity` | body | object | 是 | 活动信息 | `` |
| `  └ activity_title` | body | string | 是 | 活动名称，最大25个字符 | `测试活动标题` |
| `  └ activity_type` | body | string | 是 | 活动类型，50：配送费营销 | `50` |
| `  └ activity_sub_type` | body | string | 是 | 活动子类型，502:配送费满减 | `502` |
| `  └ activity_base_info` | body | object | 否 | 活动基础信息 | `` |
| `    └ subsidy_apply_way` | body | string | 是 | ALL_ACTIVITY_TIME：活动时间内都补贴; SPECIFIED_TIME_PERIOD：指定时间段补贴 | `ALL_ACTIVITY_TIME` |
| `    └ is_free_freight` | body | boolean | 是 | 是否包邮（配送费0元） | `false` |
| `    └ activity_end_time` | body | number | 是 | 活动结束时间 | `1782748799` |
| `    └ discount_rules` | body | array | 否 | 满减规则，满减规则数量限制为1-5个， 多级，其中满额和减额分别需要大于上一级的满额和减额 | `` |
| `      └ condition_value` | body | string | 否 | 满足XX金额，补贴生效，单位：分，最多1位小数 | `111` |
| `      └ discount_value` | body | string | 否 | 配送费减免金额，单位：分，最多1位小数 | `0.1` |
| `    └ activity_start_time` | body | number | 是 | 活动开始时间 | `1751212800` |
| `    └ limit_week` | body | array | 否 | 活动期间内生效的时间段， 若subsidy_apply_way为SPECIFIED_TIME_PERIOD，则需要指定生效时间为周几 | `[1,2,3,4,5,6,7]` |
| `    └ day_time_range` | body | array | 否 | 活动生效的每日时间段，[0,86399]为全天生效，限制不超过10个 | `` |
| `      └ end_time` | body | number | 否 | 活动生效日期内，每日的开始时间 | `0` |
| `      └ start_time` | body | number | 否 | 活动生效日期内，每日的结束时间 | `86399` |
| `request_id` | body | string | 是 | 幂等ID，长度最大100个字符 | `test111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/orderCustomClearance?app_key=your_appkey_here&method=crossborder.orderCustomClearance&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_id` | string | 活动ID | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-40000） | 检查请求参数 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20000` | 系统错误 / 系统异常，请联系技术人员排查（sub_code: isp.service-error:-11450） | 系统异常，请联系技术人员排查 |

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
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
