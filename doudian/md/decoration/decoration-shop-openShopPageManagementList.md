# shop.openShopPageManagementList

> 店铺装修-页面管理

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.shop.openShopPageManagementList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/openShopPageManagementList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6298 |
| 更新日期 | `2026-04-02` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `query_text` | body | string | 否 | 页面名称模糊查询使用 | `""` |
| `page_type` | body | mixed | 是 | 页面类型 | `2` |
| `sort_type` | body | mixed | 否 | 时间排序方式 0：不排序 1：绑定时间从新到老 2：绑定时间从老到新 | `1` |
| `page_no` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 一页中记录个数 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/openShopPageManagementList?app_key=your_appkey_here&method=shop.openShopPageManagementList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data_result` | array | 返回值 | `` |
| `page_result` | object | 分页信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / RPC调用失败（sub_code: isp.service-error:10004） | 根据报错内容排查 |

## 响应示例

成功：

```json
{
  "data": {
    "data_result": [
      {
        "bind_shop_invalid_num": "0",
        "bind_shop_num": "\"0\"",
        "bind_shop_valid_num": "0",
        "last_update_time": "\"2024-02-06T19:16:03+08:00\"",
        "operator": {
          "operator_id": "0",
          "operator_name": "系统",
          "shop_id": "155761471"
        },
        "order_ratio_7d": {
          "benchmark_ratio": "0",
          "in_period_incr": "0",
          "is_faster": "0",
          "last_period_value": "0",
          "out_period_absolute": "0",
          "out_period_incr": "0",
          "same_period_incr": "0",
          "value": "0",
          "value_ratio": "0"
        },
        "page_source": "1",
        "product_click_number_7d": {
          "benchmark_ratio": "0",
          "in_period_incr": "0",
          "is_faster": "0",
          "last_period_value": "0",
          "out_period_absolute": "0",
          "out_period_incr": "0",
          "same_period_incr": "0",
          "value": "0",
          "value_ratio": "0"
        },
        "pv_7d": {
          "benchmark_ratio": "0",
          "in_period_incr": "0",
          "is_faster": "0",
          "last_period_value": "0",
          "out_period_absolute": "0",
          "out_period_incr": "0",
          "same_period_incr": "0",
          "value": "0",
          "value_ratio": "0"
        },
        "source_shop_id": "155749636",
        "source_shop_name": "迁移showcase连锁店",
        "status": "2",
        "template_id": "7332399246898888986",
        "tmp_id": "7332424402653184307",
        "tmp_name": "数据迁移回归数据1"
      }
    ],
    "page_result": {
      "page_no": "1",
      "page_size": "10",
      "total": "1"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10004",
  "sub_msg": "RPC调用失败"
}
```

## 备注
