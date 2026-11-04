# spu.getSpuRule

> 获取SPU发布规则和模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.spu.getSpuRule` |
| 中文名 | 获取SPU发布规则和模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/spu/getSpuRule` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2312 |
| 更新日期 | `2026-08-13` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 是 | 类目ID | `23362` |
| `channel` | body | mixed | 否 | 类目2.0渠道字段。 0为获取门捷列夫类目下的规则。1为获取标准类目的规则。注意类目ID号段要与channel匹配，否则会报错。如23362为门捷列夫类目ID，channl需要为0. 系统会根据category_id自身字段判断是门捷还是标准类目，但是channel优先级更高 | `0或1` |
| `brand_id` | body | mixed | 否 | 品牌ID | `1078152838` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/spu/getSpuRule?app_key=your_appkey_here&method=spu.getSpuRule&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `spu_property_rule` | array | SPU属性规则 | `` |
| `spu_images_rule` | object | SPU图片规则(已废弃，请采用spu_material_rules字段) | `` |
| `spu_actual_images_rule` | object | SPU实物图规则（已废弃，请采用spu_proof_rules字段） | `` |
| `control_type` | mixed | 0-不管控，商家在该类目下发布商品时，不强制要求命中SPU。 - 1-弱管控，商家在该类目下发布商品时，强制要求命中SPU（即关键属性必须一致），但绑定属性不强制要求一致。 - 2-强管控，商家在该类目下发布商品时，强制要求命中SPU，且绑定属性必须一致。 | `2` |
| `support_spu_product` | boolean | - true 表示商家在该类目基于SPU发布商品，发商品的管控策略见管控类型。 - false 表示商家在该类目不需要基于SPU发布商品。不用发布SPU，直接发布商品即可。 | `true` |
| `support_create_spu` | boolean | true-可以发布SPU，false-不能发布SPU | `true` |
| `spu_material_rules` | array | SPU素材规则（素材类型：主图） | `` |
| `spu_proof_rules` | array | 证明材料规则（证明材料类型：实物图、版权页） | `` |
| `spu_barcode_rule` | object | 条码规则 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 读取失败（sub_code: isv.business-failed:2012013） | 检查参数入参 |
| `80000` | 风控拦截 / 操作人非法（sub_code: isv.risk-control-failed:20121002） | 查看操作人信息 |
| `50002` | 业务处理失败 / 商家不存在（sub_code: isv.business-failed:20121103） | 查看操作人信息 |
| `50002` | 业务处理失败 / 商家不存在（sub_code: isv.business-failed:2012004） | 查看操作人信息 |

## 响应示例

成功：

```json
{
  "data": {
    "control_type": "2",
    "spu_actual_images_rule": {
      "is_required": "1",
      "max_num": "5",
      "min_num": "1"
    },
    "spu_barcode_rule": {
      "barcode_image_rule": {
        "data_format": "[\"png\",\"jpg\",\"jpeg\"]",
        "is_required": "1",
        "max_num": "5",
        "min_num": "1"
      },
      "barcode_rule": {
        "is_required": "1",
        "max_num": "1",
        "min_num": "1"
      }
    },
    "spu_images_rule": {
      "is_required": "1",
      "max_num": "5",
      "min_num": "1"
    },
    "spu_material_rules": [
      {
        "material_rule": {
          "aspect_ratio": "[\"1\",\"1\"]",
          "data_format": "[\"png\",\"jpg\",\"jpeg\"]",
          "is_required": "0",
          "max_num": "5",
          "max_size": "5",
          "min_num": "0",
          "name": "主图",
          "pixel": "[600,600]"
        },
        "material_type": "1"
      }
    ],
    "spu_proof_rules": [
      {
        "proof_rule": {
          "aspect_ratio": "[\"1\",\"1\"]",
          "data_format": "[\"png\",\"jpg\",\"jpeg\"]",
          "is_required": "1",
          "max_num": "5",
          "max_size": "5",
          "min_num": "1",
          "name": "版权页",
          "pixel": "[600,600]"
        },
        "proof_type": "6"
      }
    ],
    "spu_property_rule": [
      {
        "diy_type": "0",
        "is_required": "1",
        "max_select_num": "0",
        "property_id": "1831",
        "property_name": "书名",
        "property_type": "0",
        "value_type": "select",
        "values": [
          {
            "value_id": "0",
            "value_name": "小王子"
          }
        ]
      }
    ],
    "support_create_spu": "true",
    "support_spu_product": "true"
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
  "sub_code": "isv.business-failed:2012013",
  "sub_msg": "读取失败"
}
```

## 备注
