# trade.UpdateTradeLimitTemplate

> 更新限售模版

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.trade.UpdateTradeLimitTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/UpdateTradeLimitTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2707 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trade_limit_template_id` | body | mixed | 是 | 限购模板ID | `7124521073370071303` |
| `trade_limit_rule_request_list` | body | array | 是 | 限购参数 | `` |
| `  └ trade_limit_model` | body | mixed | 是 | 限购模型 1-重量，2-数量，3-地区，4-金额 | `2` |
| `  └ trade_limit_resource` | body | mixed | 是 | 限购资源类别1-抖店，2-门店，3-商品ID，4-sku,5-类目，6-活动，7-商品标 | `1` |
| `  └ trade_limit_resource_object` | body | object | 否 | 限购资源值 | `` |
| `    └ trade_limit_resource_id_list` | body | array | 否 | 限购资源值列表 | `["1"]` |
| `  └ trade_limit_pattern` | body | object | 是 | 限购值，模型为重量则单位为毫克，模型为金额则单位为分 | `` |
| `    └ minimum` | body | mixed | 是 | 单次下限 | `1` |
| `    └ maximum` | body | mixed | 是 | 单次上限 | `5` |
| `    └ cumulative_max` | body | mixed | 是 | 累计限购值 | `10` |
| `  └ time_period` | body | object | 否 | 限购时间 | `` |
| `    └ time_period_pattern` | body | mixed | 是 | 限购时间类型 | `1` |
| `    └ time_period_fixed` | body | object | 否 | 限购时间滑动窗口 | `` |
| `      └ start_time` | body | mixed | 是 | 开始时间 | `1655991571` |
| `      └ end_time` | body | mixed | 是 | 结束时间 | `1655991571` |
| `  └ trade_limit_subject_lisit` | body | array | 是 | 限购维度1 // 端用户（比如uid=122，aid=1128） 2 // 用户组用户（比如uid=122，group=aweme） 3 // 设备 4 // 下单电话 5 // 收件电话 6 // 身份证号 7 // 支付账号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trade/UpdateTradeLimitTemplate?app_key=your_appkey_here&method=trade.UpdateTradeLimitTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `trade_limit_template_id` | mixed | 限购模板ID | `7124521073370071303` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 数组越界异常（sub_code: isv.business-failed:20001） | 模版更新时需要选择限购纬度 |

## 响应示例

成功：

```json
{
  "data": {
    "trade_limit_template_id": "7124521073370071303"
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
  "sub_code": "isv.business-failed:20001",
  "sub_msg": "数组越界异常"
}
```

## 备注
