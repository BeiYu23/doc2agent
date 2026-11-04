# 【上门回收】更新上门服务范围信息同步

> resale.supplier.serviceArea — 【上门回收】更新上门服务范围信息同步

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【上门回收】更新上门服务范围信息同步 |
| 文档地址 | `/docs/doudian/recycle/recycle-resale-supplier-serviceArea` |
| 接口 ID | `doudian.recycle.resale.supplier.serviceArea` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/4497 |
| 更新日期 | `2026-03-26` |

## 接口说明

- 文档书: 回收寄卖API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_entity_code` | body | string | 是 | 服务商实体编码，抖音研发给出 | `xxx` |
| `service_area_type` | body | string | 是 | - EFENCE：电子围栏信息同步 - REGION：四级国标地址信息同步 | `EFENCE` |
| `service_areas` | body | array | 否 | 地理位置信息 | `` |
| `  └ district_name` | body | string | 否 | 三级区县名称 | `宝山区` |
| `  └ support_category_list` | body | array | 否 | 地址所支持类目列表 | `` |
| `    └ fourth_category_id` | body | string | 否 | 四级类目ID | `"444"` |
| `    └ third_category_id` | body | string | 否 | 三级类目ID | `"333"` |
| `    └ second_category_id` | body | string | 否 | 二级类目ID | `"222"` |
| `    └ first_category_id` | body | string | 否 | 一级类目ID | `"111"` |
| `  └ district_code` | body | string | 否 | 三级区国标 | `"1111"` |
| `  └ street_code` | body | string | 否 | 四级街道国标 | `"1111"` |
| `  └ service_area_status` | body | mixed | 否 | 1-可用，0-不可用 | `1` |
| `  └ province_name` | body | string | 否 | 一级省名称 | `广东省` |
| `  └ city_name` | body | string | 否 | 二级城市名称 | `深圳市` |
| `  └ support_modes` | body | array | 否 | 支持的回收模式，不传默认为分离式，[0]:分离式，[1]:一站式，都支持：传入[0,1] | `[0]` |
| `  └ province_code` | body | string | 否 | 一级省国标 | `"111"` |
| `  └ fences` | body | array | 否 | 围栏信息 | `` |
| `    └ support_category_list` | body | array | 否 | 围栏所支持类目列表 | `` |
| `      └ third_category_id` | body | string | 否 | 三级类目ID | `"333"` |
| `      └ first_category_id` | body | string | 否 | 一级类目ID | `"111"` |
| `      └ fourth_category_id` | body | string | 否 | 四级类目ID | `"444"` |
| `      └ second_category_id` | body | string | 否 | 二级类目ID | `"222"` |
| `    └ points` | body | array | 否 | 围栏经纬度列表 | `` |
| `      └ lat` | body | string | 否 | 纬度信息 | `20.232433` |
| `      └ lng` | body | string | 否 | 经度信息 | `20.232433` |
| `    └ support_modes` | body | array | 否 | 支持的回收模式，不传默认为分离式，[0]:分离式，[1]:一站式，都支持：传入[0,1] | `[0]` |
| `    └ fence_id` | body | string | 否 | 围栏ID | `"11111111111"` |
| `  └ street_name` | body | string | 否 | 四级街道名称 | `龙岗街道` |
| `  └ city_code` | body | string | 否 | 二级市国标 | `"1111"` |
| `service_coordinate_type` | body | string | 否 | service_area_type为电子围栏时选填 | `"BD09"` |
| `support_category_list` | body | array | 否 | 范围所支持类目列表 | `` |
| `  └ third_category_id` | body | string | 否 | 三级类目ID | `"333"` |
| `  └ first_category_id` | body | string | 否 | 一级类目ID | `"111"` |
| `  └ fourth_category_id` | body | string | 否 | 四级类目ID | `"444"` |
| `  └ second_category_id` | body | string | 否 | 二级类目ID | `"222"` |
| `contains_category` | body | mixed | 否 | 是否包含范围支持的类目：0-不包含，1-包含 | `1` |
| `category_type_list` | body | array | 否 | 指定推送的范围关联的类目类型列表，1：大家电，2： 3C行业，3：小家电 | `1,2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=resale.supplier.serviceArea&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `10001` | 请求部分失败 / 批量请求部分失败（sub_code: isv.business-part-failed:-8） | 检查部分地址是否符合标准 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:-3） | 请检查检查请求参数 |
| `20000` | 系统错误（sub_code: isp.service-error:-1） | 请联系开发者 |

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
  "code": 10001,
  "msg": "请求部分失败",
  "sub_code": "isv.business-part-failed:-8",
  "sub_msg": "批量请求部分失败"
}
```

## 备注
