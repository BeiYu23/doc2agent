# marketing.createActivity

> 创建营销玩法

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.marketing.marketing.createActivity` |
| 中文名 | 创建营销玩法 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/createActivity` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7779 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity` | body | object | 否 | 玩法数据 | `` |
| `  └ activity_info` | body | object | 否 | 玩法基本信息 | `` |
| `    └ create_time` | body | number | 否 | 创建时间。必填 | `1749744000` |
| `    └ update_time` | body | number | 否 | 更新时间。必填 | `1749744000` |
| `    └ activity_id` | body | number | 否 | 活动Id。创建时填0，编辑时填活动ID。 | `7543564853458698506` |
| `    └ status` | body | string | 否 | 玩法状态。固定传 1。 | `1` |
| `    └ activity_name` | body | string | 否 | 活动名称 | `限时抢购 20250806 15:45` |
| `    └ activity_code` | body | string | 否 | 玩法编码。LimitTimeTimeBuy: 限时抢购; LimitQuantityTimeBuy: 限量抢购; OrdinaryTimeBuy: 普通降价促销。 | `LimitTimeTimeBuy` |
| `  └ activity_time` | body | object | 否 | 玩法周期信息 | `` |
| `    └ start_time` | body | number | 否 | 开始时间/领取开始时间 | `1749744000` |
| `    └ end_time` | body | number | 否 | 结束时间/领取结束时间 | `1756655999` |
| `    └ warm_up_time` | body | number | 否 | 预热时间。需要和开始时间保持一致 | `1749744000` |
| `  └ activity_common_config` | body | object | 否 | 玩法通用配置 | `` |
| `    └ rule_scope` | body | object | 否 | 优惠规则作用范围 | `` |
| `      └ rule_scope_type` | body | string | 否 | 优惠规则作用类型。当前仅支持传 3，代表 sku 维度。 | `3` |
| `    └ source_page` | body | string | 否 | 创建来源页。当前仅支持 新建页(51)、复制页(52) | `52` |
| `  └ activity_rule` | body | object | 否 | 玩法规则信息 | `` |
| `    └ discount_rule` | body | array | 否 | 优惠规则 | `` |
| `      └ discount_info` | body | object | 否 | 优惠信息 | `` |
| `        └ activity_price_discount` | body | object | 否 | 价格类优惠 | `` |
| `          └ discount_value` | body | number | 否 | 优惠值。默认填充0 | `0` |
| `          └ discount_type` | body | string | 否 | 优惠方式。1: 打折; 2: 一口价; 3: 直降 | `2` |
| `      └ fund_share` | body | object | 否 | 出资信息 | `` |
| `        └ fund_share_info_list` | body | array | 否 | 出资信息 | `` |
| `          └ denominator` | body | number | 否 | 分摊分母。固定传值 100 | `100` |
| `          └ fund_id` | body | string | 否 | 出资方ID。固定传值：v1:2 | `v1:2` |
| `          └ share_way` | body | string | 否 | 平摊方式。固定传1，代表比例出资。 | `1` |
| `          └ fund_type` | body | string | 否 | 出资角色。1: 平台; 2: 店铺; 3: 达人;4: 供应商。单品直降场景传 2 | `2` |
| `          └ share_ratio` | body | number | 否 | 分摊比例。店铺单品直降传 100 | `100` |
| `    └ campaign_resource` | body | object | 否 | 活动资源规则 | `` |
| `      └ campaign_limit` | body | object | 否 | 活动限量规则 | `` |
| `        └ promotion_limit` | body | object | 否 | 营销限用规则 | `` |
| `          └ limit_type` | body | string | 否 | 限用类型。固定传 14，代表商品维度限用 | `14` |
| `        └ activity_stock` | body | object | 否 | 活动库存规则 | `` |
| `          └ stock_type` | body | string | 否 | 库存类型。固定传1，代表商品维度库存。 | `1` |
| `      └ user_limit` | body | object | 否 | 用户限购规则 | `` |
| `        └ trade_limit` | body | object | 否 | 交易限购规则 | `` |
| `          └ trade_limit_type` | body | string | 否 | 限购类型。固定传1，代表sku维度限购 | `1` |
| `    └ scene_rule` | body | object | 否 | 场景规则 | `` |
| `      └ need_live` | body | boolean | 否 | 是否直播间生效。固定传 false，代表活动期间均生效 | `false` |
| `  └ activity_products` | body | array | 否 | 玩法商品信息 | `` |
| `    └ activity_rule` | body | object | 否 | 活动优惠规则 | `` |
| `      └ campaign_resource` | body | object | 否 | 活动资源规则 | `` |
| `        └ campaign_limit` | body | object | 否 | 活动限量规则 | `` |
| `          └ promotion_limit` | body | object | 否 | 营销限用规则 | `` |
| `            └ limit_num` | body | number | 否 | 限用值 | `2` |
| `            └ limit_type` | body | string | 否 | 限用类型。固定传 14，代表商品维度限用 | `14` |
| `    └ product_info` | body | object | 否 | 商品信息 | `` |
| `      └ cover` | body | string | 否 | 商品链接 | `https://tosv.boe.byted.org/obj/ecom-shop-material/ayoJLG_m_6fa7399f9514ce5978e1451cc6e952a0_sx_69234_www800-800` |
| `      └ name` | body | string | 否 | 商品名 | `多sku半身裙01-20 21:47` |
| `      └ product_id` | body | string | 否 | 商品ID | `3633954572898306915` |
| `      └ channel_id` | body | string | 否 | 渠道ID。固定传 0。 | `0` |
| `      └ channel_type` | body | number | 否 | 渠道类型。固定传0 | `0` |
| `    └ activity_sku_list` | body | array | 否 | 活动SKU信息 | `` |
| `      └ sku_info` | body | object | 否 | SKU基本信息 | `` |
| `        └ sku_id` | body | string | 否 | skuId | `1774276049399816` |
| `        └ origin_price` | body | number | 否 | sku价格 | `800` |
| `        └ activity_fixed_price` | body | number | 否 | sku活动一口价。需要调用方根据优惠设置做计算，单位分 | `600` |
| `      └ activity_rule` | body | object | 否 | 活动优惠规则 | `` |
| `        └ discount_rule` | body | array | 否 | 优惠规则 | `` |
| `          └ discount_threshold` | body | object | 否 | 优惠门槛 | `` |
| `            └ threshold_value` | body | number | 否 | 门槛值。固定传0 | `0` |
| `            └ threshold_type` | body | string | 否 | 优惠门槛类型。固定传 2,2 代表满元。 | `2` |
| `          └ discount_info` | body | object | 否 | 优惠信息 | `` |
| `            └ activity_price_discount` | body | object | 否 | 价格类优惠 | `` |
| `              └ discount_type` | body | string | 否 | 优惠方式。1: 打折; 2: 一口价; 3: 直降 | `2` |
| `              └ discount_value` | body | number | 否 | 优惠值。一口价和直降代表面额，单位分；打折代表百分之多少 | `20` |
| `        └ campaign_resource` | body | object | 否 | 活动资源规则 | `` |
| `          └ user_limit` | body | object | 否 | 用户限购规则 | `` |
| `            └ trade_limit` | body | object | 否 | 交易限购规则(缺 类型+值) | `` |
| `              └ user_limit` | body | number | 否 | 用户限购值 | `12` |
| `              └ trade_limit_type` | body | string | 否 | 限购类型。固定传1，代表sku维度限购 | `1` |
| `  └ activity_extra_info` | body | object | 否 | 玩法扩展信息 | `` |
| `    └ time_buy_extra` | body | object | 否 | 限时限量购扩展信息 | `` |
| `      └ set_promotion_limit` | body | boolean | 否 | 是否设置营销限用 | `true` |
| `      └ order_expire_time` | body | number | 否 | 订单过期时间。仅支持传入 1800，代表 30 分钟 | `1800` |
| `common_ctx_info` | body | object | 否 | 上下文信息 | `` |
| `  └ isv_info` | body | object | 否 | isv信息 | `` |
| `    └ app_name` | body | string | 否 | ISV应用名称 | `ISV应用名称` |
| `    └ app_key` | body | number | 否 | isv应用id | `isv应用id` |
| `  └ shop_info` | body | object | 否 | 店铺信息 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getCatePropertyV2?app_key=your_appkey_here&method=product.getCatePropertyV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_id` | number | 玩法活动id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:510050002） | 1 |
| `50002` | 业务处理失败 / 开放平台仅支持商品维度限量（sub_code: isv.business-failed:-100001） | 修改入参 |
| `50002` | 业务处理失败 / 该类活动不支持设置活动限量信息（sub_code: isv.business-failed:510020006） | 修改入参 |
| `50002` | 业务处理失败 / 操作过于频繁（sub_code: isv.business-failed:510020003） | 请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "category_id": "31918",
        "cid": "31918",
        "diy_type": "1",
        "has_sub_property": "false",
        "important_type": "1",
        "measure_templates": [
          {
            "display_name": "xx模版",
            "template_id": "23",
            "value_modules": [
              {
                "input_type": "input",
                "module_id": "123",
                "prefix": "\"\"",
                "suffix": "\"\"",
                "units": [
                  {
                    "unit_id": "1",
                    "unit_name": "克"
                  }
                ],
                "validate_rule": {
                  "data_type": "integer",
                  "max": "10",
                  "min": "2",
                  "precision": "2",
                  "time_format": "YYYY-MM-DD",
                  "unit_rules": [
                    {
                      "max": "10",
                      "min": "2",
                      "unit_id": "1"
                    }
                  ]
                },
                "value_required": "true",
                "values": [
                  {
                    "value_name": "棉"
                  }
                ]
              }
            ]
          }
        ],
        "multi_select_max": "5",
        "options": [
          {
            "name": "ON:THE BODY/安宝笛",
            "sequence": "2",
            "value": "1062254699",
            "value_id": "1"
          }
        ],
        "property_id": "14133",
        "property_name": "\"材质\"",
        "property_type": "1",
        "relation_id": "1",
        "required": "0",
        "sequence": "2",
        "status": "1",
        "type": "text"
      }
    ],
    "tpl_type": "2"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:510050002",
  "sub_msg": "系统异常"
}
```

## 备注
