# 虚拟号服务商回传虚拟号接通事件

> power.HandleVirtualTelConnect — 虚拟号服务商回传虚拟号接通事件

| 元信息 | 值 |
| --- | --- |
| 中文名 | 虚拟号服务商回传虚拟号接通事件 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-HandleVirtualTelConnect` |
| 接口 ID | `doudian.logistics.power.HandleVirtualTelConnect` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/HandleVirtualTelConnect` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2011 |
| 更新日期 | `2022-12-09` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 是 | 请求id | `1` |
| `service_code` | body | string | 是 | 服务商code | `1` |
| `callid` | body | string | 否 | 通话id | `1` |
| `tel_a` | body | string | 否 | A号码 | `1` |
| `tel_x` | body | string | 否 | X号码 | `1` |
| `tel_b` | body | string | 否 | B号码 | `1` |
| `tel_y` | body | string | 否 | Y号码 | `1` |
| `subid` | body | string | 否 | 绑定id | `1` |
| `calltype` | body | string | 否 | 呼叫类型 | `1` |
| `calltime` | body | string | 否 | 呼叫时间（已废弃，请传下方的eventTime字段） | `1` |
| `remark` | body | string | 否 | 备注 | `1` |
| `tel_xext` | body | string | 否 | 分机号 | `1` |
| `collect_num_time` | body | string | 否 | 时间(可不传，废弃字段) | `1` |
| `ext` | body | string | 否 | 拓展字段 | `1` |
| `event_type` | body | string | 否 | 事件类型（1开始呼叫、2被叫方振铃、3呼叫建立、4呼叫结束） | `1` |
| `all_event_type` | body | array | 否 | 本次通话全部的通话事件（正常接通挂断的情况下） | `1,3,4` |
| `event_time` | body | number | 否 | 事件发生时间的时间戳（单位：秒） | `1669344970` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/HandleVirtualTelConnect?app_key=your_appkey_here&method=power.HandleVirtualTelConnect&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
