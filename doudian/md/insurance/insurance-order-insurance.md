# order.insurance

> 根据订单ID，获取该订单对应的运费险保单的详细信息；
1、status<=1&status=5的情况下ins_ensured_time_begin、ins_ensured_time_end没有意义（返回的是默认时间"1754-08-31 06:49:25"

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.insurance.order.insurance` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/insurance` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/32/626 |
| 更新日期 | `2021-06-23` |

## 接口说明

- 文档书: 保险API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单id(可以加A也可以不加） | `6496679971677798670` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/insurance?app_key=your_appkey_here&method=order.insurance&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `policy_info_list` | array | 保单详情列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 查询保单信息失败（sub_code: isv.business-failed:9999） | 业务处理失败，尝试重试 |
| `50002` | 业务处理失败 / 参数错误,订单不存在（sub_code: isv.business-failed:2） | 请检查order_id字段 |

## 响应示例

成功：

```json
{
  "data": {
    "policy_info_list": [
      {
        "appeal_status": "0",
        "approximate_return_fee": "1200",
        "claim_status": "0",
        "company_name": "\"中国人民财产保险股份有限公司\"",
        "fail_reason": "\"失败原因\"",
        "goods_info_list": [
          {
            "amount": "1",
            "category_id": "\"13-3004-3006\"",
            "product_id": "3436088998672617334",
            "product_name": "\"商品名称\"",
            "show_page_url": "\"https://sf1-ttcdn-tos.pstatp.com/obj/temai/6535e88c983f735cabb99f5b00f6212awww800-800\","
          }
        ],
        "ins_ensured_time_begin": "\"2020-09-17 14:48:08\"",
        "ins_ensured_time_end": "\"2020-12-16 14:48:08\"",
        "ins_policy_no": "\"10202009171446081711854084111\"",
        "insurance_hotline": "\"400-188-1949转1\"",
        "is_allow_appeal": "false",
        "merchant_premium": "60",
        "platform_premium": "0",
        "premium_status": "2",
        "status": "2",
        "total_premium": "60",
        "user_premium": "0"
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
  "sub_code": "isv.business-failed:9999",
  "sub_msg": "查询保单信息失败"
}
```

## 备注
