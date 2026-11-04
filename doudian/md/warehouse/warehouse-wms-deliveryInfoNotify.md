# 仓储系统回传发货信息

> wms.deliveryInfoNotify — 仓储系统回传发货信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 仓储系统回传发货信息 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-wms-deliveryInfoNotify` |
| 接口 ID | `doudian.warehouse.wms.deliveryInfoNotify` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/wms/deliveryInfoNotify` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1374 |
| 更新日期 | `2021-10-12` |

## 接口说明

- 文档书: 仓库作业API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tracking_no` | body | string | 是 | 运单号 | `1` |
| `operator_type` | body | string | 是 | 操作类型 | `1` |
| `operator_des` | body | string | 是 | 描述 | `1` |
| `operator_time` | body | string | 是 | 时间 | `1` |
| `operator_user` | body | string | 否 | 操作人 | `1` |
| `operator_remark` | body | string | 否 | 备注 | `1` |
| `timestamp` | body | string | 否 | 时间戳 | `2021-10-12 10:00:00` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/wms/deliveryInfoNotify?app_key=your_appkey_here&method=wms.deliveryInfoNotify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 通用业务错误码（sub_code: isv.business-failed:-1） | 参考返回值中的message字段 |

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
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "通用业务错误码"
}
```

## 备注
