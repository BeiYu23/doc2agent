# logistics.updateOrganizationInfo

> 更新服务商组织信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.updateOrganizationInfo` |
| 中文名 | 更新服务商组织信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/updateOrganizationInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5677 |
| 更新日期 | `2025-06-10` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `org_list` | body | array | 是 | 组织列表（最多支持50条数据） | `` |
| `  └ site_type` | body | mixed | 否 | 站点类型；1-揽收网点，2-派送网点，3-揽派网点，4-干线分拨，5-集散中心 | `2` |
| `  └ org_contact` | body | object | 否 | 联系人信息 | `` |
| `    └ name` | body | string | 否 | 名称 | `小李` |
| `    └ phone` | body | string | 否 | 电话 | `138xxxxxxxx` |
| `  └ org_status` | body | mixed | 是 | 组织状态 1：生效 2：不生效 | `1` |
| `  └ org_code` | body | string | 是 | 组织编码（网点编码） | `test_011` |
| `  └ org_name` | body | string | 是 | 组织名称（网点名称） | `北京省区测试` |
| `  └ org_type` | body | string | 是 | 组织类型（网点类型） ZONG_BU：总部 SHENG_QU：省区 FEN_BO_GUAN_LI：分拨管理 WANG_DIAN_GUAN_LI：网点管理 FEN_BO_ZHONG_XIN：分拨中心 WANG_DIAN：网点 | `SHENG_QU` |
| `  └ father_org_code` | body | string | 否 | 上级组织编码（父网点编码） | `test_001` |
| `  └ father_org_name` | body | string | 否 | 上级组织名称（父网点名称） | `测试总部网点` |
| `  └ org_address` | body | object | 否 | 组织地址（网点地址） | `` |
| `    └ province_code` | body | string | 否 | 省编码 | `11` |
| `    └ province_name` | body | string | 否 | 省名称 org_type = SHENG_QU，FEN_BO_ZHONG_XIN，WANG_DIAN时必填 | `北京市` |
| `    └ city_code` | body | string | 否 | 市编码 | `110000` |
| `    └ city_name` | body | string | 否 | 市名称 org_type = SHENG_QU，FEN_BO_ZHONG_XIN，WANG_DIAN 时必填 | `北京市` |
| `    └ district_code` | body | string | 否 | 区县编码 | `110108` |
| `    └ district_name` | body | string | 否 | 区县名称 org_type = FEN_BO_ZHONG_XIN，WANG_DIAN 时必填 | `海淀区` |
| `    └ street_code` | body | string | 否 | 街道编码 | `110108018` |
| `    └ street_name` | body | string | 否 | 街道名称 | `花园路街道` |
| `    └ detail_address` | body | string | 否 | 详细地址 | `中兴大厦` |
| `    └ lon` | body | string | 否 | 经度 | `121.223344` |
| `    └ lat` | body | string | 否 | 纬度 | `37.334422` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/updateOrganizationInfo?app_key=your_appkey_here&method=logistics.updateOrganizationInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fail_records` | array | 失败记录 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_records": [
      {
        "fail_desc": "xx",
        "org_info": {
          "father_org_code": "xx",
          "father_org_name": "xx",
          "org_address": {
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
          },
          "org_code": "xx",
          "org_contact": {
            "name": "xx",
            "phone": "xx"
          },
          "org_name": "xx",
          "org_status": "1",
          "org_type": "ZONG_BU",
          "site_type": "1"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
