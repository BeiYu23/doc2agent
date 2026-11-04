# 批量改价

> supplyChain.supplyProduct.batchEditPrice — 批量改价

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量改价 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-supplyProduct-batchEditPrice` |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.batchEditPrice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6686 |
| 更新日期 | `2024-08-26` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `supply_price_list` | body | array | 否 | 价格list | `` |
| `  └ supply_price` | body | mixed | 否 | 供货价，单位分 | `1000` |
| `  └ spec_price_list` | body | array | 否 | 特定供货价list | `` |
| `    └ distributor_id_list` | body | array | 否 | 分销商id列表 | `[1,2]` |
| `    └ supply_price` | body | mixed | 否 | 供货价，单位分 | `900` |
| `  └ suggest_retail_price` | body | mixed | 否 | 建议零售价，单位分 | `10000` |
| `  └ sku_id` | body | mixed | 否 | sku id | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/confirmDailyBill?app_key=your_appkey_here&method=power.confirmDailyBill&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `msg` | string | msg | `msg` |
| `code` | mixed | code | `code` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11037:已存在待生效的改价申请，不允许重复操作改价（sub_code: isv.business-failed:11037） | 11037:已存在待生效的改价申请，不允许重复操作改价 |
| `50002` | 业务处理失败 / 1000:服务异常（sub_code: isv.business-failed:1000） | 1000:服务异常 |
| `50002` | 业务处理失败 / 11002:当前分销品正在改价，请稍后重试~（sub_code: isv.business-failed:11002） | 11002:当前分销品正在改价，请稍后重试~ |

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
  "sub_code": "isv.business-failed:11037",
  "sub_msg": "11037:已存在待生效的改价申请，不允许重复操作改价"
}
```

## 备注
