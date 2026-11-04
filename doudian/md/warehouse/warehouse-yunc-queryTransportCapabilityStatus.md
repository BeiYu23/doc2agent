# yunc.queryTransportCapabilityStatus

> 运力配送状态查询接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.queryTransportCapabilityStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/queryTransportCapabilityStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/3584 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `platform_order_no` | body | string | 是 | 店铺父订单号 | `1111111` |
| `out_order_no` | body | string | 是 | ERP单号 | `22222` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/queryTransportCapabilityStatus?app_key=your_appkey_here&method=yunc.queryTransportCapabilityStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20001` | 内部服务超时 / 1103:请求内部服务超时（sub_code: isp.service-timeout-error:1103） | 请重试！ |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "logistics_track_no": "44444",
      "occurred_time": "2023-04-18 14:48:13",
      "out_order_no": "22222",
      "platform_order_no": "111111",
      "rider_latitude": "66.28",
      "rider_longitude": "103.44",
      "rider_name": "李四",
      "rider_phone": "13444444444",
      "service_provider": "shenzhenshishun",
      "shipment_error": "1001",
      "shipment_status": "1",
      "shop_id": "12345",
      "store_id": "45678",
      "to_aoi_name": "test",
      "track_no": "33333"
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
  "code": 20001,
  "msg": "内部服务超时",
  "sub_code": "isp.service-timeout-error:1103",
  "sub_msg": "1103:请求内部服务超时"
}
```

## 备注
