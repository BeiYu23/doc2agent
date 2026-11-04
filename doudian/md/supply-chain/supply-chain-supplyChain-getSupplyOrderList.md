# 供销平台供货单的分页查询

> supplyChain.getSupplyOrderList — 供销平台供货单的分页查询接口。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 供销平台供货单的分页查询 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-getSupplyOrderList` |
| 接口 ID | `doudian.supply-chain.supplyChain.getSupplyOrderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/getSupplyOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/1732 |
| 更新日期 | `2025-11-28` |

## 接口说明

- 文档书: 供销平台API（版本 V5.13）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fx_product_id` | body | number | 否 | 货品id | `7073424631901749548` |
| `order_status` | body | string | 否 | 单据状态，10待发货，20已发货，-1已取消 | `10` |
| `create_time_start` | body | number | 否 | 单据创建开始时间戳，秒 | `1617355413` |
| `create_time_end` | body | number | 否 | 单据创建结束时间戳，秒 | `1617355513` |
| `order_by` | body | string | 否 | 排序条件，当前仅支持create_time 订单创建时间 | `create_time` |
| `order_asc` | body | boolean | 否 | 是否升序，默认降序 | `true` |
| `page` | body | string | 是 | 页码，从1开始 | `1` |
| `size` | body | string | 是 | 每一页的条数，最大100 | `20` |
| `update_time_start` | body | number | 否 | 单据修改开始时间戳，秒 | `1617355413` |
| `update_time_end` | body | number | 否 | 单据修改结束时间戳，秒 | `1617355513` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 单据总条数 | `999` |
| `order_list` | array | 订单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务错误（sub_code: isp.service-error:1000） | 请稍后重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1020） | 请传入正确的参数 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:2000） | 请稍后重试 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1000",
  "sub_msg": "服务错误"
}
```

## 备注
