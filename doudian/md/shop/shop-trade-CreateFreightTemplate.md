# 小时达创建运费模板

> trade.CreateFreightTemplate — 小时达创建运费模板

| 元信息 | 值 |
| --- | --- |
| 中文名 | 小时达创建运费模板 |
| 文档地址 | `/docs/doudian/shop/shop-trade-CreateFreightTemplate` |
| 接口 ID | `doudian.shop.trade.CreateFreightTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/CreateFreightTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/4195 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `freight_template_vo` | body | object | 是 | 运费模板模型 | `` |
| `  └ template_shop_id` | body | mixed | 否 | 店铺ID | `904191` |
| `  └ name` | body | string | 是 | 模板名称 | `模板名称` |
| `  └ base` | body | array | 是 | 基础运费 | `` |
| `    └ price` | body | mixed | 是 | 基础运费值 | `100` |
| `  └ weight` | body | array | 是 | 重量规则 | `` |
| `    └ first_weight` | body | mixed | 是 | 起始重量 单位mg | `1000` |
| `    └ add_weight` | body | mixed | 是 | 增加重量 | `2000` |
| `    └ add_price` | body | mixed | 是 | 加价 单位分 | `100` |
| `  └ distance` | body | array | 是 | 距离规则 | `` |
| `    └ first_distance` | body | mixed | 是 | 起始距离 单位m | `1000` |
| `    └ add_distance` | body | mixed | 是 | 增加距离 | `2000` |
| `    └ add_price` | body | mixed | 是 | 加价 | `100` |
| `  └ interval` | body | array | 是 | 时段规则 | `` |
| `    └ time_start` | body | mixed | 是 | 起始时间 单位秒 比如00:00就是0 | `0` |
| `    └ time_end` | body | mixed | 是 | 结束时间 单位秒 比如10:00 就是36000 | `36000` |
| `    └ add_price` | body | mixed | 是 | 加价 | `100` |
| `  └ free` | body | array | 是 | 包邮规则 | `` |
| `    └ amount` | body | mixed | 是 | 满xx包邮 单位分 | `10000` |
| `  └ shipping_address` | body | object | 是 | 发货地址 | `` |
| `    └ province_id` | body | string | 是 | 省 | `11` |
| `    └ city_id` | body | string | 是 | 市 | `110000` |
| `    └ town_id` | body | string | 否 | 区 | `110114` |
| `    └ street_id` | body | string | 否 | 街道 | `110114007` |
| `    └ coordinate` | body | object | 否 | 经纬度 | `` |
| `      └ latitude` | body | string | 是 | 纬度 | `23.103084` |
| `      └ longitude` | body | string | 是 | 经度 | `114.455865` |
| `      └ geo_hash` | body | string | 否 | GeoHash | `geo_hash` |
| `      └ expire_time` | body | mixed | 否 | 过期时间 | `1` |
| `  └ freight_mode` | body | mixed | 是 | 模板类型 仅4和5 | `4` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trade/CreateFreightTemplate?app_key=your_appkey_here&method=trade.CreateFreightTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_id` | mixed | 模板ID | `29877897` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "template_id": "29877897"
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
