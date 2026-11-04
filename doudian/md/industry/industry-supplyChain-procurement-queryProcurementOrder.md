# 查询采购单信息

> supplyChain.procurement.queryProcurementOrder — 查询采购单信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询采购单信息 |
| 文档地址 | `/docs/doudian/industry/industry-supplyChain-procurement-queryProcurementOrder` |
| 接口 ID | `doudian.industry.supplyChain.procurement.queryProcurementOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/7969 |
| 更新日期 | `2025-12-19` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 否 | 店铺单号 | `691111111111111111111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.procurement.queryProcurementOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 采购单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "complete_time": "1766124572",
        "create_time": "1766124572",
        "detail_list": [
          {
            "author_subsidy_amount": "100",
            "commission_amount": "100",
            "estimated_procurement_amount": "100",
            "estimated_procurement_price": "100",
            "gov_subsidy_amount_info": {
              "government_subsidy": "100",
              "platform_subsidy": "100",
              "shop_subsidy": "100"
            },
            "order_no": "PO75792201184678",
            "pay_subsidy_amount": "100",
            "platform_subsidy_amount": "100",
            "procurement_amount": "100",
            "product_id": "3788402848050000000",
            "product_name": "xx商品",
            "quantity": "1",
            "sku_order_id": "691111111111111111111111"
          }
        ],
        "distributor_id": "206400000",
        "distributor_name": "xx公司",
        "order_no": "PO75792201184678",
        "order_status": "100",
        "pay_time": "1766124572",
        "shop_order_id": "691111111111111111111111",
        "supplier_id": "148000074",
        "supplier_name": "xx公司"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
