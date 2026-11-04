# superm.getPlatformPickUpEstimatedCharge

> 运力呼叫询价（逆向）/运力取消询价（逆向）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.getPlatformPickUpEstimatedCharge` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/getPlatformPickUpEstimatedCharge` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2737 |
| 更新日期 | `2022-11-10` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 是 | 售后单ID | `7161813415244218654` |
| `selected_calendar_period` | body | object | 否 | 查询的时间段 | `` |
| `  └ time_begin_ts` | body | number | 是 | 时间段开始时间；Unix时间戳，单位：秒 | `1667790000` |
| `  └ time_end_ts` | body | number | 是 | 时间段结束时间；Unix时间戳，单位：秒 | `1667793600` |
| `dispatcher_fee_type` | body | string | 是 | 查询的费用类型；1 -呼叫运力费用；2-取消运力费用 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/getPlatformPickUpEstimatedCharge?app_key=your_appkey_here&method=superm.getPlatformPickUpEstimatedCharge&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `dispatcher_fee` | number | 运力费用预估，单位：分 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统服务异常,请重试（sub_code: isp.service-error:20100） | 读操作数据库异常 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `20000` | 系统错误 / 请求内部服务异常,请重试（sub_code: isp.service-error:20200） | 请求内部服务异常,请重试 |
| `50002` | 业务处理失败 / op not found（sub_code: isv.business-failed:20201） | op not found |
| `50002` | 业务处理失败 / 业务错误，此状态下不可重试（sub_code: isv.business-failed:50300） | 业务错误，此状态下不可重试 |

## 响应示例

成功：

```json
{
  "data": {
    "dispatcher_fee": "100"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:20100",
  "sub_msg": "系统服务异常,请重试"
}
```

## 备注
