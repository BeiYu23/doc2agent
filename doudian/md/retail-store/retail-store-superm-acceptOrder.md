# superm.acceptOrder

> 超市小时达接单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.acceptOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/acceptOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2959 |
| 更新日期 | `2023-09-19` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 门店id | `1123456` |
| `shop_order_id` | body | string | 是 | 店铺单id | `3157462748578289376209` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wmsOutbound/create?app_key=your_appkey_here&method=yunc.wmsOutbound.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `50002` | 业务处理失败 / 90001:暂无接口调用权限，系统默认自动接单，如有疑问请联系客户经理咨询（sub_code: isv.business-failed:90001） | 暂无接口调用权限，系统默认自动接单，如有疑问请联系客户经理咨询 |
| `50002` | 业务处理失败 / 90008:系统繁忙，请稍后重试（sub_code: isv.business-failed:90008） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 90000:系统繁忙，请稍后重试（sub_code: isv.business-failed:90000） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 700007:查询订单详情错误（sub_code: isv.business-failed:700007） | 查询订单详情错误 |
| `50002` | 业务处理失败 / 90007:该订单状态非备货中或部分发货，不能操作接单（sub_code: isv.business-failed:90007） | 90007:该订单状态非备货中或部分发货，不能操作接单 |
| `50002` | 业务处理失败 / 90005:该订单已取消，不能操作接单（sub_code: isv.business-failed:90005） | 90005:该订单已取消，不能操作接单 |
| `50002` | 业务处理失败 / 90004:该订单已发货，不能操作接单（sub_code: isv.business-failed:90004） | 90004:该订单已发货，不能操作接单 |
| `50002` | 业务处理失败 / 90006:该订单已完结，不能操作接单（sub_code: isv.business-failed:90006） | 90006:该订单已完结，不能操作接单 |
| `50002` | 业务处理失败 / 90013:系统繁忙，请稍后重试（sub_code: isv.business-failed:90013） | 90013:系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 90009:非本店铺订单，不允许操作，请核对订单后操作（sub_code: isv.business-failed:90009） | 90009:非本店铺订单，不允许操作，请核对订单后操作 |
| `50002` | 业务处理失败 / 90010:非本门店订单，不允许对该订单操作（sub_code: isv.business-failed:90010） | 90010:非本门店订单，不允许对该订单操作 |

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
