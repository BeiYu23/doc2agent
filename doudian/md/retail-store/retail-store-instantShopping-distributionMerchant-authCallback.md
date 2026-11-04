# 授权回调

> instantShopping.distributionMerchant.authCallback — 授权回调

| 元信息 | 值 |
| --- | --- |
| 中文名 | 授权回调 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-instantShopping-distributionMerchant-authCallback` |
| 接口 ID | `doudian.retail-store.instantShopping.distributionMerchant.authCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/6515 |
| 更新日期 | `2024-11-25` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `merchantId` | body | string | 是 | 抖音店铺id | `"1"` |
| `sourceId` | body | string | 是 | 操作来源的唯一身份ID | `"1"` |
| `carrierAccountId` | body | string | 是 | 配送商账号Id | `"1"` |
| `carrierAccountName` | body | string | 否 | 配送商账号名称 | `"门店"` |
| `serviceProducts` | body | array | 否 | 用户注册配送商账号时选择的服务产品,例如:"专人直送"、"同城急送" | `` |
| `  └ productCode` | body | string | 是 | 服务产品code | `uuzc` |
| `  └ productName` | body | string | 否 | 服务产品名称 | `UU专送` |
| `  └ productType` | body | mixed | 是 | 服务产品类型 | `2` |
| `carrierAccountType` | body | mixed | 否 | 账号类型： 1：B侧账号 2：C侧账号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.distributionMerchant.authCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
