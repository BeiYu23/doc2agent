# warehouse.setFence

> 更新电子围栏接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.warehouse.setFence` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/setFence` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/1784 |
| 更新日期 | `2024-08-20` |

## 接口说明

- 文档书: 店铺API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fence_info` | body | object | 否 | 围栏信息 | `` |
| `  └ out_fence_id` | body | string | 是 | 外部围栏id，如果传入门店id，该字段请填为0。 | `fence01` |
| `  └ shape` | body | mixed | 是 | 形状 1. 圆  2:多边形  3:带洞多边形（兼容普通多边形）4:多个多边形，兼容带洞和不带洞 | `形状` |
| `  └ circular` | body | object | 否 | 形状为圆的经纬度信息 | `` |
| `    └ center` | body | object | 是 | 圆的中心经纬度 | `` |
| `      └ longitude` | body | string | 是 | 经度 | `115.35644` |
| `      └ latitude` | body | string | 是 | 纬度 | `40.438585` |
| `    └ radius` | body | string | 是 | 半径，单位 米 | `1000` |
| `  └ polygon` | body | object | 否 | 普通多边形 | `` |
| `    └ vertices` | body | array | 是 | 多边形顶点的经纬度：逆时针 | `` |
| `      └ longitude` | body | string | 是 | 经度 | `115.356445` |
| `      └ latitude` | body | string | 是 | 纬度 | `40.438585` |
| `  └ polygons` | body | array | 否 | 该字段已废弃，如需使用多多边形，请使用polygon_new | `` |
| `    └ vertices` | body | array | 是 | 多边形顶点 | `` |
| `      └ longitude` | body | string | 否 | 无用字段 | `dd` |
| `      └ latitude` | body | string | 否 | 无用字段 | `dd` |
| `  └ polygon_new` | body | object | 否 | 带洞多边形，可兼容普通多边形 | `` |
| `    └ outer` | body | object | 是 | 带洞多边形的外圈数据 | `` |
| `      └ vertices` | body | array | 是 | 经纬度列表，外圈为逆时针 | `` |
| `        └ longitude` | body | string | 否 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 否 | 纬度 | `40.438585` |
| `    └ inner` | body | array | 否 | 带洞多边形的内圈数据，空表示普通多边形 | `` |
| `      └ vertices` | body | array | 是 | 经纬度列表，内圈为顺时针 | `` |
| `        └ longitude` | body | string | 否 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 否 | 纬度 | `40.438585` |
| `  └ multi_polygons` | body | array | 否 | 多个多边形 | `` |
| `    └ outer` | body | object | 是 | 带洞多边形的外圈数据 | `` |
| `      └ vertices` | body | array | 是 | 经纬度列表，外圈为逆时针 | `` |
| `        └ longitude` | body | string | 否 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 否 | 纬度 | `40.438585` |
| `    └ inner` | body | array | 否 | 带洞多边形的内圈数据，空表示普通多边形 | `` |
| `      └ vertices` | body | array | 是 | 经纬度列表，内圈为顺时针 | `` |
| `        └ longitude` | body | string | 否 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 否 | 纬度 | `40.438585` |
| `  └ fence_i_d` | body | mixed | 否 | 服务内部生成的围栏id，一定会生成 | `12823223` |
| `  └ properties` | body | string | 否 | 围栏的相关的一些抽象属性（围栏名称，围栏属性：学校商圈，小区） | `{key:value}` |
| `auto_opt` | body | boolean | 否 | 是否允许平台自动处理(超出平台最大限制会被纠正), 默认不处理 | `false` |
| `store_id` | body | mixed | 否 | 门店id | `1232322` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/setFence?app_key=your_appkey_here&method=warehouse.setFence&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `limit_fence` | array | 围栏限制 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2） | 修改后重试 |
| `20000` | 系统错误 / 系统错误（如果是 edge xx crosses edge xx，那就是围栏数据不对，边有交叉，不是个合法的多边形，检查数据）（sub_code: isp.service-error:9999） | 重试 |
| `50002` | 业务处理失败 / 调用围栏空间计算服务失败（sub_code: isv.business-failed:20012） | 检查围栏是否合法 |
| `50002` | 业务处理失败 / 围栏距离门店位置太远（sub_code: isv.business-failed:1009） | 检查围栏大小位置是否合理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2122） | 修改后重试 |
| `20000` | 系统错误 / 参数错误（sub_code: isp.service-error:2129999） | 修改后重试 |
| `50002` | 业务处理失败 / 检查围栏大小是否合理（sub_code: isv.business-failed:2121006） | 调整围栏大小 |

## 响应示例

成功：

```json
{
  "data": {
    "limit_fence": [
      {
        "latitude": "24.5",
        "longitude": "116.12"
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
