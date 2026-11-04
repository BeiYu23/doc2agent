# logistics.virtualServicePushCallRecord

> 虚拟号服务商通话记录回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.logistics.virtualServicePushCallRecord` |
| 中文名 | 虚拟号服务商通话记录回传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/virtualServicePushCallRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/2735 |
| 更新日期 | `2022-11-14` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 是 | 业务id | `0` |
| `service_code` | body | string | 是 | 服务商标识 | `0` |
| `tel_a` | body | string | 是 | 被叫号码 | `0` |
| `tel_x` | body | string | 是 | 虚拟主号 | `0` |
| `tel_b` | body | string | 是 | 主叫号码 | `0` |
| `tel_y` | body | string | 否 | 来显号码 | `0` |
| `sub_id` | body | string | 否 | 绑定id | `0` |
| `call_type` | body | string | 是 | 10：A号主叫，即A回呼 11：A号被叫，即A呼入 12：未输入分机号放弃呼叫 20：无绑定关系，即Xx无绑定号码 | `0` |
| `call_time` | body | string | 是 | 发起呼叫时间 格式: yyyy-MM-dd HH:mm:ss | `0` |
| `ringing_time` | body | string | 是 | 振铃开始时间格式: yyyy-MM-dd HH:mm:ss | `0` |
| `start_time` | body | string | 是 | 通话开始时间格式: yyyy-MM-dd HH:mm:ss | `0` |
| `release_time` | body | string | 是 | 通话结束时间格式: yyyy-MM-dd HH:mm:ss | `0` |
| `call_duration` | body | string | 是 | 通话时长 | `0` |
| `ringing_duration` | body | string | 是 | 振铃时长 | `0` |
| `call_id` | body | string | 是 | 通话标识 | `0` |
| `release_dir` | body | string | 是 | 释放方向1表示主叫, 2表示被叫，0表示平台释放 | `0` |
| `release_cause` | body | string | 否 | 释放原因 | `0` |
| `call_display` | body | string | 是 | 来显控制当其他号码为主叫时，是否在被叫上显示其他号码的真实号码。 0：不显示真实号码；1：显示真实号码。默认是0不显示真实号码 | `0` |
| `call_recording` | body | string | 是 | 录音控制 | `0` |
| `record_url` | body | string | 否 | 通话录音地址 | `0` |
| `ringing_record_url` | body | string | 否 | 振铃录音地址 | `0` |
| `area_code` | body | string | 否 | 对应绑定请求中areacode | `0` |
| `remark` | body | string | 否 | 接入商自有字段 | `0` |
| `tel_xext` | body | string | 否 | 四位分机号 | `0` |
| `collect_num_time` | body | string | 否 | 发起收号时获取的时间。格式YYYY-MM-DD HH:mm:SS | `0` |
| `call_state` | body | string | 是 | 呼叫状态 ANSWERED通话成功，被叫接通，双方成功建立通话 BUSY被叫正忙 NO_ANSWER被叫无应答 REJECT被叫拒接 HANGUP主叫放弃 INVALID_NUMBER空号，话务平台返回的号码是空号，非返回字段为空 POWER_OFF被叫关机 UNAVAILABLE被叫暂时无法接听，不在服务区、暂时无法接通（不关机拔电池）等SUSPEND被叫停机 NO_BINDING无绑定关系 BANNED无权呼叫 OTHER其他失败情形 | `0` |
| `ext` | body | string | 否 | 额外字段 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/orienPlanAuthors?app_key=your_appkey_here&method=buyin.orienPlanAuthors&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -1:获取分布式锁失败（sub_code: isv.business-failed:-1） | -1:获取分布式锁失败 |

## 响应示例

成功：

```json
{
  "data": {
    "orien_plan_authors": [
      {
        "apply_id": "1",
        "apply_info": "申请加入",
        "apply_suc_time": "1625480546",
        "apply_time": "1625480546",
        "audit_status": "1",
        "buyin_id": "11111",
        "end_time": "end_time",
        "orien_plan_id": "1233221",
        "user_name": "达人昵称"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "-1:获取分布式锁失败"
}
```

## 备注
