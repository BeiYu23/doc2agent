# superm.rejectOrder

> 超市小时达拒单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.rejectOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/rejectOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2960 |
| 更新日期 | `2023-09-19` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 门店id | `234223` |
| `shop_order_id` | body | string | 是 | 店铺单id | `123321354314315341` |
| `reason_code` | body | number | 是 | 拒单原因 | `12` |
| `reason_mark` | body | string | 否 | 拒绝备注 | `没货了` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=yunc.erp.outbound.callbackToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20201） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50120） | 店铺未在灰度中，不存在接单和未接单状态 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50121） | 履约状态不允许变更 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50122） | 拒绝系统拒单的操作 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50123） | 订单已发货，不允许拒单/接单 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50124） | 订单已取消，无需拒单/接单 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50125） | 订单已完结，不允许拒单/接单 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40101） | 传入履约的参数错误（需商家后台排查） |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:90008） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 该订单已取消，无需操作取消订单（sub_code: isv.business-failed:90005） | 该订单已取消，无需操作取消订单 |
| `50002` | 业务处理失败 / 90011:请选择正确的拒单原因（sub_code: isv.business-failed:90011） | 90011:请选择正确的拒单原因 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40100",
  "sub_msg": "参数错误"
}
```

## 备注
