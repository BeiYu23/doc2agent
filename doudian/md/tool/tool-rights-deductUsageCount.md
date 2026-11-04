# rights.deductUsageCount

> 扣减权益可使用次数

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.rights.deductUsageCount` |
| 中文名 | 扣减权益可使用次数 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/rights/deductUsageCount` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/6060 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_biz_id` | body | string | 否 | 外部业务ID(模板市场为模板code)，非必传，不可与service_id同传 | `6859718390706503687` |
| `service_id` | body | mixed | 否 | 抖店服务市场服务ID，非必传，不可与outer_biz_id同传 | `11111` |
| `log_id` | body | string | 是 | 用户使用软件时, 调用抖店开放平台接口的日志id(触发这次扣减操作的业务操作的logId) | `20231225105514FF055C41D500275B3726` |
| `req_id` | body | string | 是 | 请求id, 用作幂等键 | `isv_service1#user1#202312251010999` |
| `deduct_cnt` | body | mixed | 是 | 扣减次数，不支持传负数 | `1` |
| `remark` | body | string | 否 | 备注，长度不超过1024 | `备注` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/rights/deductUsageCount?app_key=your_appkey_here&method=rights.deductUsageCount&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:100001） | 更正传参 |
| `50002` | 业务处理失败 / 查询数据库错误（sub_code: isv.business-failed:200） | 等待系统恢复后重试 |
| `50002` | 业务处理失败 / 越权, 查询了不属于该应用的数据（sub_code: isv.business-failed:500） | 仅查询有权限的数据 |
| `50002` | 业务处理失败 / 系统内部错误（sub_code: isv.business-failed:100） | 等待系统恢复后重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:300000） | 满足业务条件后重试 |
| `50002` | 业务处理失败 / 重复请求, 命中幂等（sub_code: isv.business-failed:800） | 已经执行过请求, 无需重复操作 |

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
  "sub_code": "isv.parameter-invalid:100001",
  "sub_msg": "参数错误"
}
```

## 备注
