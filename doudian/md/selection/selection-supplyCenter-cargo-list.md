# supplyCenter.cargo.list

> 精选货源获取货品列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.cargo.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/cargo/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5336 |
| 更新日期 | `2023-11-09` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 是 | 页码，从1开始，最大为100；page* size最大不能超过1万条 | `1` |
| `size` | body | number | 是 | 页数，填写范围1~100；page* size最大不能超过1万条 | `10` |
| `use_cursor` | body | boolean | 否 | 是否使用游标，true 使用，false 不使用；使用游标能遍历全量商品，不会受到只能查询到10000个数据的影响。 特别说明：使用游标查询时，page字段失效，只会查询当前游标后面size条数据；根据获取查询数据为空来判断本次遍历结束；查询过程中数据发生变更，可能重复、遗漏数据；需要保证每次查询的筛选条件一致。 | `true` |
| `cursor_id` | body | string | 否 | 游标id，结合use_cursor使用（use_cursor=true）;首次查询时不需要传值，每次查询结果会返回cursor_id，下一次查询时复制给该字段。当查询返回数据为空时，结束遍历。 | `WzE2ODI1Nzc4MjksMTc2NDMxMDczMDU3MDg0M10=` |
| `name` | body | string | 否 | 商品标题，支持模糊匹配 | `标题` |
| `product_id` | body | array | 否 | 商品id，最大支持传入100个； | `12345` |
| `status` | body | number | 否 | 商品在店铺中状态: 0-在线；1-下线；2-删除；详见商品状态机：https://op.jinritemai.com/docs/question-docs/92/2070 | `0` |
| `check_status` | body | number | 否 | 商品审核状态: 1-未提交；2-待审核；3-审核通过；4-审核未通过；5-封禁；7-审核通过待上架；详见商品状态机：https://op.jinritemai.com/docs/question-docs/92/2070 | `3` |
| `start_time` | body | number | 否 | 商品创建开始时间，unix时间戳，单位：秒； | `1619161933` |
| `end_time` | body | number | 否 | 商品创建结束时间，unix时间戳，单位：秒； | `1619162000` |
| `update_start_time` | body | number | 否 | 商品更新开始时间，unix时间戳，单位：秒；注意：查询范围是update_start_time和update_end_time之间的数据，不包含入参时间。 | `1619161933` |
| `update_end_time` | body | number | 否 | 商品更新结束时间，unix时间戳，单位：秒；注意：查询范围是update_start_time和update_end_time之间的数据，不包含入参时间。 | `1619162000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.cargo.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 商品数据 | `` |
| `total` | number | 本次查询返回的商品总数 | `10000` |
| `page` | number | 当前页码 | `10` |
| `size` | number | 页数（每页数量） | `100` |
| `cursor_id` | string | 使用游标时，每次查询会返回该值，作为下次查询的入参使用。 | `WzE2ODI1Nzc4MjksMTc2NDMxMDczMDU3MDg0M10=` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照商品列表接口（sub_code: isv.parameter-invalid:66666） | https://op.jinritemai.com/docs/api-docs/14/633 |

## 响应示例

成功：

```json
{
  "data": {
    "cursor_id": "WzE2ODI1Nzc4MjksMTc2NDMxMDczMDU3MDg0M10=",
    "data": [
      {
        "category_detail": {
          "first_cid": "20117",
          "first_cname": "本地生活服务",
          "fourth_cid": "31800",
          "fourth_cname": "咖啡",
          "second_cid": "22139",
          "second_cname": "餐饮美食卡券",
          "third_cid": "28901",
          "third_cname": "甜品/冰淇淋/咖啡/冷饮"
        },
        "check_status": "3",
        "create_time": "1619161933",
        "description": "<p><img src=\\\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933\\\" style=\\\"max-width:100%;\\\"/><img src=\\\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153426724709337920183_dd825b6f3c1bc43ec26faea488447709_sx_1059417_www1080-933\\\" style=\\\"max-width:100%;\\\"/><img src=\\\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153465487927217040183_d963cc36ef6e66c0cba70e4cb2188f88_sx_436442_www1920-1080\\\" style=\\\"max-width:100%;\\\"/></p>",
        "draft_status": "3",
        "freight_remark": "1-5元",
        "freight_type": "3",
        "img": "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933",
        "name": "夏季男生白色短袖",
        "outer_platform": "1",
        "outer_product_id": "12345",
        "outer_sell_num": "20000",
        "outer_sort_factor": "20000",
        "product_id": "12231829784718",
        "status": "0",
        "supplier_company_name": "xxx公司",
        "supplier_id": "1234",
        "supplier_license_no": "9xxxxxxxxxxxM",
        "supplier_phone": "40010000",
        "update_time": "1619161933"
      }
    ],
    "page": "10",
    "size": "100",
    "total": "10000"
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
  "sub_code": "isv.parameter-invalid:66666",
  "sub_msg": "参照商品列表接口"
}
```

## 备注
