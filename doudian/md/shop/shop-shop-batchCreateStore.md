# shop.batchCreateStore

> 批量创建门店

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.shop.batchCreateStore` |
| 中文名 | 批量创建门店 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/batchCreateStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2040 |
| 更新日期 | `2022-08-15` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_list` | body | array | 是 | 与createStore接口入参一致 | `` |
| `  └ row_id` | body | number | 是 | 标识这行数据 | `1` |
| `  └ name` | body | string | 是 | 门店名称 | `123` |
| `  └ store_code` | body | string | 是 | 门店编码 | `123` |
| `  └ longitude` | body | string | 是 | 经度 | `123` |
| `  └ latitude` | body | string | 是 | 纬度 | `123` |
| `  └ province` | body | string | 是 | 省份 | `四川省` |
| `  └ city` | body | string | 是 | 市 | `成都市` |
| `  └ district` | body | string | 是 | 区 | `武侯区` |
| `  └ address` | body | string | 是 | 详细地址 | `xxx小区` |
| `  └ contact` | body | string | 是 | 电话 | `123` |
| `  └ open_time` | body | object | 是 | Key:用数字表示周几，例：1:周一、2:周一、5:周五、6:周六、7:周日。Value: 营业时间，多段时间用空格分隔，例：“x-x x-x”。x的区间：[00:00, 23:59]（24:00无效）。营业到次日举例："19:00-02:00"。完整举例(周3周4不营业)：{1:"12:00-16:00",2:"12:00-16:00",5:"19:00-02:00",6:"12:00-16:00",7:"12:00-16:00"} | `` |
| `    └ day_map` | body | string | 是 | Key:用数字表示周几，例：1:周一、2:周一、5:周五、6:周六、7:周日。Value: 营业时间，多段时间用空格分隔，例：“x-x x-x”。x的区间：[00:00, 23:59]（24:00无效）。营业到次日举例："19:00-02:00"。完整举例(周3周4不营业)：{1:"12:00-16:00",2:"12:00-16:00",5:"19:00-02:00",6:"12:00-16:00",7:"12:00-16:00"} | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/batchCreateStore?app_key=your_appkey_here&method=shop.batchCreateStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result_list` | array | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result_list": [
      {
        "is_success": "true",
        "msg": "invalid param",
        "store": {
          "address": "-",
          "city": "-",
          "contact": "-",
          "district": "-",
          "latitude": "-",
          "longitude": "-",
          "name": "-",
          "open_time": {
            "custom": "-",
            "day_map": {}
          },
          "province": "-",
          "rel_shop_id": "-",
          "row_id": "-",
          "store_code": "-",
          "store_id": "123"
        }
      }
    ]
  },
  "err_no": 0,
  "message": "success",
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
