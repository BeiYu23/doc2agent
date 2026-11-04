# order.ordeReportList

> 明文手机号报备接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.ordeReportList` |
| 中文名 | 明文手机号报备 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/ordeReportList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1550 |
| 更新日期 | `2021-12-20` |

## 接口说明

- 文档书: 订单API（版本 V2.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `add_real_mobile_whites` | body | array | 是 | 报备请求 | `` |
| `  └ order_id` | body | string | 否 | 订单号，订单号和售后单号只需选择一个传入即可 | `4878621053383018305` |
| `  └ after_sale_id` | body | string | 否 | 售后单号，订单号和售后单号只需选择一个传入即可 | `7043704348588900652` |
| `  └ reason_no` | body | number | 是 | 报备原因编码：1-无法发货，2-无法处理售后，3-无法处理客诉，4-无法处理物流包裹，5-其他原因 | `1` |
| `  └ remark` | body | string | 否 | 报备备注 | `需要联系买家` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/ordeReportList?app_key=your_appkey_here&method=order.ordeReportList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `add_real_mobile_whites` | array | 报备响应 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:88888） | 重试 |
| `40004` | 非法的参数 / 申请数量不能超过100（sub_code: isv.parameter-invalid:10005） | 减少请求量 |
| `40002` | 缺少必选参数 / 申请信息不能为空（sub_code: isv.missing-parameter:10004） | 输入请求参数 |

## 响应示例

成功：

```json
{
  "data": {
    "add_real_mobile_whites": [
      {
        "after_sale_id": "7043704348588900652",
        "msg": "请输入正确的申请原因编码",
        "order_id": "4878621053383018305"
      }
    ]
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
  "sub_code": "isv.business-failed:88888",
  "sub_msg": "系统异常，请稍后重试"
}
```

## 备注
