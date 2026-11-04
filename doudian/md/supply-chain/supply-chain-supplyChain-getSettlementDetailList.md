# 结算单列表查询

> supplyChain.getSettlementDetailList — 结算单列表查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 结算单列表查询 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-getSettlementDetailList` |
| 接口 ID | `doudian.supply-chain.supplyChain.getSettlementDetailList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/getSettlementDetailList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/7420 |
| 更新日期 | `2025-04-24` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `status` | body | mixed | 否 | 结算状态 1-待结算 4-已结算 | `1` |
| `biz_codes` | body | string | 否 | 结算模式 代销分账-SUPPLY-CHAIN#SEPARATE-ACCOUNTING  担保交易-SUPPLY-CHAIN#SECURED-TRANSACTIONS 赔付-SUPPLY-CHAIN-COMPENSATION | `SUPPLY-CHAIN#SEPARATE-ACCOUNTING` |
| `settle_mode` | body | mixed | 否 | 结算方式 1-分账 2-转账 | `1` |
| `page_size` | body | mixed | 否 | 请求页大小，最大值100 | `100` |
| `settle_time_start` | body | mixed | 否 | 结算完成开始时间（时间戳到秒） | `1744958170` |
| `settle_time_end` | body | mixed | 否 | 结算完成结束时间（时间戳到秒） | `1744958170` |
| `order_id` | body | string | 否 | 抖店订单号 | `69123123123123123` |
| `trade_order_no` | body | string | 否 | 供货单号 | `CT123123123123123` |
| `distributor_id` | body | string | 否 | 分销商id | `12312312312312` |
| `biz_time_end` | body | mixed | 否 | 供货单发货结束时间（时间戳到秒） | `1744958170` |
| `transfer_status` | body | mixed | 否 | 转账状态 1-转账成功 2-转账失败 | `1` |
| `page` | body | mixed | 否 | 页码 1-xxx（从1开始） | `1` |
| `settlement_no` | body | string | 否 | 结算单号 | `SO123123123123123` |
| `biz_time_start` | body | mixed | 否 | 供货发货开始时间（时间戳到秒） | `1744958170` |
| `account_type` | body | string | 否 | 动账账户类型 PA-聚合账户 微信账户-NEW_WX 支付宝-ZFB 抖音支付-NEW_HZ 保证金账户-BZJ | `PA` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/getSettlementDetailList?app_key=your_appkey_here&method=supplyChain.getSettlementDetailList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 单据总条数 | `999` |
| `order_list` | array | 结算单列表 | `` |

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
  "data": {
    "order_list": [
      {
        "account_type": "PA",
        "after_sale_amount": "123",
        "biz_code": "SUPPLY-CHAIN#SEPARATE-ACCOUNTING",
        "biz_time": "1744958170",
        "distributorId": "12312312312321",
        "order_id": "6912321321321321",
        "payer_name": "分销商",
        "settle_mode": "1",
        "settle_time": "1744958170",
        "settlement_amount": "123",
        "settlement_no": "SO123123123",
        "status": "1",
        "supply_order_amount": "123",
        "trade_order_no": "CTxxxxxxxxxxxx",
        "transfer_status": "1"
      }
    ],
    "total": "999"
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
  "sub_msg": "服务错误"
}
```

## 备注
