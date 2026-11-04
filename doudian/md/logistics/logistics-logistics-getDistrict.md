# 四级地址查询

> logistics.getDistrict — 四级地址查询接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 四级地址查询 |
| 文档地址 | `/docs/doudian/logistics/logistics-logistics-getDistrict` |
| 接口 ID | `doudian.logistics.logistics.getDistrict` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getDistrict` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2905 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `code` | body | string | 否 | 行政区划code | `CN` |
| `subdistrict` | body | string | 否 | 返回下级层级 | `2` |
| `version` | body | string | 否 | 版本号 | `ecom` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getDistrict?app_key=your_appkey_here&method=logistics.getDistrict&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `district` | object | 区划信息 | `` |
| `version` | string | 版本号 | `1.0.0` |
| `update_time` | string | 更新时间戳 | `123456789` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:400） | 修改参数重新调用 |

## 响应示例

成功：

```json
{
  "data": {
    "district": {
      "centroid": "1.0,2.0",
      "code": "110000",
      "description": "市",
      "level": "1",
      "name": "北京",
      "par_regions": [
        {
          "centroid": "1.0,2.0",
          "code": "110000",
          "description": "市",
          "level": "1",
          "name": "北京"
        }
      ],
      "pre_region": {
        "centroid": "1",
        "code": "1",
        "description": "1",
        "level": "1",
        "name": "1"
      },
      "sub_region": [
        {
          "centroid": "1",
          "code": "110000",
          "description": "1",
          "level": "1",
          "name": "北京",
          "sub_region": [
            {
              "centroid": "1",
              "code": "1",
              "description": "1",
              "level": "1",
              "name": "1",
              "sub_region": [
                {
                  "centroid": "[1.0,2.0]",
                  "code": "1",
                  "description": "1",
                  "level": "1",
                  "name": "1",
                  "sub_region": [
                    {
                      "centroid": "1",
                      "code": "1",
                      "description": "1",
                      "level": "1",
                      "name": "1"
                    }
                  ]
                }
              ]
            }
          ]
        }
      ]
    },
    "update_time": "123456789",
    "version": "1.0.0"
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
  "sub_code": "isv.business-failed:400",
  "sub_msg": "参数错误"
}
```

## 备注
