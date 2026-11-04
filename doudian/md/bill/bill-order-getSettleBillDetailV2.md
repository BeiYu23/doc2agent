# order.getSettleBillDetailV2

> 2024年7月1日停止服务。已结算的订单才会有数据，数据T+1生成，建议第二天12点之后来查询。如因任务积压导致延迟的情况，建议重试。从/order/settle接口迁移至此接口，可参考此文档:https://bytedance.feishu.cn/doc

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.getSettleBillDetailV2` |
| 中文名 | 2024年7月1日停止服务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getSettleBillDetailV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1390 |
| 更新日期 | `2022-11-02` |

## 接口说明

- 文档书: 账单API（版本 V2.11）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=order.getSettleBillDetailV2&param_json={}'
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
  "msg": "success"
}
```

失败：

```json
{
  "code": 40004,
  "msg": "非法的参数"
}
```

## 备注
