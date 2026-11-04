# 运单轨迹查询

> instantShopping.logistics.trackNoRouteDetail — 运单轨迹查询接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 运单轨迹查询 |
| 文档地址 | `/docs/doudian/retail-logistics/retail-logistics-instantShopping-logistics-trackNoRouteDetail` |
| 接口 ID | `doudian.retail-logistics.instantShopping.logistics.trackNoRouteDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1530/7381 |
| 更新日期 | `2025-03-25` |

## 接口说明

- 文档书: 物流发货API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 是 | 物流商编码；需使用【/order/logisticsCompanyList】接口响应参数中的code； | `shentong` |
| `track_no` | body | string | 是 | 运单号；可使用电子面单接口获取返回的单号查询【YOUR_SECRET_KEY】或商家店铺后台查看 | `78393454` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logistics.trackNoRouteDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `route_node_list` | array | 轨迹信息 | `` |
| `track_info` | object | 运单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 运单号不能为空、物流商不能为空（sub_code: isv.parameter-invalid:40001） | - |
| `20000` | 系统错误 / 服务异常（sub_code: isp.service-error:50020） | 请稍后重试 |
| `50002` | 业务处理失败 / 非即时零售电子面单不支持（sub_code: isv.business-failed:40004） | 切换取号的店铺授权后来查询 |
| `50002` | 业务处理失败 / 店铺无该运单号权限（sub_code: isv.business-failed:40006） | 请检查运单号 |

## 响应示例

成功：

```json
{
  "data": {
    "route_node_list": [
      {
        "content": "配送",
        "site_name": "1",
        "state": "配送中",
        "state_description": "配送",
        "timestamp": "161324234"
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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "运单号不能为空、物流商不能为空"
}
```

## 备注
