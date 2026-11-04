# 分页查询开票申请

> supplyChain.invoice.pageQueryInvoiceApply — 分页查询开票申请

| 元信息 | 值 |
| --- | --- |
| 中文名 | 分页查询开票申请 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-supplyChain-invoice-pageQueryInvoiceApply` |
| 接口 ID | `doudian.logistics-provider.supplyChain.invoice.pageQueryInvoiceApply` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6937 |
| 更新日期 | `2024-10-17` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `apply_no` | body | string | 否 | 开票申请单号 | `IAO7366832755336380690` |
| `seller_role` | body | string | 是 | 销方角色(SERVICE_MARKET_PROVIDER_LP:服务商市场服务商) | `SERVICE_MARKET_PROVIDER_LP` |
| `biz_code` | body | string | 是 | 业务线(WH-FFAZ-3PL:付费安装) | `WH-FFAZ-3PL` |
| `apply_order_status` | body | string | 否 | 申请单状态编码(approving:待开票,invoiced:已开票) | `approving` |
| `create_time_gte` | body | mixed | 否 | 申请时间大于等于(秒级时间戳) | `1726297637` |
| `create_time_lte` | body | mixed | 否 | 申请时间小于等于(秒级时间戳) | `1726297637` |
| `page` | body | mixed | 是 | 页数，默认50，不能高于100 | `1` |
| `page_size` | body | mixed | 是 | 每页数量，从1开始，page*page_size不超过2万 | `50` |
| `sort_field` | body | string | 否 | 排序字段, 默认按申请时间倒序(create_time:申请时间, invoice_amount:开票金额) | `create_time` |
| `sort_type` | body | string | 否 | 排序字段(asc:升序, desc:降序) | `desc` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.invoice.pageQueryInvoiceApply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |
| `ret_code` | string | 错误码，"000000"代表请求成功 | `000000` |
| `ret_msg` | string | 错误码说明 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "list": [
        {
          "apply_no": "IAO7418495025201152296",
          "apply_order_status": "approving",
          "apply_record_no": "IAR7367275749566316854",
          "biz_code": "WH-FFAZ-3PL",
          "biz_no": "6934482450979296642",
          "buyer_entity_info": {
            "address": "浙江省杭州市余杭区xx号",
            "bank_account": "6228210669002516829",
            "bank_name": "中国工商银行上海市徐泾支行",
            "email": "124289076@qq.com",
            "entity_name": "北京字跳网络技术有限公司",
            "entity_type": "company",
            "id": "4053272734729401",
            "mobile_number": "18088888888",
            "name": "小明",
            "phone_no": "18088888888",
            "role": "CUSTOMER",
            "tax_no": "91110108MA01F2L25J"
          },
          "create_time": "1726297637",
          "invoice_amount_str": "11.31",
          "invoice_type": "2",
          "main_shop_order_no": "6934482450979296642",
          "operate_no": "BSO50595841538"
        }
      ],
      "page": "1",
      "page_size": "50",
      "total": "8372"
    },
    "ret_code": "000000",
    "ret_msg": "成功"
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
