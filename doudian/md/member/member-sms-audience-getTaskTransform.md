# sms.audience.getTaskTransform

> 获取任务转化数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.audience.getTaskTransform` |
| 中文名 | 获取任务转化数据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/getTaskTransform` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6751 |
| 更新日期 | `2025-10-15` |

## 接口说明

- 文档书: 会员中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_id` | body | mixed | 是 | 任务ID。当任务id传0，返回单条发送&批量发送的转化效果 | `123` |
| `send_date` | body | string | 否 | 发送时间，仅在taskId=0时有效。格式为'yyyyMMdd' | `20250618` |
| `data_date` | body | string | 否 | 时间分区，格式为yyyyMMdd;不传入则返回最新分区的数据 | `20251010` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.audience.getTaskTransform&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_cnt` | mixed | 成功数量 | `10` |
| `seven_day_order_user_cnt` | mixed | 7天下单用户数 | `11` |
| `one_day_order_amt` | mixed | 24h订单金额转化（单位：分） | `12` |
| `one_day_order_user_cnt` | mixed | 24h下单用户数 | `12` |
| `date_partition` | string | 日期分区 | `20240823` |
| `task_id` | mixed | 任务ID | `12` |
| `success_bill_cnt` | mixed | 成功计费条数 | `2312` |
| `seven_day_order_amt` | mixed | 7天订单金额转化（单位：分） | `123121` |
| `one_day_recall_user_cnt` | mixed | 24h召回用户数 | `1212` |
| `one_day_prod_show_cnt` | mixed | 24h商品详情页PV | `123` |
| `one_day_pay_prod_cnt` | mixed | 24h付款件数 | `123` |
| `seven_day_crt_ord_user_cnt` | mixed | 7d下单人数 | `123` |
| `seven_day_crt_amt` | mixed | 7d下单金额(单位：分) | `1234` |
| `seven_day_join_user_cnt` | mixed | 7d新入会人数 | `123` |
| `one_day_prod_show_user_cnt` | mixed | 24h商品详情页UV | `123` |
| `seven_day_prod_show_user_cnt` | mixed | 7d商品详情页UV | `123` |
| `seven_day_join_pay_ord_cnt` | mixed | 7d新入会购买次数 | `111` |
| `seven_day_prod_wish_user_cnt` | mixed | 7d收藏UV | `123` |
| `one_day_pay_ord_cnt` | mixed | 24h付款PV | `111` |
| `seven_day_pay_prod_cnt` | mixed | 7d付款件数 | `123` |
| `one_day_crt_ord_user_cnt` | mixed | 24h下单人数 | `123` |
| `seven_day_join_pay_ord_user_cnt` | mixed | 7d新入会购买UV | `543` |
| `seven_day_crt_prod_cnt` | mixed | 7d下单件数 | `534` |
| `one_day_join_user_cnt` | mixed | 24h新入会人数 | `53` |
| `seven_day_prod_show_cnt` | mixed | 7d商品详情页PV | `12` |
| `one_day_crt_ord_cnt` | mixed | 24h下单PV | `42` |
| `seven_day_crt_ord_cnt` | mixed | 7d下单PV | `64` |
| `one_day_crt_prod_cnt` | mixed | 24h下单件数 | `123` |
| `seven_day_pay_ord_cnt` | mixed | 7d付款PV | `543` |
| `one_day_crt_amt` | mixed | 24h下单金额 | `123` |
| `send_cnt` | mixed | 触达人数 | `341` |
| `one_day_join_pay_ord_cnt` | mixed | 24h新入会购买PV | `123` |
| `one_day_join_pay_ord_user_cnt` | mixed | 24h新入会购买UV | `123` |
| `one_day_prod_wish_user_cnt` | mixed | 24h收藏UV | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:628002001） | 请重新检查入参 |
| `50002` | 业务处理失败 / 628003309:暂未查询到任务转化数据（sub_code: isv.business-failed:628003309） | 628003309:暂未查询到任务转化数据 |
| `50002` | 业务处理失败 / 628004000:系统错误（sub_code: isv.business-failed:628004000） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "date_partition": "20240823",
    "one_day_crt_amt": "123",
    "one_day_crt_ord_cnt": "42",
    "one_day_crt_ord_user_cnt": "123",
    "one_day_crt_prod_cnt": "123",
    "one_day_join_pay_ord_cnt": "123",
    "one_day_join_pay_ord_user_cnt": "123",
    "one_day_join_user_cnt": "53",
    "one_day_order_amt": "12",
    "one_day_order_user_cnt": "12",
    "one_day_pay_ord_cnt": "111",
    "one_day_pay_prod_cnt": "123",
    "one_day_prod_show_cnt": "123",
    "one_day_prod_show_user_cnt": "123",
    "one_day_prod_wish_user_cnt": "123",
    "one_day_recall_user_cnt": "1212",
    "send_cnt": "341",
    "seven_day_crt_amt": "1234",
    "seven_day_crt_ord_cnt": "64",
    "seven_day_crt_ord_user_cnt": "123",
    "seven_day_crt_prod_cnt": "534",
    "seven_day_join_pay_ord_cnt": "111",
    "seven_day_join_pay_ord_user_cnt": "543",
    "seven_day_join_user_cnt": "123",
    "seven_day_order_amt": "123121",
    "seven_day_order_user_cnt": "11",
    "seven_day_pay_ord_cnt": "543",
    "seven_day_pay_prod_cnt": "123",
    "seven_day_prod_show_cnt": "12",
    "seven_day_prod_show_user_cnt": "123",
    "seven_day_prod_wish_user_cnt": "123",
    "success_bill_cnt": "2312",
    "success_cnt": "10",
    "task_id": "12"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "参数非法"
}
```

## 备注
