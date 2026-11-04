# iop.orderList

> 【厂商】查询代打订单列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.orderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/orderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/673 |
| 更新日期 | `2024-06-25` |

## 接口说明

- 文档书: 代发API（版本 V8.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_update_time` | body | mixed | 否 | 与分配时间段二选一传入，更新时间开始时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总秒数 PS：开始时间结束时间间距不超过半小时，更新时间段与分配时间段均传入时以更新时间段为准 | `1625628558` |
| `end_update_time` | body | mixed | 否 | 与分配时间段二选一传入，更新时间开始时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总秒数 PS：开始时间结束时间间距不超过半小时，更新时间段与分配时间段均传入时以更新时间段为准 | `1625628558` |
| `page` | body | mixed | 是 | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `10` |
| `size` | body | mixed | 是 | 返回数量，最大 100 | `80` |
| `distr_status` | body | mixed | 否 | 分配状态 1-已分配未回传 2-已回传 3-已取消 | `1` |
| `start_distr_time` | body | mixed | 否 | 与更新时间段二选一传入，分配时间开始时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总秒数 PS：开始时间结束时间间距不超过半小时，更新时间段与分配时间段均传入时以更新时间段为准 | `1625628558` |
| `end_distr_time` | body | mixed | 否 | 与更新时间段二选一传入，分配时间结束时间的时间戳，指格林威治时间 1970 年 01 月 01 日 00 时 00 分 00 秒(北京时间 1970 年 01 月 01 日 08 时 00 分 00 秒)起至现在的总秒数 PS：开始时间结束时间间距不超过半小时，更新时间段与分配时间段均传入时以更新时间段为准 | `1625628558` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/orderList?app_key=your_appkey_here&method=iop.orderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_list` | array | 订单列表 | `` |
| `total` | mixed | 订单总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 结束时间不可以小于开始时间（sub_code: isv.parameter-invalid:10000） | 检查参数是否正确 |
| `20000` | 系统错误 / (空字符串)（sub_code: isp.service-error:88888） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:1000） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10005） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "order_list": [
      {
        "aftersale_status": "1",
        "buyer_words": "1",
        "city": "上海市",
        "city_id": "101000",
        "distr_cancel_reason": "订单已取消",
        "distr_order_id": "77878786688878787",
        "distr_status": "1",
        "distr_time": "1625628558",
        "district": "长宁区",
        "district_id": "101000",
        "exp_ship_time": "1625628558",
        "order_tag": {},
        "out_sku_id": "A11",
        "pack_list": [
          {
            "company_code": "jd",
            "deliver_id": "77878786688878781",
            "track_no": "123456"
          }
        ],
        "product_count": "2",
        "product_id": "1142351234",
        "product_name": "衣服",
        "product_price": "990",
        "province": "上海市",
        "province_id": "101000",
        "receiver_id": "4239E33B82F201A3D73D8DA2DDA21AD4",
        "seller_words": "发xxx快递",
        "serial_number_list": "[\"546443524543534\",\"646443524543534\"]",
        "ship_time": "1625628558",
        "sku_spec": "绿色/小",
        "spec": [
          {
            "name": "名称",
            "value": "绿色/小"
          }
        ],
        "street": "中关村",
        "street_id": "101000",
        "user_id": "55557775757756",
        "user_name": "xxx店"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "结束时间不可以小于开始时间"
}
```

## 备注
