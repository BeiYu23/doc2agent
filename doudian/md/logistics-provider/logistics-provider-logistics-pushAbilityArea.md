# logistics.pushAbilityArea

> 能力服务范围推送

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.pushAbilityArea` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/pushAbilityArea` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7510 |
| 更新日期 | `2025-06-23` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `param` | body | object | 是 | 入参对象 | `` |
| `  └ ability_code` | body | string | 是 | 能力编码，由字节分配提供 | `AC_INT_HOME_TEST0000001` |
| `  └ area_type` | body | mixed | 是 | 范围类型 1-行政区划，2-电子围栏 | `1` |
| `  └ ability_type` | body | string | 是 | 能力类型，由字节分配提供 | `NATIONAL_SUBSIDY` |
| `  └ region_areas` | body | array | 否 | 行政区划范围列表，最多支持100条 | `` |
| `    └ properties` | body | string | 否 | 属性信息，有业务诉求时可传入，传入前需向字节申请属性Key | `key：netCode，value：0001` |
| `    └ city_code` | body | string | 否 | 城市编码 | `440300` |
| `    └ city_name` | body | string | 否 | 城市名称 | `深圳市` |
| `    └ ability_area_express` | body | mixed | 否 | 该范围是否支持该能力，1-支持/生效，2-不支持/不生效 | `1` |
| `    └ district_name` | body | string | 否 | 区域名称 | `宝安区` |
| `    └ street_code` | body | string | 否 | 区域编码 | `440306024` |
| `    └ street_name` | body | string | 否 | 区域名称 | `松岗街道` |
| `    └ detail_address` | body | string | 否 | 详细地址 | `xxxx小区xxx` |
| `    └ province_code` | body | string | 否 | 省份编码 | `44` |
| `    └ province_name` | body | string | 否 | 省份名称 | `广东省` |
| `    └ district_code` | body | string | 否 | 区域编码 | `440306` |
| `  └ fence_areas` | body | array | 否 | 电子围栏范围列表，最多支持100条 | `` |
| `    └ coordinate` | body | mixed | 否 | 坐标系，1-高德，2-百度 | `1` |
| `    └ shape` | body | mixed | 否 | 围栏形状：1-圆，2-单多边形，3-带洞多边形，4-多个（带洞）多边形 | `2` |
| `    └ circular` | body | object | 否 | 圆形区域,shape = 1时必填 | `` |
| `      └ point` | body | object | 否 | 圆心 | `` |
| `        └ latitude` | body | string | 否 | 纬度 | `23.5300` |
| `        └ longitude` | body | string | 否 | 经度 | `118.9400` |
| `      └ radius` | body | string | 否 | 半径，单位：米 | `2300.10` |
| `    └ polygon_old` | body | array | 否 | 单多边形区域,shape = 2时必填 | `` |
| `      └ latitude` | body | string | 否 | 纬度 | `23.5300` |
| `      └ longitude` | body | string | 否 | 经度 | `118.9400` |
| `    └ polygon` | body | array | 否 | 带洞多边形,shape = 3时必填 | `` |
| `      └ points` | body | array | 否 | Point列表对象 | `` |
| `        └ latitude` | body | string | 否 | 纬度 | `2300.10` |
| `        └ longitude` | body | string | 否 | 经度 | `118.9400` |
| `    └ multi_polygon` | body | array | 否 | 多（带洞）多边形,shape = 4时必填 | `` |
| `      └ arrs` | body | array | 否 | Point列表数组对象 | `` |
| `        └ points` | body | array | 否 | Point列表对象 | `` |
| `          └ longitude` | body | string | 否 | 经度 | `118.9400` |
| `          └ latitude` | body | string | 否 | 纬度 | `23.5300` |
| `    └ fence_id` | body | string | 否 | 围栏ID | `a0001` |
| `    └ properties` | body | string | 否 | 属性信息，有业务诉求时可传入，传入前需向字节申请属性Key | `key：netCode，value：0001` |
| `    └ fence_name` | body | string | 否 | 围栏名称 | `xxxx围栏` |
| `    └ ability_area_express` | body | mixed | 否 | 该范围是否支持该能力，1-支持/生效，2-不支持/不生效 | `1` |
| `  └ business_sense` | body | string | 否 | 业务场景（dapan：大盘，douchao：抖超，jishilingshou:即时零售） | `douchao` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/pushAbilityArea?app_key=your_appkey_here&method=logistics.pushAbilityArea&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据对象 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-10000） | 修正入参，重新调用 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "ability_code": "AC_INT_HOME_TEST0000001",
      "ability_type": "NATIONAL_SUBSIDY",
      "area_type": "1",
      "fail_fence_areas": [
        {
          "ability_area_express": "1",
          "circular": {
            "point": {
              "latitude": "118.9400",
              "longitude": "23.5300"
            },
            "radius": "2300.10"
          },
          "coordinate": "1",
          "fence_id": "a0001",
          "fence_name": "xxxx围栏",
          "multi_polygon": [
            {
              "arrs": [
                {
                  "points": [
                    {
                      "latitude": "23.5300",
                      "longitude": "118.9400"
                    }
                  ]
                }
              ]
            }
          ],
          "polygon": [
            {
              "points": [
                {
                  "latitude": "23.5300",
                  "longitude": "118.9400"
                }
              ]
            }
          ],
          "polygon_old": [
            {
              "latitude": "23.5300",
              "longitude": "118.9400"
            }
          ],
          "properties": {},
          "shape": "2"
        }
      ],
      "fail_region_areas": [
        {
          "ability_area_express": "1",
          "city_name": "深圳市",
          "detail_address": "xxxx小区xxx",
          "district_name": "宝安区",
          "properties": {},
          "province_name": "广东省",
          "street_name": "松岗街道"
        }
      ],
      "lp_code": "power_test"
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
  "sub_code": "isv.business-failed:-10000",
  "sub_msg": "业务处理失败"
}
```

## 备注
