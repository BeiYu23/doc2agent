# pigeon.getShopHistoryDailyStatistics

> 查询店铺维度统计数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.getShopHistoryDailyStatistics` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/getShopHistoryDailyStatistics` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5346 |
| 更新日期 | `2023-11-28` |

## 接口说明

- 文档书: 飞鸽API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `date` | body | string | 是 | 近4天的数据是会动态更新的，所以建议每天拉取近4天的数据 | `20231024` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/getShopHistoryDailyStatistics?app_key=your_appkey_here&method=pigeon.getShopHistoryDailyStatistics&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_history_statistics` | object | 结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误，请检查入参（sub_code: isv.parameter-invalid:2） | 参数错误，请检查入参 |
| `20000` | 系统错误 / 数据查询失败，请稍后重试（sub_code: isp.service-error:3） | 数据查询失败，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "shop_history_statistics": {
      "alarm_conv_cnt": "1",
      "avg_first_response_duration": "1",
      "avg_queuing_duration": "1",
      "avg_response_duration": "1",
      "consult_amount": "1",
      "cpd_online_duration": "1",
      "first_response_con_amount": "1",
      "first_response_duration_amount": "1",
      "labor_amount": "1",
      "labor_user_amount": "1",
      "leave_msg_cnt": "1",
      "non_repeat_conv_rate": "0.7568",
      "non_reply_rate": "0.7568",
      "pick_up_rate": "0.7568",
      "stars1_num": "1",
      "stars2_num": "1",
      "stars3_num": "1",
      "stars4_num": "1",
      "stars5_num": "1",
      "switch_to_labor_amount": "1",
      "three_min_response_con_amount": "1",
      "three_min_response_con_rate": "0.7568",
      "three_min_response_rate": "0.7568",
      "total_queuing_duration": "1",
      "user_wait_amount": "1",
      "user_wait_duration_amount": "1",
      "work_order_cnt": "1",
      "work_order_rate": "0.7568",
      "work_time_labor_amount": "1",
      "work_time_labor_first_response_duration": "1",
      "work_time_labor_first_response_num": "1",
      "work_time_switch_to_labor_amount": "1",
      "work_time_three_min_response_amount": "1",
      "work_time_two_min_first_resp_con_amount": "1",
      "work_time_user_send_amount": "1"
    }
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
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "参数错误，请检查入参"
}
```

## 备注
