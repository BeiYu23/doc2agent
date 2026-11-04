# pigeon.getStaffOnlineRecordList

> 查询客服在线日志列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.getStaffOnlineRecordList` |
| 中文名 | 查询客服在线日志列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/getStaffOnlineRecordList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5343 |
| 更新日期 | `2023-11-10` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `date` | body | string | 是 | 查询哪一天的数据 | `20231223` |
| `staff_id` | body | number | 否 | 客服id | `20` |
| `platform` | body | number | 否 | 1 APP 2 PC 3 PC+APP | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/inbound/create?app_key=your_appkey_here&method=yunc.wms.inbound.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `staff_online_records` | array | 结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-1） | 业务处理失败 |
| `50002` | 业务处理失败 / 最多只能查询35天的数据（sub_code: isv.business-failed:2） | 最多只能查询35天的数据 |
| `50002` | 业务处理失败 / 3:db错误（sub_code: isv.business-failed:3） | 3:db错误 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
