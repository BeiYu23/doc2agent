# 获取用户真实手机号

> logistics.majorAppliances.GetUserRealPhone — 获取用户真实手机号

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取用户真实手机号 |
| 文档地址 | `/docs/doudian/industry/industry-logistics-majorAppliances-GetUserRealPhone` |
| 接口 ID | `doudian.industry.logistics.majorAppliances.GetUserRealPhone` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8277 |
| 更新日期 | `2026-05-12` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pickup_order_id` | body | string | 否 | 取件单号 | `LBFxxxxxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.majorAppliances.GetUserRealPhone&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `user_phone` | string | 用户手机号 | `18000000000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单信息不存在（sub_code: isv.business-failed:12000） | 检查订单号 |
| `50002` | 业务处理失败 / 调用次数达到上限（sub_code: isv.business-failed:17006） | 使用虚拟号联系用户 |
| `50002` | 业务处理失败 / 风控限制无法获取用户手机号（sub_code: isv.business-failed:17008） | 联系平台处理 |

## 响应示例

成功：

```json
{
  "data": {
    "user_phone": "18000000000"
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
  "sub_code": "isv.business-failed:12000",
  "sub_msg": "订单信息不存在"
}
```

## 备注
