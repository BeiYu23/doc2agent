# pigeon.historyConversationList

> 飞鸽历史会话列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.historyConversationList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/historyConversationList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5342 |
| 更新日期 | `2024-02-22` |

## 接口说明

- 文档书: 飞鸽API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | mixed | 是 | 页数，从1开始 | `1` |
| `page_size` | body | mixed | 是 | pageSize，单次最多1000条 | `100` |
| `convention_id_list` | body | array | 否 | ["1","2"] | `会话id` |
| `end_time_start` | body | mixed | 是 | 查询end_time_start-end_time_end期间结束的会话  注意：部分指标数据非T+1稳定，所以每天会更新近三天的数据。举例：会话A在10.29号结束，用户在10.30号评价了该会话，那么10.31号的时候1029日期的会话数据也会有更新。 | `1700064000` |
| `end_time_end` | body | mixed | 是 | 查询end_time_start-end_time_end期间结束的会话 | `1700064000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/historyConversationList?app_key=your_appkey_here&method=pigeon.historyConversationList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `convention_details` | array | 会话列表 | `` |
| `count` | mixed | 总记录条数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:1000） | 请检查入参 |
| `50002` | 业务处理失败 / 数据查询失败，请稍后重试（sub_code: isv.business-failed:2000） | 数据查询失败，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "convention_details": [
      {
        "alarm_list": "1",
        "avg_response_duration": "1",
        "comment_type": "-1：未评价；0：用户主动评价；1：客服邀请评价；2：系统自动邀请评价",
        "conv_id": "7290506587424019",
        "convcmnt_stars": "1",
        "conversation_type": "0",
        "cs_id_list": "1",
        "doudian_open_id": "7290506587424019",
        "end_scene": "1",
        "end_time": "1",
        "evaluate_time": "1",
        "evaluation_labels": "[\"态度恶劣\"]",
        "first_response_duration": "1",
        "inquiry_type": "1",
        "labor_session_duration": "10",
        "labor_time": "1",
        "queuing_duration": "1",
        "robot_reception_time": "1",
        "sales_amount": "1",
        "session_type": "1",
        "staff_id": "7290506587424019",
        "start_scene": "1",
        "start_time": "1",
        "switch2_labor_time": "1",
        "switch_comment_infos": [
          {
            "comment_stars": "5",
            "comment_time": "2024/01/08 15:01:51",
            "comment_type": "-1：未评价；0：用户主动评价；1：客服邀请评价；2：系统自动邀请评价",
            "evaluation_labels": "[\"态度恶劣\"，\"回复慢\"]",
            "staff_id": "7290506587424019"
          }
        ],
        "user_nick": "陌**"
      }
    ],
    "count": "10"
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
  "sub_code": "isv.business-failed:1000",
  "sub_msg": "参数错误"
}
```

## 备注
