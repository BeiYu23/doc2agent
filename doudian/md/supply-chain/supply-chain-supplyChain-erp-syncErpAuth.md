# supplyChain.erp.syncErpAuth

> 授权信息同步

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.erp.syncErpAuth` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/8110 |
| 更新日期 | `2026-04-15` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `auth_list` | body | array | 否 | 待同步的授权领域对象 | `` |
| `  └ data_sync_mode` | body | string | 否 | platform_pull:平台拉取；erp_push:ERP推送（为空时默认erp_push） | `platform_pull` |
| `  └ status` | body | mixed | 是 | 状态枚举： 1：授权；0：取消授权 | `1` |
| `  └ type` | body | mixed | 是 | 类型: 1:库存； | `1` |
| `  └ app_name` | body | string | 否 |  | `` |
| `  └ app_key` | body | string | 否 |  | `` |
| `  └ platform_shop_id_list` | body | array | 是 | 店铺id | `[1,2,3]` |
| `  └ access_code` | body | string | 否 | 访问编码 | `sadggfdfsdfdgdggf` |
| `  └ cargo_owner_id` | body | string | 是 | erp货主id | `124343a` |
| `  └ company_id` | body | string | 否 | 公司id | `"1111"` |
| `  └ check_list` | body | array | 是 | 库存类型枚举（英文是枚举值）： 在库=stock_quantity; 销售待出库占用=order_pending_quantity; 销退在途=sales_return_quantity 采购在途=purchase_quantity; 调拨在途=transfer_quantity | `["stock_quantity","order_pending_quantity"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.erp.syncErpAuth&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | code | `0` |
| `msg` | string | msg | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "成功"
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
