# afterSale.submitEvidence

> 卖家提交举证信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.submitEvidence` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/submitEvidence` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/1853 |
| 更新日期 | `2021-01-04` |

## 接口说明

- 文档书: 售后退款API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 是 | 售后单ID ，通过[/trade/refundListSearch](https://op.jinritemai.com/docs/api-docs/17/254) 或者 [/afterSale/refundProcessDetail](https://op.jinritemai.com/docs/api-docs/17/96) 获取 | `1122` |
| `comment` | body | string | 是 | 备注 | `备注` |
| `evidence` | body | array | 是 | [https://xxxx.jpg](https://xxxx.jpg/) \| 凭证，最多四张 | `[https://xxxx.jpg]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/submitEvidence?app_key=your_appkey_here&method=afterSale.submitEvidence&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
