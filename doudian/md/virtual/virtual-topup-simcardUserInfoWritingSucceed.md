# 号卡商品用户信息补录完成回调

> topup.simcardUserInfoWritingSucceed — 号卡商品用户信息补录完成回调

| 元信息 | 值 |
| --- | --- |
| 中文名 | 号卡商品用户信息补录完成回调 |
| 文档地址 | `/docs/doudian/virtual/virtual-topup-simcardUserInfoWritingSucceed` |
| 接口 ID | `doudian.virtual.topup.simcardUserInfoWritingSucceed` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/simcardUserInfoWritingSucceed` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/8278 |
| 更新日期 | `2026-05-12` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/simcardUserInfoWritingSucceed?app_key=your_appkey_here&method=topup.simcardUserInfoWritingSucceed&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | string | 响应固定字符串："SUCCESS" | `SUCCESS` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result": "SUCCESS"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
