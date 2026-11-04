# compass.CommonProductQueryData

> 数据T+1生成，建议第二天10点之后查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.compass.CommonProductQueryData` |
| 中文名 | 数据T+1生成，建议第二天10点之后查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/compass/CommonProductQueryData` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2768 |
| 更新日期 | `2022-11-29` |

## 接口说明

- 文档书: 商品API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `end_date` | body | string | 是 | 周期结束时间,T-1;如3月24号查询近7天的数据，入参date_type=21&&end_date=“2023-03-23” | `2022/11/15 23:59:59` |
| `date_type` | body | string | 是 | REALTIME          = 1   // 实时 BeginDate和EndDate都不传入 表示查询今日实时数据 BeginDate和EndDate都传入 表示查询BeginDate～EndDate的实时数据；     DAY               = 2   // 自然日 BeginDate和EndDate都传入 表示查询趋势 只传入BeginDate表示查询该自然日；     WEEK              = 3   // 自然周 传入BeginDate（周一的日期） 指定对应自然周；     MONTH             = 4   // 自然月 传入BeginDate（月一号的日期） 指定对应自然月；     LAST_ONE_DAYS     = 20  // 近一日；     LAST_SEVEN_DAYS   = 21  // 近七日 当日为基准；     LAST_THREE_DAYS   = 22  // 近三日 当日为基准；     LAST_ONE_MONTH    = 23  // 近30日 当日为基准； | `21` |
| `activity_id` | body | string | 否 | 大促id，非大促默认使用空字符串“” | `105241` |
| `begin_date` | body | string | 是 | 周期开始时间 | `2022/11/15 00:00:00` |
| `product_id` | body | string | 是 | 商品id | `3579566747054921902` |
| `page_no` | body | number | 否 | 页码，默认为1 | `1` |
| `page_size` | body | number | 否 | 页面大小，默认为10 | `10` |
| `sorted_field` | body | string | 否 | 排序字段，支持product_show_ucnt,product_click_ucnt,product_click_ratio,pay_ucnt,pay_cnt,product_pay_ratio | `product_show_ucnt` |
| `is_asc` | body | boolean | 否 | 排序方向，默认降序 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/info?app_key=your_appkey_here&method=warehouse.info&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_list` | array | 商品数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 621000704:调用下游失败，请稍后重试（sub_code: isv.business-failed:621000704） | 请重试 |
| `50002` | 业务处理失败 / 621000625:当前没有权限访问（sub_code: isv.business-failed:621000625） | 请检查是否拥有权限 |
| `50002` | 业务处理失败 / 621000602:参数非法（sub_code: isv.business-failed:621000602） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "addr": [
        {
          "addr_id1": "1",
          "addr_id2": "2",
          "addr_id3": "3",
          "addr_id4": "4",
          "create_time": "1624245280",
          "update_time": "1624245280"
        }
      ],
      "address_detail": "\"\"",
      "create_time": "1624245280",
      "intro": "介绍测试",
      "name": "名称测试",
      "out_fence_ids": "[\"1\", \"2\"]",
      "out_warehouse_id": "ABC",
      "shop_id": "95250",
      "update_time": "1624245280",
      "warehouse_id": "6152361283123",
      "warehouse_location": {
        "address_id1": "11",
        "address_id2": "110000",
        "address_id3": "110101",
        "address_id4": "0",
        "address_name1": "北京市",
        "address_name2": "北京市",
        "address_name3": "东城区",
        "address_name4": "\"\""
      }
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:621000704",
  "sub_msg": "621000704:调用下游失败，请稍后重试"
}
```

## 备注
