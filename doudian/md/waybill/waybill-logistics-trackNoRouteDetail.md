# 查询条件

> logistics.trackNoRouteDetail — 查询条件：
1、必须是通过抖音电子面单获取的单号并且调用过发货接口回传的运单号才可以查询到物流轨迹；

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询条件 |
| 文档地址 | `/docs/doudian/waybill/waybill-logistics-trackNoRouteDetail` |
| 接口 ID | `doudian.waybill.logistics.trackNoRouteDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/trackNoRouteDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1851 |
| 更新日期 | `2021-08-18` |

## 接口说明

- 文档书: 电子面单API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 是 | 物流商编码；需使用【/order/logisticsCompanyList】接口响应参数中的code； | `shentong` |
| `track_no` | body | string | 是 | 运单号；可使用电子面单接口获取返回的单号查询【/logistics/newCreateOrder】或商家店铺后台查看 | `78393454` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/trackNoRouteDetail?app_key=your_appkey_here&method=logistics.trackNoRouteDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `route__node_list` | array | 轨迹信息 | `` |
| `track_info` | object | 运单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 订单已取消，不允许变更（sub_code: isv.parameter-invalid:10901） | - |
| `50002` | 业务处理失败 / 非抖音电商电子面单不支持查询轨迹（sub_code: isv.business-failed:10015） | - |
| `50002` | 业务处理失败 / 请求内部服务超时，请重试（sub_code: isv.business-failed:4007） | 请稍后重试 |
| `50002` | 业务处理失败 / 记录不存在（sub_code: isv.business-failed:-10004） | - |
| `50002` | 业务处理失败 / 服务器开了小差，请稍后重试（sub_code: isv.business-failed:-10006） | 请稍后重试 |
| `50002` | 业务处理失败 / 运单号不能为空（sub_code: isv.business-failed:4006） | 请检查运单号信息 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:-10001） | 请检查请求参数 |

## 响应示例

成功：

```json
{
  "data": {
    "route__node_list": [
      {
        "content": "配送中",
        "site_name": "北京",
        "state": "1",
        "state_description": "配送",
        "timestamp": "161324234234"
      }
    ],
    "track_info": {
      "express": "shentong",
      "track_no": "234234234"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:10901",
  "sub_msg": "订单已取消，不允许变更"
}
```

## 备注
