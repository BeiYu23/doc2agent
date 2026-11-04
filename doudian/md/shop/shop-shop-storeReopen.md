# 门店恢复营业

> shop.storeReopen — 门店恢复营业

| 元信息 | 值 |
| --- | --- |
| 中文名 | 门店恢复营业 |
| 文档地址 | `/docs/doudian/shop/shop-shop-storeReopen` |
| 接口 ID | `doudian.shop.shop.storeReopen` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/storeReopen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2059 |
| 更新日期 | `2022-06-27` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 门店ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/storeReopen?app_key=your_appkey_here&method=shop.storeReopen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | number | 0失败1成功 | `1` |
| `reason` | string | 失败原因 | `当前状态不允许恢复营业` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "reason": "当前状态不允许恢复营业",
    "result": "1"
  },
  "err_no": 0,
  "message": "success",
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
