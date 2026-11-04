# supplyCenter.order.logistics

> 精选货源发货状态数据同步

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.order.logistics` |
| 中文名 | 精选货源发货状态数据同步 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5321 |
| 更新日期 | `2023-11-17` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pur_order_id` | body | string | 是 | 精选货源订单号 | `123` |
| `express_type` | body | string | 是 | 发货类型 1 整单发货 2 分单发货 | `1` |
| `pack_info` | body | object | 否 | 分单发货必传 | `` |
| `  └ shipped_pur_sub_orders` | body | array | 否 | 精选货源子订单号列表 | `12` |
| `express_time` | body | number | 是 | 发货时间，秒级时间戳 | `1698146585` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.order.logistics&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
