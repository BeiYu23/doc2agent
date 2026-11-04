# alliance.colonelActivityCreateOrUpdate

> 团长活动创建/编辑接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.alliance.colonelActivityCreateOrUpdate` |
| 中文名 | 团长活动创建/编辑 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/colonelActivityCreateOrUpdate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/966 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 否 | 活动ID | `111` |
| `application_limited` | body | boolean | 是 | 是否有报名门槛，默认无门槛 | `true` |
| `is_new_shop` | body | boolean | 否 | 报名门槛-新手店铺，当 application_limited = true 时必填：false 可报名（默认），true 不可报名 | `true` |
| `shop_type` | body | string | 否 | 报名门槛-店铺类型支持复选,当 application_limited = 1 时必填：0:普通店，1:专营店，2:旗舰店，3:专卖店，4:商场店，6:卖场型旗舰店，7：官方旗舰单，8：企业店，9:个体 | `0` |
| `activity_name` | body | string | 是 | 活动名称,不超过30个汉字 | `活动1111` |
| `activity_desc` | body | string | 是 | 活动描述,不超过200个汉字 | `活动111111` |
| `apply_start_time` | body | string | 是 | 商品报名开始时间 | `2021-09-02` |
| `apply_end_time` | body | string | 是 | 商品报名结束时间 | `2021-09-02` |
| `promote_start_time` | body | string | 否 | 推广开始时间 | `2021-09-02` |
| `promote_end_time` | body | string | 否 | 推广结束时间 | `2021-09-02` |
| `commission_rate` | body | string | 是 | 最低商品佣金率X100，小于等于50。服务费率+佣金率不能高于90% | `10` |
| `service_rate` | body | string | 是 | 团长服务费率X100，不超过40（服务费率不能超过40%） | `10` |
| `wechat_id` | body | string | 否 | 微信号 | `fasdf` |
| `phone_num` | body | string | 否 | 手机号 | `111111` |
| `estimated_single_sale` | body | string | 是 | 预估单品销售额，单位元 | `11111` |
| `activity_type` | body | mixed | 是 | 活动类型（1 全部商家 2 指定商家） | `1` |
| `specified_shop_ids` | body | string | 否 | 指定商家ID （入参为店铺的shop_id，当 application_scope =1 时必填） | `111` |
| `online` | body | boolean | 是 | 是否上线活动，默认不上线 | `true` |
| `categories` | body | string | 否 | 招商类目:支持复选：门捷列夫行业类目，传数字，多个用英文逗号隔开。类目获取接口：/alliance/activityProductCategoryList | `类目一` |
| `shop_score` | body | mixed | 否 | 报名门槛-店铺体验分（填整数，0表示不限） | `4` |
| `activity_kind` | body | mixed | 否 | 活动类型 0:专属招商 1:公开招商 | `1` |
| `min_promotion_days` | body | mixed | 否 | 最短推广周期，不传默认90天（目前只能支持以下天数：30，90，180，360） | `0` |
| `threshold_cross_border` | body | mixed | 否 | 跨境店铺是否可以报名，不传表示可报名 | `0` |
| `min_exclusion_duration` | body | mixed | 否 | 团长活动侧设置的限时独家期限 0-6个月，不传默认为 0 | `1` |
| `ad_commission_rate` | body | string | 否 | 最低双佣金投放期商品佣金率 | `10` |
| `ad_service_rate` | body | string | 否 | 最低双佣金投放期团长服务费率 | `10` |
| `cos_limit_type` | body | mixed | 否 | 佣金限制类型 1:不限制 2:仅双佣金 3:仅固定佣金 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/colonelActivityCreateOrUpdate?app_key=your_appkey_here&method=alliance.colonelActivityCreateOrUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `institution_id` | mixed | 机构ID | `111` |
| `activity_id` | mixed | 活动ID | `111` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 机构结算账户不存在或部分开通，需要全部开通（sub_code: isv.business-failed:4136） | 机构结算账户不存在或部分开通，需要全部开通 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 暂时不支持创建公开招商（sub_code: isv.business-failed:100） | 暂时不支持创建公开招商 |
| `40004` | 非法的参数 / 推广结束时间必须大于报名结束时间（sub_code: isv.parameter-invalid:4131） | 推广结束时间必须大于报名结束时间 |
| `50002` | 业务处理失败 / 活动的推广开始时间不能早于今天（sub_code: isv.business-failed:10000） | 活动的推广开始时间不能早于今天 |
| `50002` | 业务处理失败 / 只能修改自己创建的团长活动（sub_code: isv.business-failed:110110） | 只能修改自己创建的团长活动，请检查 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 报名截止时间应不早于今天（sub_code: isv.business-failed:500） | 报名截止时间应不早于今天 |
| `40004` | 非法的参数 / 活动信息填写不规范，请重新填写（sub_code: isv.parameter-invalid:71100） | 活动信息填写不规范，请重新填写 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_id": "111",
    "institution_id": "111"
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
  "sub_code": "isv.business-failed:4136",
  "sub_msg": "机构结算账户不存在或部分开通，需要全部开通"
}
```

## 备注
