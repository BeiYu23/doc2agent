# shop.getStoreList

> 门店列表分页查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.shop.getStoreList` |
| 中文名 | 门店列表分页查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/getStoreList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2042 |
| 更新日期 | `2022-08-08` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_name_list` | body | array | 否 | 门店名称集合，不支持模糊 | `[xxx]` |
| `store_id_list` | body | array | 否 | 门店id集合，用于查询门店信息 | `[123]` |
| `store_code_list` | body | array | 否 | 门店编码 | `[123,aaa]` |
| `state` | body | number | 否 | 绑定状态，1绑定中;2绑定成功;3:资质验证中;4账户认证中;5正常营业(c端可下单) | `5` |
| `poi_audit_state` | body | array | 否 | poi审核状态：0无提审;1审核中;2审核成功;3驳回 | `[1,2]` |
| `province` | body | string | 否 | 省 | `四川省` |
| `city` | body | string | 否 | 市 | `成都市` |
| `district` | body | string | 否 | 区 | `高新区` |
| `poi_id_list` | body | array | 否 | 门店poiId集合 | `[123]` |
| `name_fuzzy` | body | string | 否 | 门店名称，支持模糊查询 | `xxx` |
| `store_code_fuzzy` | body | string | 否 | 门店编码，支持模糊查询 | `xxx` |
| `qual_state` | body | number | 否 | 资质审核状态，0未提交；1审核中；2审核通过；3驳回 | `2` |
| `remit_state` | body | number | 否 | 账户验证状态，0未提交；1验证中；2通过；3失败 | `2` |
| `open_account_state` | body | number | 否 | 开户状态：0未开户;1已开户 | `1` |
| `is_need_poi_audit_info` | body | boolean | 否 | 是否需要poi审核信息，注：只要审核状态的审核不要传true，需要详细的提交信息时传true | `1` |
| `is_need_rel_shop_user` | body | boolean | 否 | 是否需要关联的抖店信息，注：只要shopId不要传true，需要关联店铺名称等信息时传true | `1` |
| `page` | body | number | 是 | 第几页(从0开始) | `0` |
| `page_size` | body | number | 是 | 每页条数 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/getStoreList?app_key=your_appkey_here&method=shop.getStoreList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 总数 | `10` |
| `store_detail_list` | array | 与getStoreDetail接口返回一致 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "store_detail_list": [
      {
        "poi_audit_info": {
          "address": "与getStoreDetail接口返回一致",
          "city": "与getStoreDetail接口返回一致",
          "contact": "与getStoreDetail接口返回一致",
          "district": "与getStoreDetail接口返回一致",
          "latitude": "与getStoreDetail接口返回一致",
          "longitude": "与getStoreDetail接口返回一致",
          "name": "与getStoreDetail接口返回一致",
          "open_time": {
            "custom": "与getStoreDetail接口返回一致",
            "day_map": {}
          },
          "poi_audit_id": "与getStoreDetail接口返回一致",
          "poi_audit_state": "与getStoreDetail接口返回一致",
          "province": "与getStoreDetail接口返回一致",
          "reject_reason": "与getStoreDetail接口返回一致",
          "store_code": "与getStoreDetail接口返回一致",
          "store_id": "与getStoreDetail接口返回一致"
        },
        "rel_shop_user": {
          "biz_type": "与getStoreDetail接口返回一致",
          "id": "与getStoreDetail接口返回一致",
          "ocean_id": "与getStoreDetail接口返回一致",
          "operate_status": "与getStoreDetail接口返回一致",
          "shop_charge_name": "与getStoreDetail接口返回一致",
          "shop_name": "与getStoreDetail接口返回一致",
          "shop_type": "与getStoreDetail接口返回一致",
          "toutiao_id": "与getStoreDetail接口返回一致",
          "v_type": "与getStoreDetail接口返回一致"
        },
        "store": {
          "address": "与getStoreDetail接口返回一致",
          "city": "与getStoreDetail接口返回一致",
          "city_code": "与getStoreDetail接口返回一致",
          "contact": "与getStoreDetail接口返回一致",
          "district": "与getStoreDetail接口返回一致",
          "district_code": "与getStoreDetail接口返回一致",
          "is_open_now": "与getStoreDetail接口返回一致",
          "latitude": "与getStoreDetail接口返回一致",
          "longitude": "与getStoreDetail接口返回一致",
          "name": "与getStoreDetail接口返回一致",
          "open_account_state": "与getStoreDetail接口返回一致",
          "open_time": {
            "custom": "与getStoreDetail接口返回一致",
            "day_map": {}
          },
          "poi_id": "与getStoreDetail接口返回一致",
          "province": "与getStoreDetail接口返回一致",
          "province_code": "与getStoreDetail接口返回一致",
          "rel_shop_id": "与getStoreDetail接口返回一致",
          "state": "与getStoreDetail接口返回一致",
          "store_code": "与getStoreDetail接口返回一致",
          "store_id": "与getStoreDetail接口返回一致",
          "town": "与getStoreDetail接口返回一致",
          "town_code": "与getStoreDetail接口返回一致"
        },
        "store_charge_info": {
          "charge_mobile": "与getStoreDetail接口返回一致",
          "charge_name": "与getStoreDetail接口返回一致"
        }
      }
    ],
    "total": "10"
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
