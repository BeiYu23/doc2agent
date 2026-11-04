# 抖客获取近30天内奖励订单

> buyin.doukeRewardOrders — 抖客获取近30天内奖励订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 抖客获取近30天内奖励订单 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-doukeRewardOrders` |
| 接口 ID | `doudian.alliance.buyin.doukeRewardOrders` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/doukeRewardOrders` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/3200 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 页数，从1开始； | `1` |
| `page_size` | body | mixed | 是 | 每页订单数目，最大为100 | `10` |
| `pid` | body | string | 否 | 独立抖客PID | `dy_123_445_4995` |
| `start_date` | body | string | 否 | 查询开始日期，格式：20230308，奖励订单只保存近30天的订单 | `20230308` |
| `end_date` | body | string | 否 | 查询结束日期，格式：20230308，奖励订单只保存近30天的订单 | `20230308` |
| `distribution_type` | body | mixed | 否 | 默认全部，0:全部 1:商品分销 2: 直播间分销 3: mix自建活动页分销 4:频道页分销 99:其他 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/doukeRewardOrders?app_key=your_appkey_here&method=buyin.doukeRewardOrders&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `reward_orders` | array | 奖励订单信息 | `` |
| `total` | mixed | 查询的奖励订单总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 分销类型参数错误（sub_code: isv.parameter-invalid:4414） | 分销类型参数错误 |
| `40004` | 非法的参数 / 参数校验失败：无效pageSize（sub_code: isv.parameter-invalid:4415） | 参数校验失败：无效pageSize |
| `40004` | 非法的参数 / 参数校验失败：无效时间区间（开始时间不能大于结束时间）（sub_code: isv.parameter-invalid:4416） | 参数校验失败：无效时间区间（开始时间不能大于结束时间） |
| `40004` | 非法的参数 / 参数校验失败：无效 PID（sub_code: isv.parameter-invalid:4102） | 参数校验失败：无效 PID |
| `40004` | 非法的参数 / 参数校验失败：无效开始时间（sub_code: isv.parameter-invalid:4249） | 参数校验失败：无效开始时间 |
| `40004` | 非法的参数 / 参数校验失败：无效结束时间（sub_code: isv.parameter-invalid:4250） | 参数校验失败：无效结束时间 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "reward_orders": [
      {
        "external_info": "test",
        "pay_amount": "100",
        "pay_date": "20230308",
        "product_id": "12345678",
        "product_name": "测试商品",
        "promotion_info": "dy_123_445_4995",
        "reward_order_id": "12345678",
        "reward_type": "拉新"
      }
    ],
    "total": "100"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4414",
  "sub_msg": "分销类型参数错误"
}
```

## 备注
