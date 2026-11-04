# fuwu.settle.getBizOrder

> 获取某一笔服务市场订单的结算信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.fuwu.settle.getBizOrder` |
| 中文名 | 获取某一笔服务市场订单的结算信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/settle/getBizOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/6530 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | mixed | 是 | 要查询的订单ID，仅支持查询服务市场订单，仅支持查询近一年内订单。 | `6930098883274470000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/settle/getBizOrder?app_key=your_appkey_here&method=fuwu.settle.getBizOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `biz_order` | object | 服务市场订单结算信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:1000001） | 正确传参即可 |
| `50002` | 业务处理失败 / 获取财经信息失败（sub_code: isv.business-failed:2300001） | 按返回的错误说明文本处理 |
| `20000` | 系统错误 / 系统内部超时（sub_code: isp.service-error:1000004） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "biz_order": {
      "order_id": "6930098883274470000",
      "pay_amount": "2000",
      "settle_status": "2",
      "settled_amount": "1200"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1000001",
  "sub_msg": "参数校验失败"
}
```

## 备注
