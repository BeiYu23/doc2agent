# 同步服务范围数据

> gis.serviceArea.sync — 同步服务范围数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | 同步服务范围数据 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-gis-serviceArea-sync` |
| 接口 ID | `doudian.logistics-provider.gis.serviceArea.sync` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/gis/serviceArea/sync` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2883 |
| 更新日期 | `2023-02-28` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `express` | body | string | 是 | 物流商编码，接口研发提供 | `jdexpress` |
| `ability_code` | body | string | 是 | 能力表达，接口研发提供 | `delivery` |
| `service_areas` | body | array | 是 | 服务范围结构体 | `` |
| `  └ country_code` | body | string | 否 | 国家国标码 | `cn` |
| `  └ province_code` | body | string | 否 | 省国标码 | `310000` |
| `  └ city_code` | body | string | 否 | 市国标码 | `311200` |
| `  └ district_code` | body | string | 否 | 区国标码 | `311223` |
| `  └ street_code` | body | string | 否 | 街道国标码 | `311223003` |
| `  └ fence` | body | object | 否 | 围栏结构体 | `` |
| `    └ type` | body | string | 是 | 围栏形状，multipolygon，polygon | `multipolygon` |
| `    └ standard` | body | string | 是 | 坐标规范 | `GaoDe` |
| `    └ multipolygon` | body | array | 否 | 多多边形结构体 | `` |
| `      └ polygons` | body | array | 是 | 带洞多边形结构体 | `` |
| `        └ polygon` | body | array | 是 | 简单多边形结构体 | `` |
| `          └ longitude` | body | string | 是 | 经度 | `120.1232` |
| `          └ latitude` | body | string | 是 | 纬度 | `45.12389` |
| `  └ service_area_express` | body | string | 是 | 是否能送货上门 1-能送货上门 2-不能送货上门 | `1` |
| `  └ service_area_type` | body | string | 是 | 服务范围类型 EFENCE-围栏 REGION-行政区划 | `EFENCE` |
| `  └ country_name` | body | string | 否 | 国家名称 | `中国` |
| `  └ province_name` | body | string | 否 | 省名称 | `浙江省` |
| `  └ city_name` | body | string | 否 | 市名称 | `杭州市` |
| `  └ district_name` | body | string | 否 | 区县名称 | `余杭区` |
| `  └ street_name` | body | string | 否 | 街道名称 | `仓前街道` |
| `resource_ability` | body | object | 否 | 资源能力表达 | `` |
| `  └ resource_code` | body | string | 是 | 资源code | `1234` |
| `  └ resource_type` | body | string | 是 | 资源类型 | `fence` |
| `  └ ability_code` | body | string | 是 | 能力code | `delivery` |
| `  └ ability_type` | body | string | 是 | 能力类型 | `delivery` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/partner/GetPartnerInfo?app_key=your_appkey_here&method=partner.GetPartnerInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1:服务范围列表不能为空/最多100（sub_code: isv.business-failed:1） | 1:服务范围列表不能为空/最多100 |

## 响应示例

成功：

```json
{
  "data": {
    "partner_app": {
      "app_name": "1",
      "extra": {},
      "partner_id": "1",
      "partner_name": "1",
      "secret": "1"
    }
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
  "sub_code": "isv.business-failed:1",
  "sub_msg": "1:服务范围列表不能为空/最多100"
}
```

## 备注
