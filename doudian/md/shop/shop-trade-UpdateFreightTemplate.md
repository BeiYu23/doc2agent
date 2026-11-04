# trade.UpdateFreightTemplate

> 小时达更新运费模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.trade.UpdateFreightTemplate` |
| 中文名 | 小时达更新运费模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/UpdateFreightTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/4674 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `freight_template_vo` | body | object | 是 | 运费模板信息 | `` |
| `  └ id` | body | mixed | 是 | 模板ID | `29877897` |
| `  └ name` | body | string | 是 | 模板名称 | `测试运费模板1` |
| `  └ base` | body | array | 是 | 基础运费 | `` |
| `    └ price` | body | mixed | 是 | 基础运费值 | `100` |
| `  └ weight` | body | array | 是 | 重量规则 | `` |
| `    └ first_weight` | body | mixed | 是 | 起始重量 单位mg | `100` |
| `    └ add_weight` | body | mixed | 是 | 增加重量 | `100` |
| `    └ add_price` | body | mixed | 是 | 加价 单位分 | `100` |
| `  └ distance` | body | array | 是 | 距离规则 | `` |
| `    └ first_distance` | body | mixed | 是 | 起始距离 单位m | `100` |
| `    └ add_distance` | body | mixed | 是 | 起始距离 单位m | `100` |
| `    └ add_price` | body | mixed | 是 | 加价 | `100` |
| `  └ interval` | body | array | 是 | 时段规则 | `` |
| `    └ time_start` | body | mixed | 是 | 起始时间 单位秒 比如00:00就是0 | `0` |
| `    └ time_end` | body | mixed | 是 | 结束时间 单位秒 比如10:00 就是36000 | `36000` |
| `    └ add_price` | body | mixed | 是 | 加价 | `100` |
| `  └ free` | body | array | 是 | 包邮规则 | `` |
| `    └ amount` | body | mixed | 是 | 满xx包邮 单位分 | `100` |
| `  └ shipping_address` | body | object | 是 | 发货地址 | `` |
| `    └ province_id` | body | string | 是 | 省 | `11` |
| `    └ city_id` | body | string | 是 | 市 | `110000` |
| `    └ town_id` | body | string | 否 | 区 | `110108` |
| `    └ street_id` | body | string | 否 | 街道 | `110108011` |
| `    └ coordinate` | body | object | 否 | 经纬度 | `` |
| `      └ latitude` | body | string | 是 | 纬度 | `10.00` |
| `      └ longitude` | body | string | 是 | 经度 | `10.00` |
| `      └ geo_hash` | body | string | 否 | GeoHash | `10` |
| `  └ freight_mode` | body | mixed | 是 | 模板类型 仅4和5 | `5` |
| `update_without_rule` | body | boolean | 否 | 不更新规则标识 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/outbound/cancel?app_key=your_appkey_here&method=yunc.wms.outbound.cancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_id` | mixed | 运费模板ID | `29877897` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10009999:查询运费模版失败（sub_code: isv.business-failed:10009999） | 10009999:查询运费模版失败 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10009999",
  "sub_msg": "10009999:查询运费模版失败"
}
```

## 备注
