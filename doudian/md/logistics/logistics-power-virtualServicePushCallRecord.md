# power.virtualServicePushCallRecord

> 虚拟号服务商通话记录回传（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.virtualServicePushCallRecord` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/virtualServicePushCallRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1920 |
| 更新日期 | `2022-12-09` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 是 | - | `0` |
| `service_code` | body | string | 是 | - | `0` |
| `tel_a` | body | string | 是 | - | `0` |
| `tel_x` | body | string | 是 | - | `0` |
| `tel_b` | body | string | 是 | - | `0` |
| `tel_y` | body | string | 否 | - | `0` |
| `subid` | body | string | 否 | - | `0` |
| `calltype` | body | string | 是 | - | `0` |
| `calltime` | body | string | 是 | - | `0` |
| `ringingtime` | body | string | 是 | - | `0` |
| `starttime` | body | string | 是 | - | `0` |
| `releasetime` | body | string | 是 | - | `0` |
| `call_duration` | body | string | 否 | - | `0` |
| `ringing_duration` | body | string | 否 | - | `0` |
| `callid` | body | string | 是 | - | `0` |
| `releasedir` | body | string | 否 | - | `0` |
| `releasecause` | body | string | 否 | - | `0` |
| `calldisplay` | body | string | 否 | - | `0` |
| `callrecording` | body | string | 否 | - | `0` |
| `recordurl` | body | string | 否 | - | `0` |
| `ringingrecordurl` | body | string | 否 | - | `0` |
| `areacode` | body | string | 否 | - | `0` |
| `remark` | body | string | 否 | - | `0` |
| `tel_xext` | body | string | 否 | - | `0` |
| `collect_num_time` | body | string | 否 | - | `0` |
| `callstate` | body | string | 否 | - | `0` |
| `ext` | body | string | 否 | - | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/virtualServicePushCallRecord?app_key=your_appkey_here&method=power.virtualServicePushCallRecord&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | - | `false` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-1） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "false"
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
  "sub_msg": "业务处理失败"
}
```

## 备注
