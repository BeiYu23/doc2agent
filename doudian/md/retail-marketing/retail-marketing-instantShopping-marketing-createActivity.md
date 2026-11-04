# instantShopping.marketing.createActivity

> 创建活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.createActivity` |
| 中文名 | 创建活动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6385 |
| 更新日期 | `2024-05-11` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity` | body | object | 是 | 活动信息 | `` |
| `  └ activity_title` | body | string | 是 | 活动标题，最大25字符 | `测试活动标题` |
| `  └ activity_type` | body | string | 是 | 活动类型，10：限时限量购，20：店铺券； 30：商品券 | `10` |
| `  └ activity_sub_type` | body | string | 是 | 活动子类型， 101限时秒杀，102，普通降价促销 | `101` |
| `  └ activity_base_info` | body | object | 否 | 活动规则 | `` |
| `    └ limit_activity_stock` | body | string | 是 | 是否限制活动库存，0：不限活动库存；1：限活动库存 | `1` |
| `    └ activity_start_time` | body | number | 是 | 活动开始时间，秒 | `1711265959` |
| `    └ activity_end_time` | body | number | 是 | 活动结束时间，秒 | `1711266959` |
| `    └ order_cancel_time` | body | number | 是 | 订单取消时间，秒 | `300` |
| `    └ activity_stock_sold_setting` | body | string | 是 | 活动库存售罄策略，0：恢复为原价继续售卖；1：停止售卖，商品标示“已抢光” | `1` |
| `    └ warm_up` | body | boolean | 是 | 是否预热，目前仅支持不预热 | `false` |
| `  └ coupon_base_info` | body | object | 否 | 券规则 | `` |
| `    └ credit` | body | number | 是 | 优惠金额，分 | `100` |
| `    └ threshold` | body | number | 否 | 门槛，满减券专属 | `500` |
| `    └ discount` | body | number | 否 | 折扣，打折券专属 | `9.8` |
| `    └ activity_start_time` | body | number | 是 | 领取开始时间 | `1711265959` |
| `    └ activity_end_time` | body | number | 是 | 领取结束时间 | `1711266959` |
| `    └ apply_way` | body | string | 是 | 有效开始时间类型，1：领取后xx日-xx日有效， 2：领取后x天内有效 | `1` |
| `    └ apply_start_time` | body | number | 否 | 使用开始时间，秒 | `1711265959` |
| `    └ apply_end_time` | body | number | 否 | 使用结束时间，秒 | `1711266959` |
| `    └ valid_period` | body | number | 否 | 有效期，天 | `7` |
| `    └ total_amount` | body | number | 是 | 券发放量 | `100` |
| `    └ max_apply_times` | body | number | 是 | 每人最多可领取次数 | `1` |
| `request_id` | body | string | 是 | 幂等ID，长度最大100个字符 | `1111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comcrossborder/msg/push?app_key=your_appkey_here&method=crossborder.msg.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
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
