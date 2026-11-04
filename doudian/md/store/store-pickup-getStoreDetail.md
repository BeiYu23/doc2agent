# 门店详情查询

> pickup.getStoreDetail — 门店详情查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 门店详情查询 |
| 文档地址 | `/docs/doudian/store/store-pickup-getStoreDetail` |
| 接口 ID | `doudian.store.pickup.getStoreDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/getStoreDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7234 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_type` | body | string | 是 | 门店类型 2:到店自提 | `2` |
| `store_id` | body | string | 是 | 门店id | `1138991967` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/updateCollectInfo?app_key=your_appkey_here&method=power.updateCollectInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_detail` | object | 门店信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 500:code:-50,message:用户未登录 [env:prod]ecom/industry_merchant_management/errors/error.go:57（sub_code: isv.business-failed:500） | 请检查登陆参数 |

## 响应示例

成功：

```json
{
  "data": {
    "is_weight_exception": "重量是否异常"
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
  "sub_code": "isv.business-failed:500",
  "sub_msg": "500:code:-50,message:用户未登录\n[env:prod]ecom/industry_merchant_management/errors/error.go:57"
}
```

## 备注
