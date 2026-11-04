# instantShopping.logisticsMerchant.approvalSign

> 审批签约意向

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-express.instantShopping.logisticsMerchant.approvalSign` |
| 中文名 | 审批签约意向 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1584/7300 |
| 更新日期 | `2025-03-03` |

## 接口说明

- 文档书: 合作快递【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_type_code` | body | string | 否 | 配送产品，双方约定 | `"001"` |
| `store_id` | body | mixed | 否 | 商家的经营门店/仓id（经营子门店id） | `123` |
| `operate_type` | body | mixed | 否 | 审批类型，1-同意，2-拒绝 | `1` |
| `comment` | body | string | 否 | 评论，拒绝时是拒绝原因 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logisticsMerchant.approvalSign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
