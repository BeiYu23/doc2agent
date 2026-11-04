# order.policy

> 查各种保险的保单详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.insurance.order.policy` |
| 中文名 | 查各种保险的保单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/policy` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/32/1854 |
| 更新日期 | `2023-04-17` |

## 接口说明

- 文档书: 保险API（版本 V1.07）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单id | `6496679971677798670` |
| `ins_product_id` | body | string | 是 | 保单类型枚举值： returnfreight2020v1-运费险；allergyinsurance2021-过敏险；plant7dinsurance2021-绿植养死包赔7天； plant15dinsurance2021-绿植养死包赔15天；insopenbox2022v12b-开箱无忧；foodsafety2022ecom2b -食安保； | `returnfreight2020v1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `policy_info` | object | 保单详情列表 | `` |
| `claim_info_list` | array | 理赔列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单未找到（sub_code: isv.business-failed:2） | 请检查订单信息 |
| `50002` | 业务处理失败 / 查询保单失败（sub_code: isv.business-failed:9999） | 请稍后重试 |

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
  "sub_code": "isv.business-failed:2",
  "sub_msg": "订单未找到"
}
```

## 备注
