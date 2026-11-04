# 骑手上报异常

> instantShopping.distribution.exceptionReport — 骑手上报异常

| 元信息 | 值 |
| --- | --- |
| 中文名 | 骑手上报异常 |
| 文档地址 | `/docs/doudian/logistics/logistics-instantShopping-distribution-exceptionReport` |
| 接口 ID | `doudian.logistics.instantShopping.distribution.exceptionReport` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/6584 |
| 更新日期 | `2024-06-14` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `delivery_id` | body | string | 是 | 抖音运单id(以此id为主) | `"a_7372453214286987305"` |
| `distributor_delivery_id` | body | string | 是 | 配送商运单id | `"DH2024052459066015"` |
| `distributor_code` | body | string | 是 | 抖音为每个配送商分配的标识信息 | `"MOCK_DELIVERY"` |
| `status` | body | mixed | 是 | 运单状态，见附录F02 | `102` |
| `rider_name` | body | string | 是 | 骑手姓名 | `"朱涛"` |
| `rider_phone` | body | string | 是 | 骑手电话 | `"13168887777"` |
| `rider_lat` | body | string | 是 | 骑手位置纬度 （火星坐标系GCJ02） | `39.980042` |
| `rider_lng` | body | string | 是 | 骑手位置经度 （火星坐标系GCJ02） | `116.374061` |
| `exception_time` | body | mixed | 是 | 骑手上报运单异常的时间，时间戳(秒) | `1716538402` |
| `audit_time` | body | mixed | 否 | 异常上报审核通过时间，时间戳(秒) | `1716538420` |
| `exception_code` | body | mixed | 是 | 骑手选择的异常场景code，详见：F07:  配送商异常CODE | `30000` |
| `exception_name` | body | string | 是 | 骑手选择的异常场景 | `"车辆故障/没电/事故"` |
| `exception_descr` | body | string | 否 | 骑手填写的异常描述 | `"电瓶车故障"` |
| `exception_images` | body | string | 否 | 骑手上传的图片url-list，特定异常场景下，必传(逗号分割的字符串，list先传进来时骑手第一张发布的图片) | `"https://loc-1258916733.cos.ap-shanghai.myqcloud.com/orderpic/6bc5fb1d13f43c565245a2c3d7e87882.jpeg?sign=q-sign-algorithm%3Dsha1%26q-ak%3DYOUR_ACCESS_KEY_ID%26q-sign-time%3D1717376767%3B1719968827%26q-key-time%3D1717376767%3B1719968827%26q-header-list%3Dhost%26q-url-param-list%3D%26q-signature%3D4eb4639571763578fb52aacc118099d515b3cf77"` |
| `expect_time` | body | mixed | 否 | 新的预计送达时间，时间戳(秒) | `1716539958` |
| `notify_time` | body | mixed | 是 | 系统通知时间，时间戳(秒) | `1716538423` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.distribution.exceptionReport&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `delivery_id` | string | 抖音运单id | `"a_7372453214286987305"` |
| `distributor_delivery_id` | string | 配送商运单id | `"DH2024052459066015"` |
| `notify_time` | mixed | 通知时间 | `1716538423` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_id": "\"a_7372453214286987305\"",
    "distributor_delivery_id": "\"DH2024052459066015\"",
    "notify_time": "1716538423"
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
