# crossborder.takingLogisticsInfo

> 运单信息回告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossborder.takingLogisticsInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossborder/takingLogisticsInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/1293 |
| 更新日期 | `2021-09-27` |

## 接口说明

- 文档书: 跨境API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vendor` | body | string | 是 | 服务商编码 | `NBFL` |
| `order_id` | body | string | 是 | 交易单号 | `4853003828309985089` |
| `domestic_carrier` | body | string | 是 | 物流公司编码 | `yuantong` |
| `domestic_trans_no` | body | string | 是 | 物流单号 | `YT1634023916000` |
| `express_code` | body | string | 否 | 物流企业代码，四字中文编码 | `中通速递` |
| `express_cop_code` | body | string | 是 | 物流企业海关编码 | `3122480063` |
| `express_cop_name` | body | string | 是 | 物流企业名称 | `上海大誉国际物流有限公司` |
| `sort_code` | body | string | 否 | 三段码 | `801- 503 55,北京转香河` |
| `remark01` | body | string | 否 | 物流备用字段01 | `服务商自行透传，平台不限制` |
| `remark02` | body | string | 否 | 物流备用字段02 | `服务商自行透传，平台不限制` |
| `remark03` | body | string | 否 | 物流备用字段03 | `服务商自行透传，平台不限制` |
| `remark04` | body | string | 否 | 物流备用字段04 | `服务商自行透传，平台不限制` |
| `remark05` | body | string | 否 | 物流备用字段05 | `服务商自行透传，平台不限制` |
| `remark06` | body | string | 否 | 物流备用字段06 | `服务商自行透传，平台不限制` |
| `remark07` | body | string | 否 | 物流备用字段07 | `服务商自行透传，平台不限制` |
| `remark08` | body | string | 否 | 物流备用字段08 | `服务商自行透传，平台不限制` |
| `remark09` | body | string | 否 | 物流备用字段09 | `服务商自行透传，平台不限制` |
| `remark10` | body | string | 否 | 物流备用字段10 | `服务商自行透传，平台不限制` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/takingLogisticsInfo?app_key=your_appkey_here&method=crossborder.takingLogisticsInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 成功 | `0` |
| `msg` | string | 成功 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 服务不可用 / 接口调用异常，请重试，多次失败请人工反馈（sub_code: isp.service-error:1005） | 按 sub_code 定位问题后处理 |
| `20000` | 服务不可用 / NotifyLogisticsInfo err（sub_code: isp.service-error:-1） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "success"
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
  "msg": "服务不可用",
  "sub_code": "isp.service-error:1005",
  "sub_msg": "接口调用异常，请重试，多次失败请人工反馈"
}
```

## 备注
