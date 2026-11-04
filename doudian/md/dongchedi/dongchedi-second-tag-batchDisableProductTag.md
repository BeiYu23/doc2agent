# 【二方接口】商品批量去标

> second.tag.batchDisableProductTag — 【二方接口】商品批量去标

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【二方接口】商品批量去标 |
| 文档地址 | `/docs/doudian/dongchedi/dongchedi-second-tag-batchDisableProductTag` |
| 接口 ID | `doudian.dongchedi.second.tag.batchDisableProductTag` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/tag/batchDisableProductTag` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6942 |
| 更新日期 | `2024-10-15` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 商业化账号组uid，用作鉴权 | `15495388485` |
| `productTags` | body | array | 否 | productTags | `[]` |
| `  └ shopId` | body | mixed | 否 | shopId | `5055915` |
| `  └ tagCode` | body | string | 否 | tagCode | `5169adc9` |
| `  └ tagVal` | body | string | 否 | tagVal | `b046b431` |
| `  └ productId` | body | mixed | 否 | productId | `9612565` |
| `operator` | body | object | 否 | operator | `` |
| `  └ userId` | body | string | 否 | userId | `2dcc30e6` |
| `  └ userName` | body | string | 否 | userName | `a95e4149` |
| `tagSource` | body | mixed | 否 | tagSource | `8337850` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/tag/batchDisableProductTag?app_key=your_appkey_here&method=second.tag.batchDisableProductTag&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `successList` | array | successList | `[]` |
| `failedList` | array | failedList | `[]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / uid不能为空（sub_code: isp.service-error:300001） | uid不能为空 |
| `20000` | 系统错误 / productTags不能为空（sub_code: isp.service-error:300002） | productTags不能为空 |
| `20000` | 系统错误 / 只能更改同一店铺的商品Tag（sub_code: isp.service-error:300003） | 只能更改同一店铺的商品Tag |
| `20000` | 系统错误 / userId不能为空（sub_code: isp.service-error:300004） | userId不能为空 |
| `20000` | 系统错误 / userName不能为空（sub_code: isp.service-error:300005） | userName不能为空 |
| `20000` | 系统错误 / tagCode不能为空（sub_code: isp.service-error:300006） | tagCode不能为空 |
| `20000` | 系统错误 / tagVal不能为空（sub_code: isp.service-error:300007） | tagVal不能为空 |
| `20000` | 系统错误 / productId不能为空（sub_code: isp.service-error:300008） | productId不能为空 |
| `20000` | 系统错误 / 店铺鉴权失败（sub_code: isp.service-error:500004） | 店铺鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "failedList": [
      {
        "channel": {
          "channelId": "5714884",
          "channelType": "4543034"
        },
        "productId": "4620210",
        "shopId": "3330051",
        "tagCode": "cb8cc6ad",
        "tagVal": "38c2c825"
      }
    ],
    "successList": [
      {
        "channel": {
          "channelId": "3255576",
          "channelType": "3961043"
        },
        "productId": "5214315",
        "shopId": "1295438",
        "tagCode": "dbe2be84",
        "tagVal": "11fce41c"
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
