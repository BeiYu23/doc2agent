# install.store.providerStoreAPIList

> 服务商门店列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.providerStoreAPIList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/providerStoreAPIList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7675 |
| 更新日期 | `2026-05-25` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 否 | 门店名称模糊匹配 | `门店名称` |
| `store_custom_codes` | body | array | 否 | 门店自用编码筛选 | `门店自用编码` |
| `audit_status` | body | array | 否 | 门店审核状态筛选 | `1` |
| `rn` | body | mixed | 否 | 每一页数量 | `10` |
| `store_ids` | body | array | 否 | 门店id筛选 | `[123,456]` |
| `phone_call_state` | body | boolean | 否 | 隐私号接通状态筛选，true:接通，false:未接通 | `true` |
| `store_status` | body | array | 否 | 门店状态筛选 | `1：门店上线 2：下线 4：审核中 5：审核成功 6：审核失败` |
| `pn` | body | mixed | 否 | 页码 | `1` |
| `addr_params` | body | array | 否 | 地址匹配使用的param，上面的省市区县的字段可以不使用了 | `` |
| `  └ district` | body | string | 否 | 区 | `海淀区` |
| `  └ city` | body | string | 否 | 市 | `北京市` |
| `  └ street` | body | string | 否 | 县 | `花园路街道` |
| `  └ province` | body | string | 否 | 省 | `北京市` |
| `audit_callback_time_param` | body | object | 否 | 审核时间 | `` |
| `  └ start_time` | body | mixed | 否 | 查询的起始时间，时间戳 | `1752637538` |
| `  └ end_time` | body | mixed | 否 | 查询的结束时间，时间戳 | `1752637538` |
| `category_channel` | body | mixed | 否 | 类目渠道 | `0表示旧类目体系能力 1 表示新类目体系能力` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.providerStoreAPIList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pn` | mixed | 页码 | `1` |
| `rn` | mixed | 页面数量 | `10` |
| `total` | mixed | 门店总量 | `100` |
| `store_list` | array | 门店信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "pn": "1",
    "rn": "10",
    "store_list": [
      {
        "address": "中兴大厦",
        "audit_callback_time": "1752637538",
        "audit_failed_reason": "审核失败",
        "audit_status": "2",
        "back_up_contactor": "18600000000",
        "business_license_address": "\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"",
        "business_license_url": "\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"",
        "city": "北京市",
        "contactor": "18600000000",
        "contactor_name": "刘先生",
        "create_time": "1753973349",
        "district": "花园路街道",
        "door_image_url": "\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"",
        "last_call_status": "true",
        "open_time_desc": "[\"周一至周五 10:00-23:00\"]",
        "province": "北京市",
        "room_image_url": "[\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"]",
        "status": "1",
        "store_abilities": [
          {
            "abilities": [
              {
                "ability_id": "34226_304099_7696",
                "ability_name": "安装刹车片(不含解码)_黄色"
              }
            ],
            "category_type": "0",
            "first_category_id": "\"123\"",
            "first_category_name": "\"123\"",
            "fourth_category_id": "”123“",
            "fourth_category_name": "\"123\"",
            "second_category_id": "\"123\"",
            "second_category_name": "\"123\"",
            "third_category_id": "\"123\"",
            "third_category_name": "”123“"
          }
        ],
        "store_code": "abc",
        "store_id": "123",
        "store_name": "门店名称",
        "street": "海淀区"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
