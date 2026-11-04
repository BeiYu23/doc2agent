# pickup.searchStoreList

> 门店列表搜索

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.store.pickup.searchStoreList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/searchStoreList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7232 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `district_code` | body | string | 否 | 区编码，如 110108、440106 | `110108` |
| `biz_type` | body | mixed | 是 | 门店类型 2:到店自提 | `2` |
| `province_code` | body | string | 否 | 省编码 如 11、44 | `11` |
| `street_code` | body | string | 否 | 街道编码，如 110108011、440106010 | `110108011` |
| `size` | body | mixed | 是 | 单页大小，限制1000以内 | `10` |
| `store_code` | body | string | 否 | 门店编码 | `1138991967` |
| `poi_id_list` | body | array | 否 | 门店poi列表 | `-` |
| `city_code` | body | string | 否 | 市编码，如 110000、440100 | `110000` |
| `page` | body | mixed | 是 | 页码, 从1开始 | `1` |
| `store_id_list` | body | array | 否 | 门店id | `-` |
| `name` | body | string | 否 | 门店名称 | `测试门店1` |
| `search_type` | body | mixed | 是 | 门店信息查询类型 Effective=0生效门店,Script=1审批中门店 | `0` |
| `state_list` | body | array | 否 | 门店主状态 门店主状态，init=0初始化，poi_auditing=1poi审核中，poi_audit_success=2poi审核成功，qual_auditing=3资质审核中，qual_audit_success=4资质审核成功，open=5正常营业，suspend=6暂停营业 | `[1]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/searchStoreList?app_key=your_appkey_here&method=pickup.searchStoreList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 门店信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "store_detail_list": [
        {
          "store_script_search_info": {
            "address": "江湾城路96号",
            "announcement": "正常营业",
            "biz_type": "2",
            "bound_time": "1.73753701e+09",
            "city": "上海市",
            "city_code": "310000",
            "contact": "19812122322",
            "create_time": "1.737531505e+09",
            "district": "杨浦区",
            "district_code": "310110",
            "ext": {
              "audit_reject_reason": "-"
            },
            "latitude": "31.270755",
            "library_id_list": "-",
            "longitude": "121.522797",
            "name": "测试门店3",
            "open_account_state": "0",
            "open_account_time": "0",
            "open_time": {
              "custom": "-",
              "day_map": {}
            },
            "poi_audit_state": "0",
            "poi_id": "7462662814935566380",
            "province": "上海市",
            "province_code": "31",
            "qual_pass_time": "0",
            "qual_state": "0",
            "rel_shop_id": "1111241785",
            "remit_pass_time": "0",
            "remit_state": "0",
            "state": "5",
            "store_code": "A013",
            "store_id": "1138991967",
            "street": "江浦路街道",
            "street_code": "310110008",
            "suspend_type": "0",
            "threshold": "100",
            "update_time": "1.737537016e+09"
          },
          "store_search_info": {
            "address": "江湾城路96号",
            "announcement": "正常营业",
            "biz_type": "2",
            "bound_time": "1737537010",
            "city": "上海市",
            "city_code": "310000",
            "contact": "19812122322",
            "create_time": "1737537010",
            "district": "杨浦区",
            "district_code": "310110",
            "ext": {
              "audit_reject_reason": "-"
            },
            "latitude": "31.270755",
            "library_id_list": "-",
            "longitude": "121.522797",
            "name": "测试门店3",
            "open_account_state": "0",
            "open_account_time": "0",
            "open_time": {
              "custom": "-",
              "day_map": {}
            },
            "poi_audit_state": "0",
            "poi_id": "7462662814935566380",
            "province": "上海市",
            "province_code": "31",
            "qual_pass_time": "0",
            "qual_state": "0",
            "rel_shop_id": "1111241785",
            "remit_pass_time": "0",
            "remit_state": "0",
            "state": "5",
            "store_code": "A013",
            "store_id": "1138991967",
            "street": "江浦路街道",
            "street_code": "310110008",
            "suspend_type": "0",
            "threshold": "100",
            "update_time": "1.737537016e+09"
          }
        }
      ],
      "total": "3"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
