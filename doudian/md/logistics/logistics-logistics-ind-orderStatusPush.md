# logistics.ind.orderStatusPush

> 订单状态回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.ind.orderStatusPush` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/ind/orderStatusPush` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2456 |
| 更新日期 | `2023-04-24` |

## 接口说明

- 文档书: 物流发货API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_order_id` | body | string | 是 | 承运商单据号 | `xx123456` |
| `transport_order_id` | body | string | 是 | 抖音单据号 | `DY123456` |
| `order_status` | body | string | 是 | 订单状态(待接单＝1,配送员接单＝2,配送员到店＝3,配送员取货=4,配送员配送中=5,已取消＝6,订单逆向返回中=7, 订单逆向返回完成=8,骑手更换=9,订单妥投=10 | `1` |
| `exception_status` | body | object | 否 | 异常情况 | `` |
| `  └ status` | body | string | 是 | 订单拒收=1,配送异常=2 | `1` |
| `  └ reason` | body | string | 是 | 配送异常feature：订单拒收=1,配送异常=2 配送异常feature： { 1001,商家出货慢, 1002,商家出错货, 1003,商家缺货, 2001,破损, 2002,丢失, 2003,骑手取错货, 2004,骑手无法送达 3001,小票码错误, 3002,商家地址错误, 3003,消费者地址错误, 3004, 订单重量偏差过大, 4001,消费者拒收, 4002,消费者电话未接通, 4003,消费者不在家, 4004,消费者线下联系修改地址, 5001,其他 } | `1001` |
| `estimate_sign_time` | body | number | 否 | 计划应妥投时间，时间戳 | `1663294915` |
| `estimate_fetch_time` | body | number | 否 | 计划应取件时间 | `1663294915` |
| `rider` | body | object | 否 | 骑手信息 | `` |
| `  └ rider_code` | body | string | 否 | 骑手id | `骑手id` |
| `  └ rider_name` | body | string | 否 | 骑手name | `骑手name` |
| `  └ temperature` | body | string | 否 | 骑手温度 | `骑手温度` |
| `  └ vaccine` | body | string | 否 | 骑手疫苗情况  0=未接种,1=一针,2=2针,3=3针 | `骑手疫苗接种情况` |
| `  └ covid_report` | body | string | 否 | 骑手健康码情况 0 - 绿码且24h内核酸 1 - 绿码且48h内核酸 2 - 绿码且48h外核酸 3 - 黄码 4 - 红码 | `骑手健康码情况` |
| `  └ contact` | body | object | 否 | 骑手联系方式 | `` |
| `    └ name` | body | string | 否 | 姓名 | `张三` |
| `    └ mobile` | body | string | 否 | 电话 | `电话` |
| `    └ tel` | body | string | 否 | 手机号码 | `18294311234` |
| `location` | body | object | 否 | 骑手位置信息 | `` |
| `  └ longitude` | body | string | 是 | 经度 | `111.23` |
| `  └ latitude` | body | string | 是 | 维度 | `111.32` |
| `  └ standard` | body | string | 是 | 使用的地图 | `GaoDe` |
| `update_time` | body | number | 是 | 本次状态流更新时间 | `1663294915` |
| `logistics_out_order_id` | body | string | 否 | 承运商单据号，电子面单号、用作打印面单使用 | `承运商单据号，电子面单号、用作打印面单使用` |
| `to_aoi_name` | body | string | 否 | 接驳商圈名称，接驳模式下运力服务商返回的接驳商圈，需要在面单打印 | `接驳商圈名称，接驳模式下运力服务商返回的接驳商圈，需要在面单打印` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/addresSwitchConfig?app_key=your_appkey_here&method=order.addresSwitchConfig&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `return_code` | string | 错误码，0表示成功 | `0` |
| `message` | string | 错误消息，失败时填写 | `数据插入失败` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "authorized_status": "0"
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
