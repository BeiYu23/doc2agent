# spu.getSpu

> 查询SPU（根据关键属性/SPU ID）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.spu.getSpu` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/spu/getSpu` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2309 |
| 更新日期 | `2026-08-14` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | mixed | 否 | 叶子类目ID | `23362` |
| `key_properties` | body | array | 否 | 关键属性 | `` |
| `  └ property_values` | body | array | 否 | 属性值 | `` |
| `    └ value_name` | body | string | 否 | 属性值 | `测试` |
| `    └ value_id` | body | mixed | 否 | 属性值ID | `0` |
| `  └ property_id` | body | mixed | 否 | 属性ID | `1618` |
| `spu_id` | body | mixed | 否 | SPU ID（传SPUID时，关键属性不用传，传关键属性时，SPU ID不用传，两个都传的情况下，会以SPU ID为准，查询SPU） | `7120712486076088620` |
| `channel` | body | mixed | 否 | 0：门捷列夫，1：标准类目2.0 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/spu/getSpu?app_key=your_appkey_here&method=spu.getSpu&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `spu_id` | mixed | SPU ID | `7120712486076088620` |
| `spu_name` | string | SPU名 | `小王子/981013` |
| `category_leaf_id` | mixed | 类目ID | `23362` |
| `property_infos` | array | 属性信息 | `` |
| `cspus` | array | CSPU信息 | `` |
| `status` | mixed | 1:上线，2:下线，3:审核中，4:审核不通过 | `状态` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2012004:没有当前类目资质（sub_code: isv.business-failed:2012004） | 2012004:没有当前类目资质 |
| `50002` | 业务处理失败 / 2012001:查询spu失败（sub_code: isv.business-failed:2012001） | 2012001:查询spu失败 |
| `50002` | 业务处理失败 / 20121016:类目参数错误（sub_code: isv.business-failed:20121016） | 检查入参 |
| `50002` | 业务处理失败 / 2012013:查询类目属性时发生错误（sub_code: isv.business-failed:2012013） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "category_leaf_id": "23362",
    "cspus": [
      {
        "cspu_id": "7120712207235555563",
        "sale_properties": [
          {
            "property_id": "1998",
            "property_name": "颜色",
            "value_id": "0",
            "value_name": "红色"
          }
        ],
        "spu_id": "7120712486076088620"
      }
    ],
    "property_infos": [
      {
        "property_id": "1618",
        "property_name": "书名",
        "property_type": "1",
        "property_values": [
          {
            "value_id": "0",
            "value_name": "小王子"
          }
        ]
      }
    ],
    "spu_id": "7120712486076088620",
    "spu_name": "小王子/981013",
    "status": "状态"
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
  "sub_code": "isv.business-failed:2012004",
  "sub_msg": "2012004:没有当前类目资质"
}
```

## 备注
