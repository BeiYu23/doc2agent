# 呼叫运力售后取件

> superm.applyPlatformPickUp — 呼叫运力售后取件

| 元信息 | 值 |
| --- | --- |
| 中文名 | 呼叫运力售后取件 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-applyPlatformPickUp` |
| 接口 ID | `doudian.retail-store.superm.applyPlatformPickUp` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/applyPlatformPickUp` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2741 |
| 更新日期 | `2025-12-11` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | string | 是 | 售后单ID | `7161813415244218654` |
| `selected_calendar_period` | body | object | 否 | 运力呼叫时间段 | `` |
| `  └ time_end_ts` | body | mixed | 是 | 时间段结束时间 | `1667793600` |
| `  └ time_begin_ts` | body | mixed | 是 | 时间段开始时间 | `1667790000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/applyPlatformPickUp?app_key=your_appkey_here&method=superm.applyPlatformPickUp&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `logistics_id` | string | 物流单ID | `100000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `20000` | 系统错误 / 请求内部服务异常,请重试（sub_code: isp.service-error:20200） | 请求内部服务异常,请重试 |
| `20000` | 系统错误 / 虚拟号生成异常（sub_code: isp.service-error:20213） | 虚拟号生成异常 |
| `20000` | 系统错误 / 请求内部服务异常,请重试（sub_code: isp.service-error:20201） | 请求内部服务异常,请重试 |
| `50002` | 业务处理失败 / 拓展字段校验不通过（sub_code: isv.business-failed:50400） | 拓展字段校验不通过 |
| `50002` | 业务处理失败 / 业务错误，此状态下不可重试（sub_code: isv.business-failed:50300） | 业务错误，此状态下不可重试 |
| `50002` | 业务处理失败 / 19009:已存在进行中的物流单，请刷新页面后按前一次预约配送方式重试。上次配送方式为：平台运力（sub_code: isv.business-failed:19009） | 19009:已存在进行中的物流单，请刷新页面后按前一次预约配送方式重试。上次配送方式为：平台运力 |
| `50002` | 业务处理失败 / 20306002:操作冲突，请稍后重试（sub_code: isv.business-failed:20306002） | 20306002:操作冲突，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "logistics_id": "100000"
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
  "sub_code": "isv.parameter-invalid:40100",
  "sub_msg": "参数错误"
}
```

## 备注
