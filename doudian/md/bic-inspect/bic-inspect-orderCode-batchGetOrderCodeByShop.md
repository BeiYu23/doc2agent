# 批量预绑订单码

> orderCode.batchGetOrderCodeByShop — 批量预绑订单码
批量预绑订单码，下载后订单进入预绑码状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量预绑订单码 |
| 文档地址 | `/docs/doudian/bic-inspect/bic-inspect-orderCode-batchGetOrderCodeByShop` |
| 接口 ID | `doudian.bic-inspect.orderCode.batchGetOrderCodeByShop` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/batchGetOrderCodeByShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/51/1872 |
| 更新日期 | `2024-08-01` |

## 接口说明

- 文档书: BIC质检API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_ids` | body | array | 是 | 订单号列表 | `4652554264337710006, 4652998694668485077` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `batch_data` | array | 订单码数据 | `` |
| `delivery_type` | number | 送检方式 | `0` |
| `ship_type` | number | 出仓方式 | `3` |
| `reinspection_quota` | number | 当前复检额度 | `500` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
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
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "存在未维护sku的订单"
}
```

## 备注
