# 服务商接单

> resale.order.accept — 服务商接单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商接单 |
| 文档地址 | `/docs/doudian/recycle/recycle-resale-order-accept` |
| 接口 ID | `doudian.recycle.resale.order.accept` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/resale/order/accept` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/4633 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 回收寄卖API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 内部单号 | `"1232323213"` |
| `service_entity_code` | body | string | 是 | 服务商编码，平台提供 | `"xxxx"` |
| `operate_time` | body | string | 是 | 操作时间 | `"yyyy-MM-dd hh:MM:ss"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyuncang/qa/get/1?app_key=your_appkey_here&method=yuncang.qa.get.1&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |

## 响应示例

成功：

```json
{
  "data": {
    "output_double": "output_double",
    "output_int": "0"
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
  "sub_code": "isv.business-failed:10000004",
  "sub_msg": "10000004:系统内部错误"
}
```

## 备注
