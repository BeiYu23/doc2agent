# second.brand.getBrandQualInfos

> 【二方接口】查询品牌资质信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.brand.getBrandQualInfos` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/brand/getBrandQualInfos` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6941 |
| 更新日期 | `2024-10-15` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 商业化账号组uid，用作鉴权 | `15495388485` |
| `shopId` | body | mixed | 否 | 店铺ID | `5055915` |
| `holder` | body | object | 否 | holder | `` |
| `  └ objectId` | body | mixed | 否 | 对象id，\n当object_type是店铺的时候，是店铺id\n当object_type是机构的时候，是机构id\n当object_type是服务市场服务商的时候，是服务商id\nint64->string | `8109181` |
| `  └ objectType` | body | mixed | 否 | 对象类型 | `1753215` |
| `extraOptions` | body | object | 否 | extra_options | `` |
| `  └ excludeDisplayedUrl` | body | boolean | 否 | excludeDisplayedUrl 不返回图片URL | `false` |
| `  └ includeInvalid` | body | boolean | 否 | includeInvalid 是否包含无效品牌资质(失效、封禁) | `false` |
| `  └ excludeCategory` | body | boolean | 否 | excludeCategory 排除类目返回 | `false` |
| `  └ excludeAggregatedCategory` | body | boolean | 否 | excludeAggregatedCategory 不聚合类目信息，为true时将只返回category_id, 且没有Name | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.brand.getBrandQualInfos&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_qual_infos` | array | brand_qual_infos | `[]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / uid不能为空（sub_code: isp.service-error:300001） | uid不能为空 |
| `20000` | 系统错误 / shopId不能为空（sub_code: isp.service-error:300002） | shopId不能为空 |
| `20000` | 系统错误 / objectId不能为空（sub_code: isp.service-error:300003） | objectId不能为空 |
| `20000` | 系统错误 / objectType不能为空（sub_code: isp.service-error:300004） | objectType不能为空 |
| `20000` | 系统错误 / excludeDisplayedUrl不能为空（sub_code: isp.service-error:300005） | excludeDisplayedUrl不能为空 |
| `20000` | 系统错误 / includeInvalid不能为空（sub_code: isp.service-error:300006） | includeInvalid不能为空 |
| `20000` | 系统错误 / excludeCategory不能为空（sub_code: isp.service-error:300007） | excludeCategory不能为空 |
| `20000` | 系统错误 / excludeAggregatedCategory不能为空（sub_code: isp.service-error:300008） | excludeAggregatedCategory不能为空 |
| `20000` | 系统错误 / 店铺鉴权失败（sub_code: isp.service-error:500004） | 店铺鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "brand_qual_infos": [
      {
        "brand_info": {
          "brand_id": "4366412",
          "cn_name": "a7d95216",
          "en_name": "93860b34",
          "relate_id": "1774893"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:300001",
  "sub_msg": "uid不能为空"
}
```

## 备注
