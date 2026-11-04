# 根据商品查询用户权益现状

> mini.activity.rights — 根据商品查询用户权益现状

| 元信息 | 值 |
| --- | --- |
| 中文名 | 根据商品查询用户权益现状 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-activity-rights` |
| 接口 ID | `doudian.miniapp.mini.activity.rights` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/rights` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6746 |
| 更新日期 | `2024-08-05` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | array | 是 | 商品id列表 | `[111,222,333]` |
| `dy_open_id` | body | string | 是 | 抖音openId | `777` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/activity/rights?app_key=your_appkey_here&method=mini.activity.rights&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result_map` | string | 商品id->权益map | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result_map": {}
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
