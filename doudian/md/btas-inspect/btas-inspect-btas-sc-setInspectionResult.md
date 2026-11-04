# btas.sc.setInspectionResult

> 质检机构_上传订单质检结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.sc.setInspectionResult` |
| 中文名 | 质检机构_上传订单质检结果 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/setInspectionResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2923 |
| 更新日期 | `2023-02-09` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `234231` |
| `result` | body | string | 是 | 质检结果：1-通过，2-不通过，5-无法质检，99-无需质检，触发退货发 | `1` |
| `service_status` | body | string | 是 | 1：上传质检报告，2：取消质检报告 | `1` |
| `service_charge` | body | string | 是 | 回传的这单的质检费用。单位（分） | `3000` |
| `service_center_id` | body | number | 是 | 质检中心ID | `1` |
| `certification_code` | body | string | 是 | 质检编码,仅字母数字 | `SNAKE001001` |
| `result_details` | body | string | 是 | 质检详情。JSON字符串 | `{"brand":"苹果","model":"Iphone 12 Pro Max"}` |
| `inspection_complete_time` | body | number | 是 | 质检完成时间（秒,UTC） | `1675244344` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/OpenAfterSaleChannel?app_key=your_appkey_here&method=afterSale.OpenAfterSaleChannel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 订单状态异常（sub_code: isp.service-error:2019） | 登录btas处理异常订单 |
| `20000` | 系统错误（sub_code: isp.service-error:3001） | 重试 |
| `20000` | 系统错误 / 质检任务错误（sub_code: isp.service-error:4002） | 重试 |
| `20000` | 系统错误 / 质检编码重复（sub_code: isp.service-error:2018） | 更换质检码 |
| `50002` | 业务处理失败 / 4105:更新质检任务出错（sub_code: isv.business-failed:4105） | 4105:更新质检任务出错 |
| `50002` | 业务处理失败 / 10000:正在执行该订单的请求，请耐心等待（sub_code: isv.business-failed:10000） | 10000:正在执行该订单的请求，请耐心等待 |

## 响应示例

成功：

```json
{
  "data": {
    "conclusion": {
      "can_apply_type_list": "[1,2]",
      "match_conclusion": "1",
      "match_message": "\"\"",
      "match_success": "true"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:2019",
  "sub_msg": "订单状态异常"
}
```

## 备注
