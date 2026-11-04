# 获取电子围栏信息/列表

> warehouse.getFences — 获取电子围栏信息/列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取电子围栏信息/列表 |
| 文档地址 | `/docs/doudian/shop/shop-warehouse-getFences` |
| 接口 ID | `doudian.shop.warehouse.getFences` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/getFences` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/1783 |
| 更新日期 | `2024-06-11` |

## 接口说明

- 文档书: 店铺API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_fence_id_list` | body | array | 否 | 外部围栏id列表，不填则查全部 | `fenceid2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/getFences?app_key=your_appkey_here&method=warehouse.getFences&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fences` | array | 围栏信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2） | 修改后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:9999） | 重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2122） | 修改后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:2129999） | 重试 |
| `20000` | 系统错误（sub_code: isp.service-error:2121006） | 重试，重试失败联系管理员 |

## 响应示例

成功：

```json
{
  "data": {
    "fences": [
      {
        "circular": {
          "center": {
            "latitude": "40.438585",
            "longitude": "115.356445"
          },
          "radius": "1000"
        },
        "fence_id": "1312312313",
        "multi_polygons": [
          {
            "inner": [
              {
                "vertices": [
                  {
                    "latitude": "40.438585",
                    "longitude": "115.356445"
                  }
                ]
              }
            ],
            "outer": {
              "vertices": [
                {
                  "latitude": "40.438585",
                  "longitude": "115.356445"
                }
              ]
            }
          }
        ],
        "out_fence_id": "fence02",
        "polygon": {
          "vertices": [
            {
              "latitude": "40.438585",
              "longitude": "115.356445"
            }
          ]
        },
        "polygon_new": {
          "inner": [
            {
              "vertices": [
                {
                  "latitude": "40.438585",
                  "longitude": "115.356445"
                }
              ]
            }
          ],
          "outer": {
            "vertices": [
              {
                "latitude": "40.438585",
                "longitude": "115.356445"
              }
            ]
          }
        },
        "shape": "2"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "参数错误"
}
```

## 备注
