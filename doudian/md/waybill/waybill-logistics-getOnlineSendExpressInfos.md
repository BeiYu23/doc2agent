# 在线寄件询价

> logistics.getOnlineSendExpressInfos — 在线寄件询价接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 在线寄件询价 |
| 文档地址 | `/docs/doudian/waybill/waybill-logistics-getOnlineSendExpressInfos` |
| 接口 ID | `doudian.waybill.logistics.getOnlineSendExpressInfos` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getOnlineSendExpressInfos` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/4831 |
| 更新日期 | `2023-10-09` |

## 接口说明

- 文档书: 电子面单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sender_address` | body | object | 是 | 寄件地址 | `` |
| `  └ province_name` | body | string | 是 | 寄件省 | `北京市` |
| `  └ city_name` | body | string | 是 | 寄件市 | `北京市` |
| `  └ district_name` | body | string | 是 | 寄件区 | `海淀区` |
| `  └ street_name` | body | string | 否 | 寄件街道 | `中关村街道` |
| `  └ detail_address` | body | string | 是 | 寄件详细地址 | `地震局` |
| `order_infos` | body | array | 是 | 订单列表 | `` |
| `  └ order_id` | body | string | 是 | 抖音订单号 | `123` |
| `  └ insured_amount` | body | number | 否 | 保价金额，单位分 | `100` |
| `  └ package_weight` | body | number | 是 | 包裹重量，单位克，默认填300 | `3000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getOnlineSendExpressInfos?app_key=your_appkey_here&method=logistics.getOnlineSendExpressInfos&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `express_infos` | array | 各物流商报价信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:4006） | 根据错误提示检查入参 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:4007） | 检查文案或重试 |
| `40004` | 非法的参数 / 订单信息不存在（sub_code: isv.parameter-invalid:15002） | 检查订单号是否真实抖音订单号 |
| `20000` | 系统错误 / 查询订单信息失败（sub_code: isp.service-error:15000） | 检查订单号是否真实抖音订单号或重试 |
| `50002` | 业务处理失败 / 发货地暂无可用服务商（sub_code: isv.business-failed:131000） | 可做友好提示：您的发货地暂无可用服务商，城市陆续开通中，敬请期待 |

## 响应示例

成功：

```json
{
  "data": {
    "express_infos": [
      {
        "cut_off_time": "15:04",
        "express": "jtexpress",
        "price_infos": [
          {
            "insured_amount": "100",
            "logistics_cost": "100",
            "order_id": "123",
            "package_weight": "1000",
            "receive_city": "北京市",
            "send_city": "北京市"
          }
        ],
        "recommended_reason": "1",
        "total_cost": "200",
        "total_insured_amount": "100",
        "total_logistics_cost": "100"
      }
    ]
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
  "sub_code": "isv.parameter-invalid:4006",
  "sub_msg": "参数异常"
}
```

## 备注
