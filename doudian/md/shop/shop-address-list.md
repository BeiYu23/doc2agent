# address.list

> 批量查询地址库列表接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.address.list` |
| 中文名 | 批量查询地址库列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/1435 |
| 更新日期 | `2025-03-17` |

## 接口说明

- 文档书: 店铺API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id` | body | mixed | 否 | 【已废弃】店铺id | `123` |
| `page_size` | body | mixed | 是 | 翻页每页数量，默认10 | `10` |
| `page_no` | body | mixed | 是 | 翻页页数，从1开始 | `1` |
| `order_by` | body | string | 是 | 排序方式支持asc/desc | `asc/desc` |
| `order_field` | body | string | 是 | 排序字段；create_time-创建时间排序，update_time-更新时间排序； | `create_time/update_time` |
| `store_id` | body | mixed | 否 | 门店ID，抖超小时达业务使用传入后只获取该门店下地址列表； | `123` |
| `is_send_home_open_req` | body | boolean | 否 | 大盘传false，即时零售商家必传true | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/list?app_key=your_appkey_here&method=address.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 地址总数 | `10` |
| `page_size` | mixed | 页码 | `1` |
| `page_no` | mixed | 每页数量 | `10` |
| `address_list` | array | 地址列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请输入正确的排序方式（sub_code: isv.parameter-invalid:5001） | 请输入正确参数 |

## 响应示例

成功：

```json
{
  "data": {
    "address_list": [
      {
        "address_id": "1",
        "biz_id": "123",
        "biz_type": "1",
        "common_phone": {
          "area_num": "0635",
          "auxiliary_num": "1111",
          "main_num": "5781308",
          "num": "0635-5781308-1111"
        },
        "company_phone": {
          "num": "40088881111234",
          "phone_num": "40088881111234"
        },
        "create_time": "\"1622103276\"",
        "is_default": "1-是；0-否",
        "is_send_default": "1-是；0-否",
        "link_type": "1",
        "mobile": "0635-5781308",
        "phone": "13288889999",
        "receiver_city": "北京",
        "receiver_detail": "xxxx",
        "receiver_district": "海淀区",
        "receiver_provinc": "北京市",
        "receiver_street": "丹棱街",
        "reciever_name": "张三",
        "remark": "请发顺丰快递",
        "update_time": "\"1622103276\""
      }
    ],
    "page_no": "10",
    "page_size": "1",
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
  "sub_code": "isv.parameter-invalid:5001",
  "sub_msg": "请输入正确的排序方式"
}
```

## 备注
