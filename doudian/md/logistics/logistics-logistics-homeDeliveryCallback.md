# logistics.homeDeliveryCallback

> 履约结果推送

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.homeDeliveryCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/homeDeliveryCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2731 |
| 更新日期 | `2022-12-14` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `resource_code` | body | string | 是 | 资源编码 | `shentong` |
| `waybill_no` | body | string | 是 | 运单号 | `123456789` |
| `number_calls` | body | string | 是 | 电联次数 | `1` |
| `is_connected` | body | string | 是 | 是否接通 0 未接通 1 已接通 | `1` |
| `connect_result` | body | string | 否 | 接通结果（消费者意愿） 1 要上门 2 要入柜 3 不确定 | `1` |
| `time_ring_list` | body | array | 否 | 电联明细 | `` |
| `  └ is_connected` | body | string | 否 | 是否接通 0 未接通 1 已接通 | `1` |
| `  └ time_ring` | body | string | 否 | 电联时长，单位秒 | `1` |
| `is_home_delivery` | body | string | 是 | 是否送货上门 1 本人签收 2 家人代签 3 朋友代签 4 入柜 5 入驿站 6 入超市等代收点 7 其他方代签 8 其他 | `1` |
| `home_delivery_remark` | body | string | 否 | 送货上门备注 | `送货上门备注` |
| `photograph` | body | string | 否 | 签收图片 | `图片信息` |
| `biz_type` | body | string | 否 | 业务场景 HomeDelivery -- 音需达 SignAndReturn -- 签单返回 FakeSign--派前电联 | `SignAndReturn` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/homeDeliveryCallback?app_key=your_appkey_here&method=logistics.homeDeliveryCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
