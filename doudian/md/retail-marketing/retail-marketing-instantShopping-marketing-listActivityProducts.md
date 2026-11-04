# instantShopping.marketing.listActivityProducts

> 即时零售商家营销工具开放服务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.listActivityProducts` |
| 中文名 | 即时零售商家营销工具开放服务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6376 |
| 更新日期 | `2024-07-10` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 当前页码，从1开始 | `1` |
| `size` | body | mixed | 是 | 分页大小 | `10` |
| `activity_id` | body | string | 是 | 活动id | `123` |
| `status` | body | mixed | 否 | Init = 10,           // 创建中 Fail = 20,           // 创建失败 Delete = 40,         // 删除 PartialSuccess = 50, // 部分成功 Success = 90,        // 创建成功 | `90` |
| `main_product_ids` | body | array | 否 | 根据主品id列表批量查询 | `['111','222','333']` |
| `main_sku_ids` | body | array | 否 | 根据主skuId列表批量查询 | `['111','222','333']` |
| `sub_product_ids` | body | array | 否 | 根据子品id列表批量查询 | `['111','222','333']` |
| `sub_sku_ids` | body | array | 否 | 根据子skuId列表批量查询 | `['111','222','333']` |
| `store_ids` | body | array | 否 | 根据门店id列表批量查询 | `[111,222,333]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.marketing.listActivityProducts&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 商品优惠明细 | `` |
| `total` | mixed | 总量 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-40000） | 检查请求参数 |
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统异常，请联系技术人员排查（sub_code: isp.service-error:-11450） | 系统异常，请联系技术人员排查 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "activity_detail": {
          "activity_price": "123",
          "limit_buy": "123",
          "stock_option": {
            "activity_stock": "123",
            "use_max_limit": "true"
          }
        },
        "create_time": "1711273687",
        "detail_status": "90",
        "detail_status_reason": "商品不存在",
        "main_product": {
          "id": "123",
          "img": "https://ehome.bytedance.net/xasdasd/1710",
          "name": "商品A",
          "status": "1"
        },
        "main_sku": {
          "id": "123",
          "img": "https://ehome.bytedance.net/xasdasd/1710",
          "name": "主SKUA",
          "original_price": "123"
        },
        "stock_info": {
          "activity_stock_remain_num": "123",
          "stock_num": "123"
        },
        "store": {
          "shop_address": "xx路xx号",
          "shop_id": "123",
          "shop_name": "xx店",
          "status": "1"
        },
        "sub_product": {
          "id": "123",
          "img": "https://ehome.bytedance.net/xasdasd/1710",
          "name": "子品A",
          "status": "1"
        },
        "sub_sku": {
          "id": "123",
          "img": "https://ehome.bytedance.net/xasdasd/1710",
          "name": "子SKUA",
          "original_price": "123"
        },
        "update_time": "1711273687"
      }
    ],
    "total": "123"
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
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
