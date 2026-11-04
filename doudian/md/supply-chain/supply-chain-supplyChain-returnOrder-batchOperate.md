# supplyChain.returnOrder.batchOperate

> 批量操作售后单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.returnOrder.batchOperate` |
| 中文名 | 批量操作售后单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/4036 |
| 更新日期 | `2023-06-05` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `return_order_no_list` | body | array | 是 | 售后单号 | `"GSH123123123123"` |
| `operate_type` | body | string | 是 | 操作类型，目前支持 同意退款：CONFIRM_REFUNDD 确认收货：CONFIRM_RETURNED 拒绝售后：REJECT | `"CONFIRM_RETURNED"` |
| `refuse_reason` | body | string | 否 | 售后拒绝原因 | `"售后拒绝原因"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.returnOrder.batchOperate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 响应码 | `0` |
| `msg` | string | 响应信息 | `success` |
| `success` | boolean | 是否操作成功 | `true` |
| `success_order_no_list` | array | 处理成功售后单号列表 | `{"GSH123123123"}` |
| `failed_order_no_list` | array | 处理失败售后单号列表 | `{"GSH321321321"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 请求参数异常（sub_code: isv.business-failed:1020） | 修改请求入参 |
| `20000` | 系统错误 / 业务处理失败（sub_code: isp.service-error:1040） | 根据提示处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1000） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "failed_order_no_list": "{\"GSH321321321\"}",
    "msg": "success",
    "success": "true",
    "success_order_no_list": "{\"GSH123123123\"}"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:1020",
  "sub_msg": "请求参数异常"
}
```

## 备注
