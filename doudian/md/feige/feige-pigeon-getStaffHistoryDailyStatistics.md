# pigeon.getStaffHistoryDailyStatistics

> 查询客服每日指标结果值

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.getStaffHistoryDailyStatistics` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/getStaffHistoryDailyStatistics` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5345 |
| 更新日期 | `2024-07-17` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `date` | body | string | 是 | 查询日期。4天内同一日期的数据不是稳定的，可能会有更新。 | `20231022` |
| `staff_ids` | body | array | 否 | 客服id | `[11,22]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/getStaffHistoryDailyStatistics?app_key=your_appkey_here&method=pigeon.getStaffHistoryDailyStatistics&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `staff_dailystatistics` | array | 结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2） | 请按报错提示检查入参 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:3） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "staff_dailystatistics": [
      {
        "cpd_online_duration": "60",
        "day_time": "20231010",
        "inquiry_amount": "1",
        "labor_amount": "2",
        "labor_user_amount": "1",
        "nap_dur1d": "7",
        "offline_dur1d": "8",
        "online_dur1d": "6",
        "place_amount": "1",
        "purchase_serv_converse_rate": "1.3",
        "purchasers_amount": "1",
        "s8e23h_expt_wel_fst_reply_conv_cnt_td": "10",
        "s8e23h_expt_wel_fst_reply_round_dur_td": "1",
        "sales_amount": "1",
        "satisfied_rate": "1.3",
        "serv_ucnt_1d": "10",
        "staff_id": "22342",
        "stars_1_num": "1",
        "stars_2_num": "1",
        "stars_3_num": "1",
        "stars_4_num": "1",
        "stars_5_num": "1",
        "user_query_amount": "1",
        "user_wait_amount": "1",
        "user_wait_duration_amount": "1",
        "work_time_cmnt_num_td": "1",
        "work_time_expt_wel_first_reply_conv_cnt1d": "1",
        "work_time_expt_wel_first_reply_conv_rate1d": "1.3",
        "work_time_expt_wel_first_reply_round_dur_td": "1",
        "work_time_in120s_reply_round_cnt_td": "1",
        "work_time_in180s_reply_conv_cnt1d": "1",
        "work_time_in180s_reply_conv_rate1d": "1.3",
        "work_time_in180s_reply_round_cnt_td": "1",
        "work_time_in180s_reply_round_rate_td": "1.3",
        "work_time_in30s_reply_round_cnt_td": "1",
        "work_time_in60s_reply_round_cnt_td": "1",
        "work_time_in_abnormal_conv_cnt1d": "1",
        "work_time_invite_cmnt_num_td": "1",
        "work_time_serv_conv_cnt1d": "1",
        "work_time_with_ask_serv_conv_cnt1d": "10"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "参数错误"
}
```

## 备注
