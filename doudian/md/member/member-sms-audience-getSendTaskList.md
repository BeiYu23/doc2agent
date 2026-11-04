# sms.audience.getSendTaskList

> 按人群包发送短信任务列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.audience.getSendTaskList` |
| 中文名 | 按人群包发送短信任务列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/getSendTaskList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6752 |
| 更新日期 | `2026-05-26` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `create_time_start` | body | mixed | 否 | 创建时间开始 | `创建时间开始` |
| `create_time_end` | body | mixed | 否 | 创建时间结束 | `创建时间结束` |
| `status` | body | mixed | 否 | 状态 | `状态` |
| `page_size` | body | mixed | 是 | pageSize,不大于100 | `pageSize` |
| `page_no` | body | mixed | 是 | pageNo,从1开始 | `pageNo` |
| `task_id` | body | mixed | 否 | 任务id | `1231` |
| `biz_request_id` | body | string | 否 | 幂等键 | `123212` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.audience.getSendTaskList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `0` |
| `audience_task_list` | array | 任务列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:628002001） | 重新检查入参 |

## 响应示例

成功：

```json
{
  "data": {
    "audience_task_list": [
      {
        "audience_from": "1",
        "audience_id": "123442",
        "audience_send_type": "1",
        "create_time": "1234567",
        "crowd_task_id": "123",
        "extra_send_info": {
          "except_count": "123",
          "produce_id": "123",
          "target_send_count": "1000",
          "target_send_percent": "30"
        },
        "parent_task_id": "3523",
        "status": "2",
        "success_bill_cnt": "18",
        "success_cnt": "9",
        "task_id": "1221",
        "template_id": "12453",
        "total_cnt": "10"
      }
    ],
    "total": "0"
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
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "非法的参数"
}
```

## 备注
