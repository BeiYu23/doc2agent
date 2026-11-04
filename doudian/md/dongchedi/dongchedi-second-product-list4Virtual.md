# second.product.list4Virtual

> 【二方接口】获取商品列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.product.list4Virtual` |
| 中文名 | 【二方接口】获取商品列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/list4Virtual` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/7015 |
| 更新日期 | `2024-10-21` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 商业化账号组uid，用作鉴权 | `15495388485` |
| `productId` | body | array | 否 | 小店商品id | `[]` |
| `name` | body | string | 否 | 小店商品名称 | `dde7ab64` |
| `status` | body | mixed | 否 | 小店商品状态，0-上架中，1-下架中，2-删除中 | `8439796` |
| `checkStatus` | body | mixed | 否 | 小店商品审核状态，1-待提交，2-审核中，3-审核通过，4-审核被驳回，5-被封禁 | `5946554` |
| `shopId` | body | mixed | 否 | fields:ShopId  小店店铺id | `690582` |
| `brandId` | body | mixed | 否 | fields:BrandId, 品牌关联id | `521150` |
| `isOnline` | body | mixed | 否 | 在线商品筛选 | `5096401` |
| `isOffline` | body | mixed | 否 | 下架中 | `5462059` |
| `categoryIds` | body | array | 否 | 新类目id列表 | `[]` |
| `tagCode` | body | array | 否 | 标签code，精确匹配 | `[]` |
| `excludeTagCode` | body | array | 否 | 排除标签code，精确匹配 | `[]` |
| `sortField` | body | string | 否 | 排序字段，默认按创建时间 | `deb3322b` |
| `sortDirection` | body | string | 否 | 排序顺序，asc-升序，desc-降序，默认desc | `a6d727e1` |
| `page` | body | mixed | 否 | page | `6264706` |
| `size` | body | mixed | 否 | size | `6754427` |
| `fields` | body | array | 否 | 指定需要获取的字段，字段名从ListInfo4Virtual中取 | `[]` |
| `scrollId` | body | string | 否 | scroll_id | `14d4adeb` |
| `isPackageProduct` | body | boolean | 否 | fields:IsPackageProduct. 是否是组套商品 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.list4Virtual&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | data | `[]` |
| `total` | mixed | total | `3122445` |
| `page` | mixed | page | `6264706` |
| `size` | mixed | size | `6754427` |
| `scrollId` | string | scroll_id | `14d4adeb` |
| `cursorId` | string | 游标id，如果需要遍历则下次查询带上 | `a6595738` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / uid不能为空（sub_code: isp.service-error:300001） | uid不能为空 |
| `20000` | 系统错误 / shopId不能为空（sub_code: isp.service-error:300002） | shopId不能为空 |
| `20000` | 系统错误 / 店铺鉴权失败（sub_code: isp.service-error:500004） | 店铺鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "cursorId": "a6595738",
    "data": [
      {
        "categoryDetail": {
          "enable": "false",
          "firstCid": "1375707",
          "firstCname": "7ac3063b",
          "fourthCid": "9914671",
          "fourthCname": "3c4caaf3",
          "is_leaf": "false",
          "secondCid": "2935859",
          "secondCname": "9cdbc5c8",
          "thirdCid": "1110923",
          "thirdCname": "db0265c9"
        },
        "categoryId": "6710316",
        "checkStatus": "2157014",
        "discountPrice": "6314216",
        "draftStatus": "1731286",
        "firstCid": "1395781",
        "firstCidName": "7c23adc2",
        "img": "db52d060",
        "marketPrice": "5126398",
        "name": "[]",
        "outerProductId": "eebd9cc8",
        "productId": "2253082",
        "secondCid": "5995184",
        "secondCidName": "3aea3310",
        "shopId": "690582",
        "specPrices": [
          {
            "id": "2679991"
          }
        ],
        "status": "5551946",
        "tags": [
          {
            "tagCode": "a8efe3ca",
            "tagName": "6694f4e9",
            "tagSource": "5c0ff8f9",
            "values": "[]"
          }
        ],
        "thirdCid": "4286276",
        "thirdCidName": "31a72c84"
      }
    ],
    "page": "6264706",
    "scrollId": "14d4adeb",
    "size": "6754427",
    "total": "3122445"
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
