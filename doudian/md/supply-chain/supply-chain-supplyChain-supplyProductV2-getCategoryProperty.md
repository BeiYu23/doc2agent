# 获取货品类目属性

> supplyChain.supplyProductV2.getCategoryProperty — 获取货品类目属性

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取货品类目属性 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-supplyProductV2-getCategoryProperty` |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.getCategoryProperty` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6672 |
| 更新日期 | `2024-07-04` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 否 | 新类目ID | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/zzh/testWDNetWork001?app_key=your_appkey_here&method=zzh.testWDNetWork001&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed |  | `` |
| `msg` | string |  | `` |
| `product_format` | array |  | `` |
| `tpl_type` | mixed | 模板类型，1：Spu 0: 普通商品 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductFormatTpl] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS\|ecom.bscp.scm_open:default:hl:\|cmp.ecom.product_backend:default:hl:\|（sub_code: isv.business-failed:2000） | 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductFormatTpl] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS\|ecom.bscp.scm_open:default:hl:\|cmp.ecom.product_backend:default:hl:\| |
| `50002` | 业务处理失败 / 1020:参数异常，请检查后重试\|供应商信息异常（sub_code: isv.business-failed:1020） | 1020:参数异常，请检查后重试\|供应商信息异常 |

## 响应示例

成功：

```json
{
  "data": {
    "biz_error": {
      "code": "示例值",
      "message": "示例值"
    },
    "code": "测试",
    "encrypt_orderId": "示例值",
    "msg": "测试",
    "order": {
      "abnormal": "测试",
      "aggregations_status_info": {
        "abnormal_count": "测试",
        "all_count": "测试",
        "all_signed_count": "测试",
        "binding_waited_count": "测试",
        "deduction_waited_count": "测试",
        "frozen_waited_count": "测试",
        "part_signed_count": "测试",
        "shipped_waited_count": "测试",
        "timed_out_count": "测试",
        "will_time_out_count": "测试"
      },
      "bind_certification_infos": [
        {
          "certification_code": "测试",
          "inspection_agency_id": "测试"
        }
      ],
      "biz_status": "测试",
      "biz_status_desc": "测试",
      "buyer_words": "测试",
      "create_time": "测试",
      "distributor_id": "测试",
      "distributor_name": "测试",
      "exp_ship_time": "测试",
      "fx_product_id": "测试",
      "fx_product_name": "测试",
      "fx_product_specs": "测试",
      "fx_spu_id": "测试",
      "fx_spu_name": "测试",
      "inventory_mode": "测试",
      "order_no": "测试",
      "order_status": "测试",
      "order_status_desc": "测试",
      "out_product_code": "测试",
      "package_list": [
        {
          "package_id": "测试",
          "ship_cnt": "测试",
          "tms_code": "测试",
          "tracking_no": "测试"
        }
      ],
      "post_addr": {
        "addr_detail": "测试",
        "city_id": "测试",
        "city_name": "测试",
        "province_code": "测试",
        "province_name": "测试",
        "street_id": "测试",
        "street_name": "测试",
        "town_id": "测试",
        "town_name": "测试"
      },
      "post_receiver": "测试",
      "post_tel": "测试",
      "pre_sale_type": "测试",
      "price": "测试",
      "product_id": "测试",
      "product_name": "测试",
      "product_specs": "测试",
      "quantity": "测试",
      "refund_status": "测试",
      "sales_type": "测试",
      "settlement_no": "测试",
      "settlement_time": "测试",
      "settlement_type": "测试",
      "ship_time": "测试",
      "shop_order_id": "测试",
      "shop_words": "测试",
      "supply_order_type": "测试",
      "total_amount": "测试",
      "trade_pay_time": "测试",
      "virtual_warehouse_id": "测试",
      "warehouse_code": "测试",
      "warehouse_name": "测试"
    },
    "total": "示例值，上线内容编辑"
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
  "sub_code": "isv.business-failed:2000",
  "sub_msg": "2000:业务处理异常|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductFormatTpl] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS|ecom.bscp.scm_open:default:hl:|cmp.ecom.product_backend:default:hl:|"
}
```

## 备注
