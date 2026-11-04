# fuwu.refund.search

> 服务市场订单退款单查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.fuwu.refund.search` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/refund/search` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/6531 |
| 更新日期 | `2024-05-23` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 服务市场订单号 | `4968462294508977000` |
| `start_time` | body | mixed | 否 | 退款开始时间 | `1716185632` |
| `arbitrate_status` | body | mixed | 否 | 仲裁状态0：初始化 1：申请仲裁 99：仲裁关闭 | `1` |
| `service_type` | body | mixed | 否 | 服务类型 1：软件 | `1` |
| `end_time` | body | mixed | 否 | 退款结束时间 | `1716185632` |
| `refund_status` | body | mixed | 否 | 退款状态0：初始化 1：已申请退款 2：退款拒绝 3：同意退款 9：退款取消 10：退款成功 99：退款关闭 100：资金退款成功 | `1` |
| `refund_id` | body | mixed | 否 | 服务市场订单退款id | `7133505927713554700` |
| `refund_reason` | body | mixed | 否 | 退款原因1: "软件功能描述与实际不符" 2:"软件有故障，完全无法使用" 3:"软件使用体验不佳（页面偶尔卡顿、闪退）"4:"48小时无理由退款" 5:"与服务商协商一致退款" 6:"服务数据、质量未达到承诺" 7:"服务商未进行对接" 8:"交付内容未通过平台审核" 9:"对交付时间不满意" 10:"服务商态度、专业度问题” 11:"服务商要求加价" 12:"平台自动根据比例退款" 999:"其他" | `1` |
| `size` | body | mixed | 是 | 每页订单数(默认值10，最大100) | `10` |
| `page` | body | mixed | 是 | 页数(第一页从1开始) | `1` |
| `rank` | body | boolean | 否 | 退款时间排序默认降序 | `false` |
| `buyer_Id` | body | mixed | 否 | 服务市场买家id(例如商家店铺id、百应id) | `121231` |
| `biz_type` | body | mixed | 否 | 业务类型1:商家 2:ebill 3:供应商 4:机构 5:团长 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/refund/search?app_key=your_appkey_here&method=fuwu.refund.search&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `search_refund_list` | array | 服务市场退款信息列表 | `` |
| `total` | mixed | 总退款单数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:1000001） | 校正入参 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1000004） | 按返回的错误说明文本处理 |

## 响应示例

成功：

```json
{
  "data": {
    "search_refund_list": [
      {
        "apply_time": "1716185220",
        "arbitrate_status": "1",
        "order_id": "6929776762739168000",
        "pay_amount": "100",
        "pay_time": "1716185220",
        "reason_code": "1",
        "refund_amount": "120",
        "refund_id": "7133505927713550000",
        "refund_status": "1",
        "service_id": "1",
        "service_name": "退款服务",
        "service_type": "1",
        "shop_id": "11111",
        "shop_name": "抖店名称"
      }
    ],
    "total": "100"
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
