# instantShopping.starhub.updateRelayReverseOrderStatus

> 同步逆向接力单状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.instantShopping.starhub.updateRelayReverseOrderStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6546 |
| 更新日期 | `2024-05-27` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `relay_order_id` | body | string | 是 | 抖音逆向接力单id | `"4732894793824719"` |
| `status` | body | mixed | 是 | 抖音逆向接力单当前状态 | `110` |
| `weight` | body | mixed | 否 | 单据货品总毛重，（后续结算需要），单位mg | `120000` |
| `failure_cause` | body | mixed | 否 | 失败原因 （在更新状态=400场景为必填） | `1` |
| `operator_id` | body | string | 否 | 操作人id | `"123"` |
| `operator_name` | body | string | 否 | 操作人姓名 | `"xxx"` |
| `update_time` | body | mixed | 是 | 状态更新时间 | `1715686939` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.starhub.updateRelayReverseOrderStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法入参（sub_code: isv.parameter-invalid:40001） | 请传入合法入参 |
| `50002` | 业务处理失败 / 不存在的逆向接力单（sub_code: isv.business-failed:40004） | 请传入正确的逆向接力单id |
| `40004` | 非法的参数 / 没有权限操作逆向接力单（sub_code: isv.parameter-invalid:40006） | 请传入正确的逆向接力单id |

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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "非法入参"
}
```

## 备注
