# warehouse.createFence

> 创建电子围栏

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.warehouse.createFence` |
| 中文名 | 创建电子围栏 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/createFence` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/1778 |
| 更新日期 | `2024-06-11` |

## 接口说明

- 文档书: 库存API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fence_info` | body | object | 是 | 围栏信息 | `` |
| `  └ out_fence_id` | body | string | 是 | 外部围栏id，必传 | `fenceid01` |
| `  └ shape` | body | mixed | 是 | 形状 1. 圆 使用circular 2:多边形，使用polygon  3:带洞多边形（兼容普通多边形），使用polygon_new  4:多个多边形，兼容带洞和不带洞，使用multi_polygons | `1` |
| `  └ circular` | body | object | 否 | 形状为圆的经纬度信息，对应shape=1 | `` |
| `    └ center` | body | object | 是 | 圆的中心经纬度 | `` |
| `      └ longitude` | body | string | 是 | 经度 | `115.35644` |
| `      └ latitude` | body | string | 是 | 纬度 | `40.438585` |
| `    └ radius` | body | string | 是 | 半径，单位 米 | `1000` |
| `  └ polygon` | body | object | 否 | 普通多边形 ，对应shape=2 | `` |
| `    └ vertices` | body | array | 是 | 多边形顶点的经纬度：逆时针 | `` |
| `      └ longitude` | body | string | 是 | 经度 | `115.356445` |
| `      └ latitude` | body | string | 是 | 纬度 | `40.438585` |
| `  └ polygon_new` | body | object | 否 | 带洞多边形，可兼容普通多边形 ，对应shape=3 | `` |
| `    └ outer` | body | object | 是 | 带洞多边形的外圈数据 | `` |
| `      └ vertices` | body | array | 是 | 经纬度列表，外圈为逆时针 | `` |
| `        └ longitude` | body | string | 是 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 是 | 纬度 | `40.438585` |
| `    └ inner` | body | array | 否 | 带洞多边形的内圈数据，空表示普通多边形 | `` |
| `      └ vertices` | body | array | 否 | 经纬度列表，内圈为顺时针 | `` |
| `        └ longitude` | body | string | 否 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 否 | 纬度 | `40.438585` |
| `  └ multi_polygons` | body | array | 否 | 多个多边形 ，对应shape=4 | `` |
| `    └ outer` | body | object | 是 | 带洞多边形的外圈数据 | `` |
| `      └ vertices` | body | array | 是 | 经纬度列表，外圈为逆时针 | `` |
| `        └ longitude` | body | string | 是 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 是 | 纬度 | `40.438585` |
| `    └ inner` | body | array | 否 | 带洞多边形的内圈数据，空表示普通多边形 | `` |
| `      └ vertices` | body | array | 否 | 经纬度列表，内圈为顺时针 | `` |
| `        └ longitude` | body | string | 否 | 经度 | `115.356445` |
| `        └ latitude` | body | string | 否 | 纬度 | `115.356445` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/createFence?app_key=your_appkey_here&method=warehouse.createFence&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fence_id` | string | 内部围栏id | `49227991164292065165` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:2） | 检查参数 |
| `50002` | 业务处理失败 / 该电子围栏已经存在（sub_code: isv.business-failed:1006） | 使用修改接口 |
| `20000` | 系统错误 / 内部错误（如果是 edge xx crosses edge xx，那就是围栏数据不对，边有交叉，不是个合法的多边形，检查数据）（sub_code: isp.service-error:9999） | 重试 |
| `50002` | 业务处理失败 / 保存失败（sub_code: isv.business-failed:1212030362） | 检查数据 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:2122） | 检查参数 |
| `50002` | 业务处理失败 / 该电子围栏已经存在（sub_code: isv.business-failed:2121006） | 使用修改接口 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:2129999） | 重试 |
| `20000` | 系统错误 / 服务器打瞌睡了，请稍后再试。（sub_code: isp.service-error:6001001） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "fence_id": "49227991164292065165"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:2",
  "sub_msg": "参数错误"
}
```

## 备注
