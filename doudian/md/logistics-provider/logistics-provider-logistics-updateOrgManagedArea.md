# 更新服务商更新组织（省区）管理范围

> logistics.updateOrgManagedArea — 更新服务商更新组织（省区）管理范围接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 更新服务商更新组织（省区）管理范围 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-updateOrgManagedArea` |
| 接口 ID | `doudian.logistics-provider.logistics.updateOrgManagedArea` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/updateOrgManagedArea` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5678 |
| 更新日期 | `2025-06-10` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `org_code` | body | string | 是 | 组织编码（网点编码） | `test_011` |
| `change_type` | body | string | 是 | 变更类型 SAVE：添加/更新范围； DEL-删除范围 | `SAVE` |
| `area_type` | body | string | 是 | 范围类型 LEVEL_ADDRESS：行政区划 | `LEVEL_ADDRESS` |
| `managed_level_area` | body | array | 是 | 组织管理范围列表 | `` |
| `  └ province_code` | body | string | 否 | 省编码 | `11` |
| `  └ province_name` | body | string | 否 | 省名称（必填） | `北京市` |
| `  └ city_code` | body | string | 否 | 市编码 | `110000` |
| `  └ city_name` | body | string | 否 | 市名称 | `北京市` |
| `  └ district_code` | body | string | 否 | 区县编码 | `110108` |
| `  └ district_name` | body | string | 否 | 区县名称 | `海淀区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `110108018` |
| `  └ street_name` | body | string | 否 | 街道名称 | `花园路街道` |
| `  └ detail_address` | body | string | 否 | 详细地址 | `中兴大厦` |
| `  └ lon` | body | string | 否 | 经度 | `121.223344` |
| `  └ lat` | body | string | 否 | 纬度 | `37.334422` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/updateOrgManagedArea?app_key=your_appkey_here&method=logistics.updateOrgManagedArea&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fail_records` | array | 失败记录 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 必填参数为空（sub_code: isv.business-failed:-2） | 修正入参 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-3） | 修正入参 |
| `50002` | 业务处理失败 / 入参对象为空（sub_code: isv.business-failed:-7） | 修正入参 |
| `50002` | 业务处理失败 / 调用下游RPC异常（sub_code: isv.business-failed:-600） | 重试 |
| `50002` | 业务处理失败 / DB写入异常（sub_code: isv.business-failed:-301） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_records": [
      {
        "fail_desc": "xx",
        "org_info": {
          "city_code": "xx",
          "city_name": "xx",
          "detail_address": "xx",
          "district_code": "xx",
          "district_name": "xx",
          "lat": "xx",
          "lon": "xx",
          "province_code": "xx",
          "province_name": "xx",
          "street_code": "xx",
          "street_name": "xx"
        }
      }
    ]
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
  "sub_code": "isv.business-failed:-2",
  "sub_msg": "必填参数为空"
}
```

## 备注
