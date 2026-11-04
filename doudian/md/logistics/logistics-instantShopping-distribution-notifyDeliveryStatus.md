# instantShopping.distribution.notifyDeliveryStatus

> 抖音侧订单状态变更回调

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.instantShopping.distribution.notifyDeliveryStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/6585 |
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
| `update_time` | body | mixed | 是 | 状态变更时间，格式为秒时间戳 | `1716537685` |
| `rider_name` | body | string | 否 | 骑手姓名 | `"朱涛"` |
| `rider_phone` | body | string | 否 | 骑手电话 | `"13684541145"` |
| `rider_lat` | body | string | 否 | 骑手当前所在纬度（火星坐标系GCJ02） | `39.973390` |
| `rider_lng` | body | string | 否 | 骑手当前所在经度（火星坐标系GCJ02） | `116.347004` |
| `cancel_code` | body | mixed | 否 | 取消原因code，取消态必填 | `0` |
| `cancel_reason` | body | string | 否 | 取消原因描述，取消态必填 | `""` |
| `notify_time` | body | mixed | 是 | 通知时间 | `1716537685` |
| `distributor_rider_id` | body | string | 否 | 配送商骑手id | `"4575457"` |
| `cancel_price` | body | mixed | 否 | 取消费用，单位：分，取消运单时必填 | `0` |
| `delivery_reverse` | body | object | 否 | 返件相关信息 | `` |
| `  └ reverse_id` | body | mixed | 否 | 返件单ID | `7257267285` |
| `  └ status` | body | mixed | 否 | 返件状态枚举： - 返件初始化：100 - 返件中：200 - 返件完成：300 - 返件取消：400 - 无需返件：900 | `900` |
| `delivered_images` | body | string | 否 | 妥投举证图片；（图片url，如果是多个，通过逗号分隔） | `"https://media-order-jd.imdada.cn/order-finish/d640f142063a40ccb919439fc413d221.jpeg,https://media-order-jd.imdada.cn/order-finish/031652144dcf4ff6be0e15f3ab5078ee.jpeg"` |
| `delivered_desc` | body | string | 否 | 妥投描述 | `"放在家门口"` |
| `rider_im_open_status` | body | mixed | 否 | 骑手IM功能开启标记，0：未知；1：开启；2：不开启 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getCatePropertyV2?app_key=your_appkey_here&method=product.getCatePropertyV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `delivery_id` | string | 抖音运单id | `"DHT46816515646"` |
| `distributor_delivery_id` | string | 配送商运单id | `"ecom_732542145416"` |
| `notify_time` | mixed | 通知时间 | `1717397898` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2075000311:取货码同步失败（sub_code: isv.business-failed:2075000311） | 2075000311:取货码同步失败 |
| `50002` | 业务处理失败 / 1075020309:UpdateDelivery lock err（sub_code: isv.business-failed:1075020309） | 1075020309:UpdateDelivery lock err |
| `50002` | 业务处理失败 / 999001001:RPCError{PSM:[life.distribution.call_delivery] Method:[NotifyCallStatus] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[1000021001] BizStatusMessage:[呼单锁定失败]}（sub_code: isv.business-failed:999001001） | 999001001:RPCError{PSM:[life.distribution.call_delivery] Method:[NotifyCallStatus] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[1000021001] BizStatusMessage:[呼单锁定失败]} |
| `50002` | 业务处理失败 / 1075039998:服务异常，请稍后再试#（sub_code: isv.business-failed:1075039998） | 1075039998:服务异常，请稍后再试# |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "category_id": "31918",
        "cid": "31918",
        "diy_type": "1",
        "has_sub_property": "false",
        "important_type": "1",
        "measure_templates": [
          {
            "display_name": "xx模版",
            "template_id": "23",
            "value_modules": [
              {
                "input_type": "input",
                "module_id": "123",
                "prefix": "\"\"",
                "suffix": "\"\"",
                "units": [
                  {
                    "unit_id": "1",
                    "unit_name": "克"
                  }
                ],
                "validate_rule": {
                  "data_type": "integer",
                  "max": "10",
                  "min": "2",
                  "precision": "2",
                  "time_format": "YYYY-MM-DD",
                  "unit_rules": [
                    {
                      "max": "10",
                      "min": "2",
                      "unit_id": "1"
                    }
                  ]
                },
                "value_required": "true",
                "values": [
                  {
                    "value_name": "棉"
                  }
                ]
              }
            ]
          }
        ],
        "multi_select_max": "5",
        "options": [
          {
            "name": "ON:THE BODY/安宝笛",
            "sequence": "2",
            "value": "1062254699",
            "value_id": "1"
          }
        ],
        "property_id": "14133",
        "property_name": "\"材质\"",
        "property_type": "1",
        "relation_id": "1",
        "required": "0",
        "sequence": "2",
        "status": "1",
        "type": "text"
      }
    ],
    "tpl_type": "2"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2075000311",
  "sub_msg": "2075000311:取货码同步失败"
}
```

## 备注
