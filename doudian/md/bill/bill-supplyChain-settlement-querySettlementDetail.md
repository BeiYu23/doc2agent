# supplyChain.settlement.querySettlementDetail

> 查询对账单行(结算明细)信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.supplyChain.settlement.querySettlementDetail` |
| 中文名 | 查询对账单行(结算明细)信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/8002 |
| 更新日期 | `2026-04-23` |

## 接口说明

- 文档书: 账单API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bizCode` | body | string | 是 | 业务身份标识 | `PLATFORM-GOV-SUBSIDIES-SHELL` |
| `checkBillNo` | body | string | 是 | 对账单编号 | `CB7587332613510512567` |
| `page` | body | mixed | 是 | 页数 | `1` |
| `pageSize` | body | mixed | 是 | 每页数量 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.settlement.querySettlementDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 错误码，"0"代表请求成功 | `0` |
| `msg` | string | 错误码说明 | `"SUCCESS"` |
| `total` | mixed | 总条数 | `1` |
| `page` | mixed | 页码 | `1` |
| `pageSize` | mixed | 每条页数 | `1` |
| `settlementList` | array | 结算明细列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常:%s（sub_code: isp.service-error:1001） | 重试或联系内部人员 |
| `40004` | 非法的参数 / 参数异常:%s（sub_code: isv.parameter-invalid:1002） | 检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "\"SUCCESS\"",
    "page": "1",
    "pageSize": "1",
    "settlementList": [
      {
        "amount": "12456",
        "extendInfo": {},
        "feeCategoryId": "132",
        "id": "123456789012345680",
        "payee": "2403442",
        "payer": "1803482"
      }
    ],
    "total": "1"
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
  "sub_code": "isp.service-error:1001",
  "sub_msg": "系统异常:%s"
}
```

## 备注
