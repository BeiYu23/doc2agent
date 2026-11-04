# orderCode.downloadOrderCodeByShop

> 预绑订单码，下载后订单进入预绑码状态【请勿使用该接口查询订单信息！！！】

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bic-inspect.orderCode.downloadOrderCodeByShop` |
| 中文名 | 预绑订单码 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/downloadOrderCodeByShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/51/1871 |
| 更新日期 | `2024-08-01` |

## 接口说明

- 文档书: BIC质检API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | number | 是 | 订单id | `4652554264338243781` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_success` | string | 是否成功 | `SUCCESS` |
| `error_desc` | string | 错误信息 | `找不到对应订单` |
| `delivery_type` | number | 送检方式 | `0` |
| `ship_type` | number | 出仓方式 | `1` |
| `order_code` | string | 订单码 | `0704798730` |
| `reinspection_quota` | number | 当前复检额度 | `500` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单处理中（sub_code: isv.business-failed:1001） | 请稍后重试 |
| `50002` | 业务处理失败 / 存在未维护sku的订单（sub_code: isv.business-failed:-1） | 需要维护sku |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:1001",
  "sub_msg": "订单处理中"
}
```

## 备注
