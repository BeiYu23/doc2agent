# superm.getPlatformPickUpCalendar

> 售后单查询运力时间段日历

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.getPlatformPickUpCalendar` |
| 中文名 | 售后单查询运力时间段日历 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/getPlatformPickUpCalendar` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2738 |
| 更新日期 | `2025-12-11` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | mixed | 是 | 售后单号 | `7161813415244218654` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/getPlatformPickUpCalendar?app_key=your_appkey_here&method=superm.getPlatformPickUpCalendar&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_support` | boolean | 是否支持查询 | `true` |
| `un_support_reason` | string | 不支持的原因 | `""` |
| `period_list` | array | 时间段 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 50112:售后单[146708678695909124]不属于当前店铺, 请输入正确的售后单号（sub_code: isv.business-failed:50112） | 50112:售后单[146708678695909124]不属于当前店铺, 请输入正确的售后单号 |

## 响应示例

成功：

```json
{
  "data": {
    "is_support": "true",
    "period_list": [
      {
        "time_begin_ts": "166779000",
        "time_end_ts": "1667793600"
      }
    ],
    "un_support_reason": "\"\""
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
  "sub_code": "isv.business-failed:50112",
  "sub_msg": "50112:售后单[146708678695909124]不属于当前店铺, 请输入正确的售后单号"
}
```

## 备注
