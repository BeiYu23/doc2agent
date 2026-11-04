# 资产领券

> marketing.BatchApplyAsset — 资产领券接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 资产领券 |
| 文档地址 | `/docs/doudian/marketing/marketing-marketing-BatchApplyAsset` |
| 接口 ID | `doudian.marketing.marketing.BatchApplyAsset` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/BatchApplyAsset` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7168 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `unique_id` | body | string | 是 | 幂等id，请求方的唯一单号 | `"123456789"` |
| `user_info` | body | object | 是 | 用户信息 | `` |
| `  └ doudian_open_id` | body | string | 是 | 抖店openID | `123456` |
| `req_item_list` | body | array | 是 | 待资产领取列表 | `` |
| `  └ apply_amount` | body | mixed | 是 | 领券时固定传0 | `0` |
| `  └ coupon_meta_id` | body | mixed | 是 | 批次Id，包含优惠券批次和红包批次ID | `12345` |
| `  └ apply_num` | body | mixed | 是 | 领取张数 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/BatchApplyAsset?app_key=your_appkey_here&method=marketing.BatchApplyAsset&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `resp_item_list` | array | 领取结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:10） | 系统内部异常，如超时，内部报错等 |
| `50002` | 业务处理失败 / 优惠券模板状态错误（sub_code: isv.business-failed:210003） | 优惠券模板状态错误 |

## 响应示例

成功：

```json
{
  "data": {
    "resp_item_list": [
      {
        "coupon_ids": "[123456789]"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10",
  "sub_msg": "系统内部错误"
}
```

## 备注
