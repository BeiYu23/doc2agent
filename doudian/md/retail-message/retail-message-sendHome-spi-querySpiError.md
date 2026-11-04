# sendHome.spi.querySpiError

> 到家查询spi最终持久化失败落库记录

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-message.sendHome.spi.querySpiError` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sendHome/spi/querySpiError` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1534/6774 |
| 更新日期 | `2024-08-15` |

## 接口说明

- 文档书: 消息管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `timestamp_start` | body | mixed | 否 | 时间戳开始时间，单位秒 | `1719989305` |
| `timestamp_end` | body | mixed | 否 | 时间戳结束时间，单位秒 | `1719989305` |
| `biz_key` | body | string | 否 | 业务key,例如商品id、订单id | `36884262250` |
| `page_no` | body | mixed | 是 | 第几页(从1开始) | `1` |
| `page_size` | body | mixed | 是 | 每页条数,最大为100 | `10` |
| `spi_type` | body | mixed | 否 | SPI场景类型 1 //订单支付 2 //订单完成 3 //商家接单 4 //商家拒单 5 // 用户申请退款,待商家审核 6 // 退款审核结果(已同意/拒绝退款) 7 // 退款成功 8 // 订单已取消 9 // 退款修改 10 // 退款关闭 21 // 商品状态变化 31 //运力状态变更 101 //（生服）订单支付 105/ / （生服）用户申请退款,待商家审核 | `21` |
| `status` | body | array | 否 | 0-未处理；1-处理成功, 未传默认未处理 | `[0,1]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sendHome.spi.querySpiError&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `100` |
| `has_more` | boolean | 是否还能查询更多 | `true` |
| `spi_notify_list` | array | 推送的详情信息，和spi推送中的业务参数是对齐的 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5100001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5100002） | 系统异常，可尝试重试 |

## 响应示例

成功：

```json
{
  "data": {
    "has_more": "true",
    "spi_notify_list": [
      {
        "id": "11111",
        "spi_notify_data": "{data:\"\"}"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.parameter-invalid:4100003",
  "sub_msg": "参数非法"
}
```

## 备注
