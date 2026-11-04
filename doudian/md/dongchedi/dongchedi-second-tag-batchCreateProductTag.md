# second.tag.batchCreateProductTag

> 【二方接口】商品批量打标

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.tag.batchCreateProductTag` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/tag/batchCreateProductTag` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6943 |
| 更新日期 | `2024-10-15` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 商业化账号组uid，用作鉴权 | `15495388485` |
| `tags` | body | array | 否 | tags | `[]` |
| `  └ shopId` | body | mixed | 否 | shopId | `8878893` |
| `  └ productId` | body | mixed | 否 | productId | `7092693` |
| `  └ reqSource` | body | mixed | 否 | 打标操作来源  TagSource | `9633383` |
| `  └ operator` | body | object | 否 | operator | `` |
| `    └ UserId` | body | string | 否 | UserId | `463da8da` |
| `    └ UserName` | body | string | 否 | UserName | `1df50586` |
| `  └ tagCode` | body | string | 否 | tagCode | `fd9a7204` |
| `  └ tagVal` | body | string | 否 | tagVal | `6a8bf9e4` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/tag/batchCreateProductTag?app_key=your_appkey_here&method=second.tag.batchCreateProductTag&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `failedTags` | array | failedTags | `[]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / uid不能为空（sub_code: isp.service-error:300001） | uid不能为空 |
| `20000` | 系统错误 / tags不能为空（sub_code: isp.service-error:300002） | tags不能为空 |
| `20000` | 系统错误 / 只能更改同一店铺的商品Tag（sub_code: isp.service-error:300003） | 只能更改同一店铺的商品Tag |
| `20000` | 系统错误 / 店铺鉴权失败（sub_code: isp.service-error:500004） | 店铺鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "failedTags": [
      {
        "channel": {
          "channelId": "6991381",
          "channelType": "8637330"
        },
        "failCode": "7492534",
        "productId": "3664132",
        "reason": "6591222",
        "tagCode": "13702964"
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
