# install.store.ProviderStoreAPIDetail

> 服务商门店详情接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.ProviderStoreAPIDetail` |
| 中文名 | 服务商门店详情 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/ProviderStoreAPIDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7677 |
| 更新日期 | `2026-05-25` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店id | `123` |
| `category_channel` | body | mixed | 否 | 类目渠道 | `类目渠道 0 表示旧类目体系，1表示新类目体系` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.ProviderStoreAPIDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_detail` | object | 返回的门店详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-3） | 业务处理失败 |

## 响应示例

成功：

```json
{
  "data": {
    "store_detail": {
      "address": "中兴大厦",
      "audit_failed_reason": "审核失败",
      "audit_status": "1",
      "back_up_contactor": "18600000000",
      "business_license_address": "中兴大厦",
      "business_license_url": "\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"",
      "city": "北京市",
      "contactor": "18600000000",
      "contactor_name": "刘先生",
      "district": "海淀区",
      "door_image_url": "\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"",
      "last_call_status": "true",
      "open_time_desc": "[\"周一至周五 10:00-21:00\"]",
      "province": "北京市",
      "room_image_url": "[\"https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/ShopInstall/image_1753333758527825153\"]",
      "status": "1",
      "store_abilities": [
        {
          "abilities": [
            {
              "ability_id": "\"123\"",
              "ability_name": "\"123\""
            }
          ],
          "category_type": "\"123\"",
          "first_category_id": "\"123\"",
          "first_category_name": "\"123\"",
          "fourth_category_id": "\"123\"",
          "fourth_category_name": "\"123\"",
          "second_category_id": "\"123\"",
          "second_category_name": "\"123\"",
          "third_category_id": "\"123\"",
          "third_category_name": "\"123\""
        }
      ],
      "store_code": "\"123\"",
      "store_id": "12344",
      "store_name": "测试门店",
      "street": "花园路街道"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-3",
  "sub_msg": "业务处理失败"
}
```

## 备注
