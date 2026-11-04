# order.checkPreDelivery

> 查询商家/订单是否可用预发货。如果不传订单ID，则查询店铺维度预发货判定结果。如果传了订单ID，则查询订单维度预发货判定结果。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.order.checkPreDelivery` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/checkPreDelivery` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/8212 |
| 更新日期 | `2026-04-22` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 否 | 订单ID | `112233` |
| `extra` | body | string | 否 | 扩展信息 | `{}` |
| `ware_mode` | body | string | 否 | 仓模式, 枚举值：self 自有仓 cloud 云仓 hybrid 混合仓 | `cloud` |
| `daily_audit_times` | body | string | 否 | 商家每日审单次数 | `3` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/outbound/create?app_key=your_appkey_here&method=yunc.wms.outbound.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `can_pre_delivery` | boolean | 是否允许预发货 | `false` |
| `reason` | string | 原因说明 | `店铺存在虚假发货违规单` |

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
