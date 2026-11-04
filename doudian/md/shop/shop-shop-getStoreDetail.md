# shop.getStoreDetail

> 单个获取门店信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.shop.getStoreDetail` |
| 中文名 | 单个获取门店信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/getStoreDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2043 |
| 更新日期 | `2022-06-27` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 门店ID | `123` |
| `is_need_poi_audit_info` | body | boolean | 否 | 是否需要poi审核信息，注：只要审核状态的审核不要传true，需要详细的提交信息时传true | `true` |
| `is_need_rel_shop_user` | body | boolean | 否 | 是否需要关联的抖店信息，注：只要shopId不要传true，需要关联店铺名称等信息时传true | `true` |
| `is_need_charge_info` | body | boolean | 否 | 是否需要负责人信息 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/getStoreDetail?app_key=your_appkey_here&method=shop.getStoreDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_detail` | object | 门店信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "store_detail": {
      "poi_audit_info": {
        "address": "",
        "city": "",
        "contact": "",
        "district": "",
        "latitude": "",
        "longitude": "",
        "name": "",
        "open_time": {
          "custom": "",
          "day_map": {}
        },
        "poi_audit_id": "",
        "poi_audit_state": "0",
        "province": "",
        "reject_reason": "",
        "store_code": "",
        "store_id": "0"
      },
      "rel_shop_user": {
        "biz_type": "0",
        "id": "0",
        "ocean_id": "0",
        "operate_status": "0",
        "shop_charge_name": "",
        "shop_name": "",
        "shop_type": "0",
        "toutiao_id": "0",
        "v_type": "0"
      },
      "store": {
        "address": "",
        "city": "",
        "city_code": "",
        "contact": "",
        "district": "",
        "district_code": "",
        "is_open_now": "0",
        "latitude": "",
        "longitude": "",
        "name": "",
        "open_account_state": "0",
        "open_time": {
          "custom": "",
          "day_map": {}
        },
        "poi_id": "0",
        "province": "",
        "province_code": "",
        "rel_shop_id": "0",
        "state": "0",
        "store_code": "",
        "store_id": "0",
        "town": "",
        "town_code": ""
      },
      "store_charge_info": {
        "charge_mobile": "123123",
        "charge_name": "xxx"
      }
    }
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
