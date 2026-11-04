# order.invoiceList

> 查看商家开票列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.invoiceList` |
| 中文名 | 查看商家开票列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/invoiceList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1842 |
| 更新日期 | `2026-09-22` |

## 接口说明

- 文档书: 订单API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 父订单ID | `4718699311644951110` |
| `order_status` | body | string | 否 | 订单状态，逗号分割 | `3,5` |
| `start_time` | body | mixed | 否 | 申请创建开始时间，时间戳，秒 | `1625638841` |
| `end_time` | body | mixed | 否 | 申请创建结束时间，时间戳，秒 | `1625638841` |
| `status` | body | mixed | 否 | 开票状态：1待开票、2已开票、3已关闭 | `1` |
| `page_no` | body | mixed | 否 | 页数（默认为0，第一页从0开始），page_no* page_size不超过1万 | `0` |
| `page_size` | body | mixed | 否 | 请求每页返回的数量，默认20，最多50 | `20` |
| `order_by` | body | string | 否 | 默认排序规则为desc； 排序方式支持asc/desc | `asc` |
| `order_field` | body | string | 否 | 排序规则： 创建时间排序create_time，不传默认创建时间 | `create_time` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/invoiceList?app_key=your_appkey_here&method=order.invoiceList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `invoice_list` | array | 发票信息清单 | `` |
| `total` | mixed | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 8888：系统繁忙，请稍后重试（sub_code: isv.business-failed:8888） | 稍后重试 |
| `40004` | 非法的参数 / 10009：PageSize 超过 100（sub_code: isv.parameter-invalid:10009） | PageSize设置为50 |
| `50002` | 业务处理失败 / 40007：批量获取政府补贴订单发票规则信息失败（sub_code: isv.business-failed:40007） | 稍后重试 |
| `50002` | 业务处理失败 / 10049: 开始时间错误（sub_code: isv.business-failed:10049） | 修改开始时间 |

## 响应示例

成功：

```json
{
  "data": {
    "invoice_list": [
      {
        "apply_scene": "2",
        "apply_time": "1625638841",
        "bank_name": "中国银行",
        "bank_no": "338923123627",
        "company_address": "北京市平谷区林荫北街13号12幢",
        "company_mobile": "010-58323810",
        "end_reason": "1",
        "end_time": "1625638841",
        "extra": "额外附加信息",
        "file_name": "发票.pdf",
        "invoice_amount": "10000",
        "invoice_detail": "{\"4817040770060371513\":{\"ProductId\":3490890566424762040,\"ProductCount\":1,\"ProductName\":\"一单多品测试 人字拖\",\"ProductPrice\":1,\"SkuSpecs\":[{\"Name\":\"尺码-欧码\",\"Value\":\"1\"}],\"SkuCode\":\"\"}}",
        "invoice_detail_extra": {
          "actual_pay_amount": "100",
          "gov_subsidy_city_code": "government_subsidy_bj_bj",
          "gov_subsidy_uninvoice_amount": "100",
          "government_subsidy_area_name": "浙江宁波",
          "government_subsidy_backdoor_order": "true",
          "government_subsidy_invoice_remark": "订单号：6941940048635500445；购机日期：2025.04.27；手机号：19821877291；69码：6922122913683；政府补贴金额0.06元；SN码：mockflow",
          "government_subsidy_item_name": "洗衣机",
          "government_subsidy_major_category_name": "家装厨卫",
          "none_government_subsidy_backdoor_order": "true",
          "payment_no": "12345678910",
          "post_amount": "600",
          "post_receiver_info": {
            "buyer_mobile": "12345678910",
            "post_addr_text": "安徽省安庆市安阳区安阳街道4 号楼 5 单元"
          },
          "recycle_credit_deduction_amount": "100",
          "refund_amount": "100",
          "urge_invoice": "\"1\""
        },
        "invoice_file_list": [
          {
            "file_name": "123.OFD",
            "tos_url": "https://lf26-ecom-shop-sign.bytetos.com/ecom-shop-order-invoice/21084d0102dc458be261deebb2f2064b?x-expires=1625495766&x-signature=a8QxsaOnBkSSeVEe%2Brv45NmB%2B%2BU%3D"
          }
        ],
        "invoice_status": "2",
        "invoice_status_type": "1",
        "invoice_sub_status": "200",
        "invoice_type": "1",
        "latest_invoice_time": "123455",
        "latest_upload_time": "1625638841",
        "order_status": "2",
        "registation_id": "6981804344242176269",
        "shop_id": "77977",
        "shop_order_id": "4816720996870743609",
        "tax_no": "11752825826826826",
        "title": "法国发四十分",
        "title_type": "1",
        "tos_url": "https://lf26-ecom-shop-sign.bytetos.com/ecom-shop-order-invoice/21084d0102dc458be261deebb2f2064b?x-expires=1625495766&x-signature=a8QxsaOnBkSSeVEe%2Brv45NmB%2B%2BU%3D",
        "upload_time": "1625638841"
      }
    ],
    "total": "10"
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
  "sub_code": "isv.business-failed:8888",
  "sub_msg": "8888：系统繁忙，请稍后重试"
}
```

## 备注
