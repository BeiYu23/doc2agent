# logistics.voiceNotifyCallRecordCallback

> 火山引擎语音通知回调

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.voiceNotifyCallRecordCallback` |
| 中文名 | 火山引擎语音通知回调 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/voiceNotifyCallRecordCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2894 |
| 更新日期 | `2023-02-27` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `account_id` | body | string | 是 | 账号ID | `1` |
| `call_id` | body | string | 是 | 呼叫唯一ID | `NM20010115474511150001012500007a8c` |
| `message_type` | body | string | 是 | 消息回执类型 2-呼叫记录；3-录音 | `2` |
| `service_type` | body | string | 是 | 服务类型，详见：https://www.volcengine.com/docs/6358/69226#%E6%9C%8D%E5%8A%A1%E7%B1%BB%E5%9E%8B | `100` |
| `sub_service_type` | body | string | 否 | 子服务类型,详见：服务类型枚举值https://www.volcengine.com/docs/6358/69226#%E5%AD%90%E6%9C%8D%E5%8A%A1%E7%B1%BB%E5%9E%8B | `101` |
| `number_pool_no` | body | string | 否 | 号码池编号 | `NP160102116501911493` |
| `caller` | body | string | 否 | 主叫方号码 | `13100001111` |
| `caller_country_iso_code` | body | string | 否 | 主叫方号码所在国家ISO编码 | `CH` |
| `caller_province_code` | body | string | 否 | 主叫方号码所在省份编码 | `110000` |
| `caller_city_code` | body | string | 否 | 主叫方号码所在城市编码 | `010` |
| `callee` | body | string | 否 | 被叫方号码 | `13100001111` |
| `callee_country_iso_code` | body | string | 否 | 被叫方号码所在国家ISO编码 | `CH` |
| `callee_province_code` | body | string | 否 | 被叫方号码所在省份编码 | `110000` |
| `callee_city_code` | body | string | 否 | 被叫方号码所在城市编码 | `010` |
| `begin_call_time` | body | number | 否 | 呼叫开始时间自(1970-01-01 00:00:00"开始的毫秒数) | `1607588903000` |
| `ring_time` | body | number | 否 | 被叫方振铃时间 | `1607588903000` |
| `start_time` | body | number | 否 | 呼叫建立时间 | `1607588903000` |
| `end_time` | body | number | 否 | 呼叫挂断时间 | `1607588903000` |
| `release_type` | body | string | 否 | 挂断类型：0-主叫；1-被叫；2-平台 | `0` |
| `call_duration` | body | string | 否 | 呼叫时长（秒） | `20` |
| `call_result` | body | string | 否 | 呼叫识别结果 1-正常接通；2-关机；3-停机；4-空号；5-主叫提前挂机；6-暂时无法接通；7-无人接听；8-被叫忙；9-被叫拒接；10-被叫不可及；11-线路忙；12-无权限呼叫；13-无绑定关系；14-网络忙>；15-路由失败；16-中间号状态异常；17-呼出限制；18-呼入限制；19-超时；20-平台系统异常；21-被叫未振铃，收到挂断消息；22-被叫振铃了挂断或超时未摘机；-1-其他(包含匹配失败的情况)； | `1` |
| `audio_record_flag` | body | string | 否 | 录音是否分轨,1-分轨；0-不分轨； | `0` |
| `cdr_create_time` | body | number | 否 | 呼叫记录建立时间 | `1607588903000` |
| `user_data` | body | string | 否 | 用户拓展参数，最大长度为2048 | `测试` |
| `task_open_id` | body | string | 否 | 任务id | `111` |
| `single_open_id` | body | string | 是 | 用户定义的id | `7180417835737481260` |
| `ext` | body | string | 否 | 用户自定义参数，长度限制250 | `7180417835737481260` |
| `digits` | body | array | 否 | ivr按键 | `["1"]` |
| `audio_record_url` | body | string | 否 | 录音文件下载地址 | `https://xx/xx/S1111111021.wav` |
| `audio_record_left_url` | body | string | 否 | 录音文件分轨左声道下载地址 | `https://xx/xx/S1111111021_L.wav` |
| `audio_record_right_url` | body | string | 否 | 录音文件分轨右声道下载地址 | `https://xx/xx/S1111111021_R.wav` |
| `audio_record_model` | body | string | 否 | 录音类型,1-主叫左声道；2-主叫右声道；3-混音； | `3` |
| `caller_show_number` | body | string | 否 | 主叫侧外显号码 | `13100001111` |
| `callee_show_number` | body | string | 否 | 被叫方外显号码 | `13100001111` |
| `call_type` | body | string | 否 | 呼叫类型 0-呼入；1-呼出； | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/voiceNotifyCallRecordCallback?app_key=your_appkey_here&method=logistics.voiceNotifyCallRecordCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
