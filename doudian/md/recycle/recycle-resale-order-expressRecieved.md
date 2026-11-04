# resale.order.expressRecieved

> 【邮寄回收】邮寄快递签收

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.recycle.resale.order.expressRecieved` |
| 中文名 | 【邮寄回收】邮寄快递签收 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/resale/order/expressRecieved` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/4630 |
| 更新日期 | `2023-09-06` |

## 接口说明

- 文档书: 回收寄卖API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 内部单号 | `"1232323213"` |
| `service_entity_code` | body | string | 是 | 服务商编码，平台提供 | `"xxxx"` |
| `logistics_order_id` | body | string | 是 | 快递单号 | `"xxxxxxxxxx"` |
| `logistics_company` | body | string | 是 | 快递公司 | `1` |
| `operate_time` | body | string | 是 | 操作时间 | `"yyyy-MM-dd hh:MM:ss"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=resale.order.expressRecieved&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
