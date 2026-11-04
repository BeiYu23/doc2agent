# instantShopping.marketing.createLiveMainProductCoupon

> 创建直播主品券

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.createLiveMainProductCoupon` |
| 中文名 | 创建直播主品券 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/7250 |
| 更新日期 | `2025-02-10` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.08）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity` | body | object | 是 | 券信息 | `` |
| `  └ coupon_base_info` | body | object | 是 | 券基础信息 | `` |
| `    └ apply_end_time` | body | number | 否 | 使用结束时间（apply_way使用方式=限制日期范围） 使用区间不长于365天 | `1738166399` |
| `    └ valid_period` | body | number | 否 | 使用天数(apply_way使用方式=限制天数) 单位是秒，范围在1s-180天内（需要是86400的倍数） | `172800` |
| `    └ activity_start_time` | body | number | 是 | 领取开始时间 | `1737561600` |
| `    └ activity_end_time` | body | number | 是 | 领取结束时间 | `1738166399` |
| `    └ total_amount` | body | number | 是 | 券发放量 数值范围1-100W | `20` |
| `    └ apply_way` | body | string | 是 | 使用方式 （限制天数-1，限制日期范围-2） | `1` |
| `    └ discount` | body | number | 否 | 折扣比例（折扣百分比） 打折券专属 例如9折，discount=90 （折扣需在1-9折） | `10` |
| `    └ biz_type` | body | number | 是 | 券业务类型（直播主品券=2） | `2` |
| `    └ max_apply_times` | body | number | 是 | 每人最多可领取次数 数值范围1-30 | `10` |
| `    └ apply_start_time` | body | number | 否 | 使用开始时间（apply_way使用方式=限制日期范围） 注意：1. 券使用时间需在365天以内 2. 使用的开始时间不可早于领取的开始时间 | `1737561600` |
| `    └ credit` | body | number | 否 | 优惠金额（单位为分） 例如9元，credit=900 直减券/满减券 （直减金额需在1-3000元的整数；满减优惠金额需在1-99999元的整数，满减券优惠金额必须大于等于券门槛的1%，满减券门槛必须大于券优惠金额） | `900` |
| `    └ threshold` | body | number | 否 | 优惠门槛金额（单位为分）满减券专属 例如9元，credit=900 （门槛金额需在1-99999元的整数） | `1000` |
| `  └ activity_title` | body | string | 是 | 活动名称，最长25个字符 | `活动A` |
| `  └ activity_type` | body | string | 是 | 活动类型（商品券=30） | `30` |
| `  └ activity_sub_type` | body | string | 是 | 活动子类型 301-直减券，302-满减券，303-折扣券 | `301` |
| `request_id` | body | string | 是 | 幂等id，长度最大100个字符 | `xxxx1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/waybillApply?app_key=your_appkey_here&method=logistics.waybillApply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_id` | string | 活动id | `1111` |

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
  "data": {
    "err_infos": [
      {
        "err_code": "1",
        "err_msg": "1",
        "order_id": "1",
        "track_no": "1"
      }
    ],
    "waybill_infos": [
      {
        "order_id": "1",
        "print_data": "1",
        "sign": "1",
        "track_no": "1"
      }
    ]
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
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
