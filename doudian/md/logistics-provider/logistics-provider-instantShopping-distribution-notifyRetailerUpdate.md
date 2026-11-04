# 配送商通知更新三方门店信息

> instantShopping.distribution.notifyRetailerUpdate — 配送商通知更新三方门店信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 配送商通知更新三方门店信息 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-instantShopping-distribution-notifyRetailerUpdate` |
| 接口 ID | `doudian.logistics-provider.instantShopping.distribution.notifyRetailerUpdate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6895 |
| 更新日期 | `2024-09-26` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `distributorCode` | body | mixed | 是 | 2 | `配送商code` |
| `carrierShopId` | body | string | 是 | 123456 | `配送商门店id` |
| `updateTime` | body | mixed | 是 | 17000000 | `更新时间` |
| `eventTypeList` | body | array | 是 | [1,2] | `更新类型` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.distribution.notifyRetailerUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
