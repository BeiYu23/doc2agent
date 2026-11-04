# sms.audience.send

> 按人群包发送短信

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.audience.send` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/send` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/6664 |
| 更新日期 | `2026-09-03` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 渠道账号，请使用专属人群包短信发送渠道账号。 | `12xxxx` |
| `sign` | body | string | 是 | 签名,请使用专属人群包短信发送渠道账号下的签名。 | `sssss` |
| `template_id` | body | string | 是 | 模版id，请使用专属人群包短信发送渠道账号下的模版。 | `ST_xxxx` |
| `template_param` | body | string | 是 | 模版参数 | `{"11":"12","12":"333"}` |
| `audience_id` | body | string | 是 | 人群ID，audienceFrom=2时，传入crowdTaskId相同值即可 | `123451245` |
| `link_id` | body | string | 否 | 需要链接统计效果时必传 | `1212212212` |
| `mini_app_link_id` | body | string | 否 | 小程序短链批次ID | `1212212212` |
| `audience_from` | body | mixed | 否 | 不同场景的人群包，0-通过抖店接口创建出来的人群包； 1-公域标签创建的人群包； 2-火山的人群包； 3-组合人群包； | `1` |
| `audience_send_type` | body | mixed | 否 | 发送类型 0默认 1时机模型 | `0` |
| `crowd_task_id` | body | mixed | 否 | 种子人群任务ID，当audience_from = 2时必填 | `123` |
| `max_send_limit` | body | mixed | 否 | 限制该任务单次最大可成功发送的人数。当audience_from = 2时有效 | `123` |
| `end_time` | body | mixed | 否 | 当audience_send_type=1时有效，秒级时间戳。跟start_time最大间隔5天，建议设置24小时间隔，结束时间限制为某天的最后一秒如23:59:59 | `1754567437` |
| `start_time` | body | mixed | 否 | 当audience_send_type=1时有效，秒级时间戳 | `1754567437` |
| `non_disturb_time_list` | body | array | 否 | 免打扰时段。平台强制上午9点前，晚上8点后为勿扰时段。可增加其他勿扰时段 | `` |
| `  └ end_time` | body | string | 否 | 勿扰结束时间 格式 hh:mm | `11:59` |
| `  └ start_time` | body | string | 否 | 勿扰开始时间 格式 hh:mm | `08:00` |
| `produce_id` | body | string | 否 | 人群圈选生产任务id | `123532` |
| `part_send_config` | body | object | 否 | 抽样发送 | `` |
| `  └ target_send_count` | body | mixed | 否 | 抽样发送数量 | `12421` |
| `  └ target_send_percent` | body | mixed | 否 | 抽样百分比，取值范围[0, 100) | `30` |
| `biz_request_id` | body | string | 否 | 业务幂等键，按照appId+shopId+biz_request_id 做幂等处理 | `11111111` |
| `abExperimentInfo` | body | object | 否 | 实验组配置 | `` |
| `  └ treatment_ratio` | body | mixed | 否 | 实验组比例范围 50~90，步长 10 | `50` |
| `  └ enabled` | body | boolean | 否 | 默认不开启ab | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/audience/send?app_key=your_appkey_here&method=sms.audience.send&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 响应码 | `12` |
| `message` | string | 响应信息 | `1234` |
| `send_task_id` | string | 发送任务ID | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:628002001） | 请检查参数 |
| `50002` | 业务处理失败 / 人群元信息不存在（sub_code: isv.business-failed:628005600） | 请使用存在的人群包 |
| `50002` | 业务处理失败 / 存在待执行的人群包发送任务，请稍后再试（sub_code: isv.business-failed:628003300） | 存在待执行的人群包发送任务，请稍后再试 |
| `50002` | 业务处理失败 / 模版信息错误（sub_code: isv.business-failed:628005100） | 请检查模版信息 |
| `50002` | 业务处理失败 / 未签署短信免责协议（sub_code: isv.business-failed:628003306） | 签署短信免责协议 |
| `50002` | 业务处理失败 / 获取人群包数量错误，请稍后再试（sub_code: isv.business-failed:628004001） | 获取人群包数量错误，请稍后再试 |
| `50002` | 业务处理失败 / 人群包数量不得少于100（sub_code: isv.business-failed:628003308） | 人群包数量不得少于100 |
| `50002` | 业务处理失败 / 当前时间段不允许发短信（sub_code: isv.business-failed:628003202） | 请在短信允许发送时间发送 |
| `50002` | 业务处理失败 / 验证码失效或不存在（sub_code: isv.business-failed:628004000） | 请检查输入的验证码 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "12",
    "message": "1234",
    "send_task_id": "123"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:628002001",
  "sub_msg": "参数错误"
}
```

## 备注
