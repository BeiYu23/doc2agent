# supplyCenter.order.confirm

> 精选货源采购单推进确认收货状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.order.confirm` |
| 中文名 | 精选货源采购单推进确认收货状态 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/order/confirm` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5320 |
| 更新日期 | `2023-11-17` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pur_order_id` | body | string | 是 | 采购单号 | `12345` |
| `confirm_time` | body | number | 是 | 确认收货时间，秒级时间戳 | `1698146585` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.order.confirm&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
