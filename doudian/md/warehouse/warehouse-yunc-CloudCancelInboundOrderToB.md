# yunc.CloudCancelInboundOrderToB

> 普通入库取消

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.CloudCancelInboundOrderToB` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/CloudCancelInboundOrderToB` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1195 |
| 更新日期 | `2021-09-17` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_order_no` | body | string | 是 | 入库单号 | `564546` |
| `action_type` | body | string | 是 | 操作类型 | `1` |
| `cancel_reason` | body | string | 是 | 取消原因 | `no` |
| `order_type` | body | string | 是 | 订单类型 | `XS1RK` |
| `shop_id` | body | number | 是 | 店铺编号 | `2232` |
| `owner_code` | body | string | 否 | 货主编码 | `121` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/CloudCancelInboundOrderToB?app_key=your_appkey_here&method=yunc.CloudCancelInboundOrderToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "logistics_no": "LB148534874387439"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
