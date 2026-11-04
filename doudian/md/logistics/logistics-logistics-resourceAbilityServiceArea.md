# logistics.resourceAbilityServiceArea

> 比如服务商送货上门的服务范围

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.resourceAbilityServiceArea` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/resourceAbilityServiceArea` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2147 |
| 更新日期 | `2025-05-09` |

## 接口说明

- 文档书: 物流发货API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ability_code` | body | string | 是 | 服务商能力编码，例如送货上门能力的编码，由抖音电商侧提供 | `AC_INT_HOME_TEST0000001` |
| `service_areas` | body | array | 是 | 能力服务范围列表 | `` |
| `  └ country_code` | body | string | 否 | 国家编码，serviceAreaType=REGION时有效，且必填 | `CN` |
| `  └ country_name` | body | string | 否 | 国家名称，serviceAreaType=REGION时有效，且必填 | `中华人民共和国` |
| `  └ province_code` | body | string | 否 | 省份编码，serviceAreaType=REGION时有效，且必填 | `44` |
| `  └ province_name` | body | string | 否 | 省份名称，serviceAreaType=REGION时有效，且必填 | `广东省` |
| `  └ city_code` | body | string | 否 | 城市编码，serviceAreaType=REGION时有效，且必填 | `440300` |
| `  └ city_name` | body | string | 否 | 城市名称，serviceAreaType=REGION时有效，且必填 | `深圳市` |
| `  └ district_code` | body | string | 否 | 区县编码，serviceAreaType=REGION时有效，且必填 | `440306` |
| `  └ district_name` | body | string | 否 | 区县名称，serviceAreaType=REGION时有效，且必填 | `宝安区` |
| `  └ street_code` | body | string | 否 | 街道编码，serviceAreaType=REGION时有效，且必填 | `440306024` |
| `  └ street_name` | body | string | 否 | 街道名称，serviceAreaType=REGION时有效，且必填 | `松岗街道` |
| `  └ service_fence` | body | string | 否 | 电子围栏serviceAreaType=EFENCE时有效，且必填 | `{}` |
| `  └ service_area_express` | body | number | 否 | 能力表达：1-能(送货上门)，2-不能(送货上门) | `1` |
| `  └ service_area_type` | body | string | 否 | 服务范围定义类型： REGION（行政区划4级地址）  EFENCE（电子围栏）——暂不支持 2种之一。 | `REGION` |
| `extend_dimension_code` | body | string | 否 | 针对上门拆旧是【一级-二级-三级回收类目编码】 | `扩展维度` |
| `busines_sense` | body | string | 否 | douchao：抖超 | `业务场景` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 传入参数错误（sub_code: isv.business-failed:-10000） | 修正参数之后，再次调用接口 |

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
  "sub_code": "isv.business-failed:-10000",
  "sub_msg": "传入参数错误"
}
```

## 备注
