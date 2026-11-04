# afterSale.applyLogisticsIntercept

> 申请物流拦截

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.applyLogisticsIntercept` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/applyLogisticsIntercept` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/897 |
| 更新日期 | `2022-11-25` |

## 接口说明

- 文档书: 售后退款API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `after_sale_id` | body | number | 是 | 售后单ID | `12345` |
| `op_from` | body | string | 是 | 操作来源（1:商家  3:客服） | `1` |
| `intercept_targets` | body | array | 是 | 要拦截的包裹 | `` |
| `  └ company_code` | body | string | 是 | 物流公司编码 | `yuantong` |
| `  └ tracking_no` | body | string | 是 | 物流单号 | `YT1387990014325` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `intercept_results` | array | 物流拦截结果 | `` |
| `success_count` | number | 拦截成功次数 | `0` |
| `failed_count` | number | 拦截失败次数 | `1` |
| `unavailable_reason_code` | number | 不可拦截编码(failed_count=1时有意义) | `-10006` |
| `unavailable_reason` | string | 不可拦截原因(failed_count=1时有意义) | `服务器开了小差，请稍后重试` |
| `refund_amount` | number | 售后单退款总金额 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 信息获取失败，请稍后重试（sub_code: isv.business-failed:10000） | 重试 |
| `50002` | 业务处理失败 / 12001:售后类型不支持快递拦截（sub_code: isv.business-failed:12001） | 12001:售后类型不支持快递拦截 |

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
  "sub_msg": "信息获取失败，请稍后重试"
}
```

## 备注
