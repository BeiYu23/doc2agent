# 玩法优惠信息创建或修改前的预校验能力

> marketing.activityPreCheck — 玩法优惠信息创建或修改前的预校验能力

| 元信息 | 值 |
| --- | --- |
| 中文名 | 玩法优惠信息创建或修改前的预校验能力 |
| 文档地址 | `/docs/doudian/marketing/marketing-marketing-activityPreCheck` |
| 接口 ID | `doudian.marketing.marketing.activityPreCheck` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/activityPreCheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7774 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity` | body | object | 否 | 活动信息信息 | `` |
| `  └ activity_info` | body | object | 是 | 玩法基本信息 | `` |
| `    └ activity_id` | body | number | 否 | 活动Id。创建时填0，编辑时填活动ID。 | `7543564853458698506` |
| `    └ activity_name` | body | string | 是 | 活动名称 | `限时抢购 20250806 15:45` |
| `    └ activity_code` | body | string | 是 | 玩法编码。LimitTimeTimeBuy: 限时抢购; LimitQuantityTimeBuy: 限量抢购; OrdinaryTimeBuy: 普通降价促销。 | `LimitTimeTimeBuy` |
| `    └ create_time` | body | number | 否 | 创建时间。必填 | `1749744000` |
| `    └ update_time` | body | number | 否 | 更新时间。必填 | `1749744000` |
| `    └ status` | body | string | 否 | 玩法状态。固定传 1。 | `1` |
| `  └ activity_time` | body | object | 是 | 玩法周期信息 | `` |
| `    └ start_time` | body | number | 是 | 开始时间时间 | `1749744000` |
| `    └ end_time` | body | number | 是 | 结束时间 | `1749744000` |
| `    └ warm_up_time` | body | number | 否 | 预热时间 | `1749744000` |
| `  └ activity_common_config` | body | object | 是 | 玩法通用配置 | `` |
| `    └ rule_scope` | body | object | 是 | 优惠规则作用范围 | `` |
| `      └ rule_scope_type` | body | string | 是 | 优惠规则作用类型。当前仅支持传 3，代表 sku 维度。 | `3` |
| `    └ source_type` | body | string | 否 | 来源类型。传固定值 10，代表开放平台 | `10` |
| `    └ source_page` | body | string | 否 | 创建来源页。传固定值 300，代表isv页面 | `300` |
| `  └ activity_rule` | body | object | 否 | 玩法规则信息 | `` |
| `    └ campaign_resource` | body | object | 否 | 活动资源规则 | `` |
| `      └ user_limit` | body | object | 否 | 用户限购规则 | `` |
| `        └ trade_limit` | body | object | 否 | 交易限购规则 | `` |
| `          └ trade_limit_type` | body | string | 否 | 限购类型。固定传1，代表sku维度限购 | `1` |
| `      └ campaign_limit` | body | object | 否 | 活动限量规则 | `` |
| `        └ promotion_limit` | body | object | 否 | 营销限用规则 | `` |
| `          └ limit_type` | body | string | 否 | 限用类型。固定传 14，代表商品维度限用 | `14` |
| `        └ activity_stock` | body | object | 否 | 活动库存规则 | `` |
| `          └ stock_type` | body | string | 否 | 库存类型。固定传1，代表商品维度库存。 | `1` |
| `    └ discount_rule` | body | array | 否 | 优惠规则 | `` |
| `      └ discount_info` | body | object | 否 | 优惠信息 | `` |
| `        └ activity_price_discount` | body | object | 否 | 价格类优惠 | `` |
| `          └ discount_value` | body | number | 否 | 优惠值。默认填充0 | `0` |
| `          └ discount_type` | body | string | 否 | 优惠方式。1: 打折; 2: 一口价; 3: 直降 | `2` |
| `      └ fund_share` | body | object | 否 | 出资信息 | `` |
| `        └ fund_share_info_list` | body | array | 否 | 出资信息 | `` |
| `          └ fund_id` | body | string | 否 | 出资方ID。固定传值：v1:2 | `v1:2` |
| `          └ share_ratio` | body | number | 否 | 分摊比例。店铺单品直降传 100 | `100` |
| `          └ denominator` | body | number | 否 | 分摊分母 | `100` |
| `          └ fund_type` | body | string | 否 | 出资角色。1: 平台; 2: 店铺; 3: 达人;4: 供应商。单品直降场景传 2 | `2` |
| `          └ share_way` | body | string | 否 | 平摊方式。固定传1，代表比例出资。 | `1` |
| `    └ scene_rule` | body | object | 否 | 场景规则 | `` |
| `      └ need_live` | body | boolean | 否 | 是否直播间生效。固定传 false，代表活动期间均生效 | `false` |
| `  └ activity_products` | body | array | 否 | 玩法商品信息 | `` |
| `    └ activity_sku_list` | body | array | 否 | 活动SKU信息 | `` |
| `      └ sku_info` | body | object | 否 | SKU基本信息 | `` |
| `        └ activity_fixed_price` | body | number | 否 | sku活动一口价。需要调用方根据优惠设置做计算，单位分 | `600` |
| `        └ sku_id` | body | string | 否 | skuId | `1774276049399816` |
| `        └ origin_price` | body | number | 否 | sku价格 | `800` |
| `      └ activity_rule` | body | object | 否 | 活动优惠规则 | `` |
| `        └ discount_rule` | body | array | 否 | 优惠规则 | `` |
| `          └ discount_threshold` | body | object | 否 | 优惠门槛 | `` |
| `            └ threshold_value` | body | number | 否 | 门槛值。固定传0 | `0` |
| `            └ threshold_type` | body | string | 否 | 优惠门槛类型。固定传 2,2 代表满元。 | `2` |
| `          └ discount_info` | body | object | 否 | 优惠信息 | `` |
| `            └ activity_price_discount` | body | object | 否 | 价格类优惠 | `` |
| `              └ discount_value` | body | number | 否 | 优惠值。一口价和直降代表面额，单位分；打折代表百分之多少 | `20` |
| `              └ discount_type` | body | string | 否 | 优惠方式。1: 打折; 2: 一口价; 3: 直降 | `2` |
| `        └ campaign_resource` | body | object | 否 | 活动资源规则 | `` |
| `          └ user_limit` | body | object | 否 | 用户限购规则 | `` |
| `            └ trade_limit` | body | object | 否 | 交易限购规则 | `` |
| `              └ user_limit` | body | number | 否 | 用户限购值 | `2` |
| `              └ trade_limit_type` | body | string | 否 | 限购类型。固定传1，代表sku维度限购 | `1` |
| `    └ product_info` | body | object | 否 | 商品信息 | `` |
| `      └ channel_type` | body | number | 否 | 渠道类型。固定传0 | `0` |
| `      └ product_id` | body | string | 否 | 商品ID | `3633954572898306915` |
| `      └ channel_id` | body | string | 否 | 渠道ID。固定传 0。 | `0` |
| `      └ name` | body | string | 否 | 商品名 | `多sku半身裙01-20 21:47` |
| `      └ cover` | body | string | 否 | 主图链接 | `https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_6fa7399f9514ce5978e1451cc6e952a0_sx_69234_www800-800` |
| `    └ activity_rule` | body | object | 否 | 活动规则 | `` |
| `      └ campaign_resource` | body | object | 否 | 活动资源规则 | `` |
| `        └ campaign_limit` | body | object | 否 | 活动限量规则 | `` |
| `          └ promotion_limit` | body | object | 否 | 营销限用规则 | `` |
| `            └ limit_type` | body | string | 否 | 限用类型。固定传 14，代表商品维度限用 | `14` |
| `            └ limit_num` | body | number | 否 | 限用数 | `2` |
| `  └ activity_extra_info` | body | object | 否 | 玩法扩展信息 | `` |
| `    └ time_buy_extra` | body | object | 否 | 限时限量购扩展信息 | `` |
| `      └ order_expire_time` | body | number | 否 | 订单过期时间。仅支持传入 1800，代表 30 分钟 | `1800` |
| `      └ set_promotion_limit` | body | boolean | 否 | 是否设置营销限用 | `true` |
| `common_ctx_info` | body | object | 否 | 上下文信息 | `` |
| `  └ isv_info` | body | object | 否 | 第三方应用信息 | `` |
| `  └ shop_info` | body | object | 否 | 店铺信息 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `check_res` | object | 校验结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:510000001） | 调整参数 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:510050002） | 联系技术排查 |

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
  "sub_code": "isv.parameter-invalid:510000001",
  "sub_msg": "非法参数"
}
```

## 备注
