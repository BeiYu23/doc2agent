# second.product.batchSaveSkuAttribute

> 【二方接口】保存SKU扩展属性

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.product.batchSaveSkuAttribute` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/batchSaveSkuAttribute` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6951 |
| 更新日期 | `2024-10-18` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 商业化账号组uid，用作鉴权 | `15495388485` |
| `items` | body | array | 否 | 参数 | `` |
| `  └ productId` | body | mixed | 否 | 商品ID | `100001` |
| `  └ skuIds` | body | array | 否 | SKU ID | `200001` |
| `  └ shopId` | body | mixed | 否 | 店铺ID（店铺必须属于uid） | `565645` |
| `key` | body | string | 否 | 扩展属性key | `key` |
| `value` | body | string | 否 | 扩展属性value | `value` |
| `option` | body | mixed | 否 | 0-覆盖更新，1-已存在该key的，返回错误 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.batchSaveSkuAttribute&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 商品信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / uid不能为空（sub_code: isp.service-error:300001） | uid不能为空 |
| `20000` | 系统错误 / items不能为空（sub_code: isp.service-error:300002） | items不能为空 |
| `20000` | 系统错误 / key不能为空（sub_code: isp.service-error:300003） | key不能为空 |
| `20000` | 系统错误 / value不能为空（sub_code: isp.service-error:300004） | value不能为空 |
| `20000` | 系统错误 / 只能更改同一店铺的商品SKU属性（sub_code: isp.service-error:300005） | 只能更改同一店铺的商品SKU属性 |
| `20000` | 系统错误 / skuIds不能为空（sub_code: isp.service-error:300006） | skuIds不能为空 |
| `20000` | 系统错误 / productId不能为空（sub_code: isp.service-error:300007） | productId不能为空 |
| `20000` | 系统错误 / shopId不能为空（sub_code: isp.service-error:300008） | shopId不能为空 |
| `20000` | 系统错误 / 店铺鉴权失败（sub_code: isp.service-error:500004） | 店铺鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "items": [
      {
        "code": "0",
        "msg": "msg",
        "productId": "100001",
        "shopId": "56767",
        "skuId": "200001"
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
