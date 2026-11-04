# afterSale.OpenAfterSaleChannel

> 商家打开售后通道

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.OpenAfterSaleChannel` |
| 中文名 | 商家打开售后通道 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/OpenAfterSaleChannel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/764 |
| 更新日期 | `2021-08-13` |

## 接口说明

- 文档书: 售后退款API（版本 V2.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | number | 是 | 订单ID | `4810811637262779447` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/OpenAfterSaleChannel?app_key=your_appkey_here&method=afterSale.OpenAfterSaleChannel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `conclusion` | object | 打开售后通道结论 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 无权操作此订单（sub_code: isv.business-failed:11001） | 检查参数后重试 |
| `50002` | 业务处理失败 / 系统错误，请重试（sub_code: isv.business-failed:10000） | 系统错误，请重试 |
| `50002` | 业务处理失败 / 售后入口已经打开，请联系买家在用户端申请售后（sub_code: isv.business-failed:12000） | 售后入口已经打开，请联系买家在用户端申请售后 |
| `50002` | 业务处理失败 / 12001:售后入口已经打开，请联系买家在用户端申请售后（sub_code: isv.business-failed:12001） | 12001:售后入口已经打开，请联系买家在用户端申请售后 |

## 响应示例

成功：

```json
{
  "data": {
    "conclusion": {
      "can_apply_type_list": "[1,2]",
      "match_conclusion": "1",
      "match_message": "\"\"",
      "match_success": "true"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:11001",
  "sub_msg": "无权操作此订单"
}
```

## 备注
