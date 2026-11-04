# inspection.order.supplierDispatch

> 服务商已派单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.order.supplierDispatch` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8327 |
| 更新日期 | `2026-05-21` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operator_mobile` | body | string | 是 | 上门师傅手机号，格式，真实号：主机号；虚拟号：主机号-分机号； | `""` |
| `operate_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `""` |
| `operation_no` | body | string | 是 | 实操单号 | `""` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `""` |
| `operator_name` | body | string | 是 | 上门师傅名字 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=inspection.order.supplierDispatch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000006:状态机跃迁校验错误（sub_code: isv.business-failed:10000006） | 10000006:状态机跃迁校验错误 |
| `50002` | 业务处理失败 / 10000000:请求参数错误（sub_code: isv.business-failed:10000000） | 10000000:请求参数错误 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |

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
  "sub_code": "isv.business-failed:10000006",
  "sub_msg": "10000006:状态机跃迁校验错误"
}
```

## 备注
