# order.searchByReceiver

> 根据收件人姓名、手机号查询订单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.searchByReceiver` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/searchByReceiver` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/3615 |
| 更新日期 | `2023-05-26` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `post_type` | body | number | 是 | 查询类型：0-收货人手机号，1-收货人姓名 | `1` |
| `post_receiver` | body | string | 是 | 收货人手机号或收货人姓名 | `张三` |
| `create_time_start` | body | number | 否 | 下单时间：开始，秒级时间戳。只允许查最近90天的订单，不传默认按90天前处理 | `1617355413` |
| `create_time_end` | body | number | 否 | 下单时间：截止，秒级时间戳。不传默认按现在处理 | `1617355414` |
| `size` | body | number | 是 | 单页大小，限制100以内 | `10` |
| `page` | body | number | 是 | 页码，0页开始 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/searchByReceiver?app_key=your_appkey_here&method=order.searchByReceiver&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `page` | number | 页数，从0开始 | `0` |
| `total` | number | 总订单数 | `10` |
| `size` | number | 单页大小 | `10` |
| `shop_order_list` | array | 订单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 查询收货人类型错误（sub_code: isv.parameter-invalid:20051） | post_type传0或1 |
| `40004` | 非法的参数 / 收货人参数不能为空（sub_code: isv.parameter-invalid:20052） | post_receiver不能传空值 |
| `40004` | 非法的参数 / 收货人手机号不正确（sub_code: isv.parameter-invalid:20053） | 传入正确的手机号 |
| `40004` | 非法的参数 / 只支持查询最近90天内的数据（sub_code: isv.parameter-invalid:20022） | 需要把下单开始时间设置为最近90天内的时间（如果没有传下单开始时间会默认设置当前时间90天前的时间为下单开始时间） |
| `40004` | 非法的参数 / 订单查询开始时间不能晚于结束时间（sub_code: isv.parameter-invalid:20048） | 传入正确的下单开始时间和结束时间 |
| `40004` | 非法的参数 / 单次最多支持查询100条（sub_code: isv.parameter-invalid:20008） | 单页最大支持100，size设置需要 <= 100 |
| `40004` | 非法的参数 / 查询订单列表页数不能小于0（sub_code: isv.parameter-invalid:10035） | 查询页数从0开始，需要输入大于等于0的数 |
| `40004` | 非法的参数 / 最多支持查询1000条（sub_code: isv.parameter-invalid:20013） | 翻页查询最多支持查询到1000，需要缩短查询时间范围，降低查询的订单量 |
| `20000` | 系统错误 / 查询异常，请稍后重试（sub_code: isp.service-error:20002） | 如遇到该报错，建议再重试3~5次，如还是报错可提交工单咨询 |
| `20000` | 系统错误 / 查询异常，请稍后重试（sub_code: isp.service-error:20054） | 如遇到该报错，建议再重试3~5次，如还是报错可提交工单咨询 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20005） | 如遇到该报错，建议再重试3~5次，如还是报错可提交工单咨询 |
| `80000` | 风控拦截（sub_code: isv.risk-control-failed:20047） | 无 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "0",
    "shop_order_list": [
      {
        "create_time": "1617355413",
        "order_id": "4781320682406083640",
        "order_status": "3"
      }
    ],
    "size": "10",
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:20051",
  "sub_msg": "查询收货人类型错误"
}
```

## 备注
