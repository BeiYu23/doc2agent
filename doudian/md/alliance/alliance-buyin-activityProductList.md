# buyin.activityProductList

> 一级团长查询提报活动商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.activityProductList` |
| 中文名 | 一级团长查询提报活动商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/activityProductList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1926 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 页数，从1开始 | `1` |
| `size` | body | mixed | 是 | 每页条数（最大20） | `20` |
| `activity_id` | body | mixed | 是 | 活动ID | `54321` |
| `applied_sub_status` | body | mixed | 否 | 报名商品子状态。0:待审核； 1:合作中； 2:拒绝合作； 4:未合作取消； 5:合作中取消 | `0` |
| `product_info` | body | string | 否 | 商品信息（支持传商品id或者商品名称，传商品id精确匹配，传商品名称模糊匹配） | `1237623814243` |
| `sort_field` | body | mixed | 否 | 排序字段。0：默认（同百应）；1：更新时间 | `1` |
| `sort_direction` | body | mixed | 否 | 排序方式。1：升序；2：倒序，sort_field为1时有效 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/activityProductList?app_key=your_appkey_here&method=buyin.activityProductList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `products` | array | 活动商品 | `` |
| `total` | mixed | 商品总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "products": [
      {
        "ad_commission_rate": "1000",
        "ad_service_rate": "500",
        "apply_id": "2368541234412",
        "commission_rate": "1000",
        "cos_type": "1",
        "is_trusteeship_product": "true",
        "origin_activity_id": "54632",
        "origin_activity_name": "原始活动",
        "product_id": "4172957616417246",
        "product_img": "https://p6-aio.ecombdimg.com/obj/temai/a7f0a0f3b3f0140dbafe239a94301f83www800-800",
        "product_name": "一个商品",
        "product_price": "1000",
        "product_stock": "100",
        "promote_end_time": "2022-10-09",
        "promote_start_time": "2022-09-09",
        "service_rate": "1000",
        "update_time": "2006-01-02 15:04:05"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
