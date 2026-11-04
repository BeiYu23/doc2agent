# afterSale.addOrderRemark

> 店家给售后单添加备注

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.addOrderRemark` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/addOrderRemark` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/585 |
| 更新日期 | `2021-06-10` |

## 接口说明

- 文档书: 售后退款API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 订单ID，与售后单ID二选一传入 | `12345` |
| `after_sale_id` | body | string | 否 | 售后单ID，与订单ID二选一传入，二者均传入时售后单ID的优先级更高 | `12345` |
| `remark` | body | string | 是 | 商家添加的备注信息 | `"客户情绪较激动，需要立即处理"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/addOrderRemark?app_key=your_appkey_here&method=afterSale.addOrderRemark&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统错误，请重试（sub_code: isv.business-failed:10000） | 系统错误，请重试 |
| `50002` | 业务处理失败 / 未填写备注（sub_code: isv.business-failed:11000） | 请填写备注信息 |
| `50002` | 业务处理失败 / 该售后单不存在（sub_code: isv.business-failed:11003） | 请检查售后单信息 |
| `50002` | 业务处理失败 / 查询退款记录失败，请稍后重试（sub_code: isv.business-failed:12000） | 查询退款记录失败，请稍后重试 |

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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "系统错误，请重试"
}
```

## 备注
