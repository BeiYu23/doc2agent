# gis.fenceArea.push

> 围栏数据推送

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.gis.fenceArea.push` |
| 中文名 | 围栏数据推送 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/gis/fenceArea/push` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2879 |
| 更新日期 | `2023-01-09` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `express` | body | string | 是 | 物流商code，接口研发提供 | `yunda` |
| `express_key` | body | string | 是 | 物流商校验码，接口研发提供 | `lqwdnqwd` |
| `action` | body | string | 是 | 0-删除 1-创建或更新 | `0` |
| `fence_area` | body | array | 是 | 围栏范围结构体 | `` |
| `  └ province_code` | body | string | 否 | 省国标码 | `310000` |
| `  └ city_code` | body | string | 否 | 市国标码 | `311100` |
| `  └ district_code` | body | string | 否 | 区国标码 | `311121` |
| `  └ street_code` | body | string | 否 | 街道国标码 | `31112103` |
| `  └ detail_address` | body | string | 否 | 详细地址 | `浙江省杭州市余杭区仓前街道爱力中心` |
| `  └ branch_code` | body | string | 是 | 物流商网点code | `23389` |
| `  └ branch_name` | body | string | 是 | 物流商网点名称 | `这是一个网点` |
| `  └ area_type` | body | string | 是 | 围栏类型 0-坐标 1-行政区划 | `0` |
| `  └ fence` | body | object | 是 | 围栏坐标结构体 | `` |
| `    └ type` | body | string | 是 | 围栏形状 | `multipolygon` |
| `    └ standard` | body | string | 是 | 围栏坐标规范 | `GaoDe` |
| `    └ multipolygon` | body | string | 否 | 围栏坐标pg定义 | `Multipolygon (((1 1,1 2,2 2,2 1, 1 1)))` |
| `  └ data_id` | body | number | 是 | 数据唯一标识 | `12938712983` |
| `  └ entity_type` | body | string | 是 | 实体类型 0-网点 1-小件员 | `0` |
| `  └ delivery_type` | body | string | 否 | 网点配送方式 0-不区分 1-仅支持配送 2-仅支持自提 | `0` |
| `  └ three_segment_code` | body | string | 否 | 小件员三段码 | `127` |
| `  └ biz_type` | body | string | 否 | 小件员业务类型 0-揽件 1-派件 | `0` |
| `  └ reachable` | body | string | 是 | 是否可达 0-不可达 1-可达 | `1` |
| `  └ calculate` | body | string | 是 | 是否可用于推算段码 0-不可用于推算段码 1-可用于推算段码 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/gis/fenceArea/push?app_key=your_appkey_here&method=gis.fenceArea.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | array | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "data_id": "1233",
        "reason": "鉴权失败",
        "success": "0"
      }
    ]
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
