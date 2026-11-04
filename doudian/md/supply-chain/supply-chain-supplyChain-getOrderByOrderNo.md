# 根据供货单号查询

> supplyChain.getOrderByOrderNo — 根据供货单号查询详情

| 元信息 | 值 |
| --- | --- |
| 中文名 | 根据供货单号查询 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-getOrderByOrderNo` |
| 接口 ID | `doudian.supply-chain.supplyChain.getOrderByOrderNo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/getOrderByOrderNo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/1738 |
| 更新日期 | `2026-03-05` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_no` | body | string | 是 | 供货单号 | `CT7074895349864743212` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/getOrderByOrderNo?app_key=your_appkey_here&method=supplyChain.getOrderByOrderNo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order` | object | 订单信息体 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务异常（sub_code: isp.service-error:1000） | 请稍后重试 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:1020） | 请使用正确的参数 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:2000） | 业务处理失败，请参考错误描述解决 |
| `50002` | 业务处理失败 / 数据不存在（sub_code: isv.business-failed:2001） | 检查单号是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "order": {
      "actually_pay_amount": "111",
      "author_id": "123123123123",
      "author_name": "达人xxxxx",
      "biz_status": "210",
      "biz_status_desc": "部份发货",
      "buyer_words": "给我发顺丰",
      "cargo_amount": "111",
      "code_for_consign": "[\"SN\", \"IMEI\"]",
      "combine_order_no": "HD7577367719507400000",
      "create_time": "1647932432",
      "distributor_id": "706141414112",
      "distributor_name": "分销商001",
      "encrypt_post_receiver": "张三",
      "encrypt_post_tel": "12352354314",
      "exp_ship_time": "1647932432",
      "freight_amount": "111",
      "fx_product_id": "702352353",
      "fx_product_name": "测试品01",
      "fx_product_specs": "[{\"name\":\"颜色\",\"value\":\"黄色\"}]",
      "fx_spu_id": "7216561674109616388",
      "imei": "123123123",
      "inventory_mode": "全国类型",
      "is_appointment_ship": "true",
      "order_no": "CT7075649073969725740",
      "order_status": "10",
      "order_status_desc": "待冻结",
      "out_product_code": "T411515",
      "payable_amount": "111",
      "post_addr": {
        "city_id": "11",
        "city_name": "杭州市",
        "district_id": "111",
        "district_name": "余杭区",
        "encrypt_addr_detail": "文一西路1号",
        "province_id": "1",
        "province_name": "浙江省",
        "street_id": "1111",
        "street_name": "仓前街道"
      },
      "pre_sale_type": "0",
      "price": "999",
      "product_id": "513513515",
      "product_name": "测试商品01",
      "product_price": "111",
      "product_specs": "[{\"name\":\"颜色\",\"value\":\"黄色\"}]",
      "promotion_amount": "111",
      "quantity": "1",
      "refund_status": "1",
      "sales_type": "1",
      "settlement_type": "1",
      "ship_time": "1647932432",
      "shop_order_id": "431212298971",
      "shop_words": "xx会员",
      "total_amount": "999",
      "trade_pay_time": "1647932432",
      "virtual_warehouse_id": "7049279407608824100",
      "warehouse_code": "LW011111111111111111111111",
      "warehouse_name": "供销全国仓"
    }
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1000",
  "sub_msg": "服务异常"
}
```

## 备注
