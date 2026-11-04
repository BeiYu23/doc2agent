# iop.waybillUpdate

> 【厂商】代发订单更新发货接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.waybillUpdate` |
| 中文名 | 【厂商】代发订单更新发货 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/waybillUpdate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/677 |
| 更新日期 | `2021-07-18` |

## 接口说明

- 文档书: 代发API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user_id` | body | number | 是 | 代打店铺id | `65543234` |
| `distr_order_id` | body | string | 是 | 代打订单号 | `78823463242134` |
| `track_no` | body | string | 是 | 运单号 | `34324234` |
| `company_code` | body | string | 是 | 快递公司 | `jd` |
| `delivery_id` | body | string | 是 | 运单id | `32423` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillUpdate?app_key=your_appkey_here&method=iop.waybillUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `return_result` | boolean | 操作结果 | `true` |
| `delivery_id` | string | 运单id | `982734` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 发货失败，请稍后重试（sub_code: isp.service-error:88888） | 发货失败，请稍后重试 |
| `50002` | 业务处理失败 / 发货失败（sub_code: isv.business-failed:41005） | 请确认代发单状态 |
| `50002` | 业务处理失败 / 代发单状态不允许发货（sub_code: isv.business-failed:41000） | 请确认代发单状态 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 请确认参数后重试 |
| `50002` | 业务处理失败 / 代发单不存在（sub_code: isv.business-failed:41002） | 请确认代发单号单是否正确 |
| `50002` | 业务处理失败 / 41004:该订单的订单状态不允许重新发货（sub_code: isv.business-failed:41004） | 41004:该订单的订单状态不允许重新发货 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_id": "982734",
    "return_result": "true"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:88888",
  "sub_msg": "发货失败，请稍后重试"
}
```

## 备注
