# 发布SPU

> spu.createSpu — 发布SPU

| 元信息 | 值 |
| --- | --- |
| 中文名 | 发布SPU |
| 文档地址 | `/docs/doudian/product/product-spu-createSpu` |
| 接口 ID | `doudian.product.spu.createSpu` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/spu/createSpu` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2311 |
| 更新日期 | `2026-08-13` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | mixed | 是 | 叶子类目ID | `23362` |
| `spu_images` | body | array | 否 | SPU图片（已废弃，请采用materials字段） | `["https://p-boe.byted.org/tos-boe-i-c1s52z2b8k/47aae92445314984b27c3854ce2ec569~tplv-c1s52z2b8k-image.image"]` |
| `property_infos` | body | array | 是 | 属性信息（/spu/getSpuRule接口可获取） | `` |
| `  └ values` | body | array | 是 | 属性值 | `` |
| `    └ value_id` | body | mixed | 是 | 属性值ID | `0` |
| `    └ value_name` | body | string | 是 | 属性值 | `小王子` |
| `  └ property_id` | body | mixed | 是 | 属性ID | `1618` |
| `spu_actual_images` | body | array | 否 | SPU实物图（已废弃，请采用proofs字段） | `["https://p-boe.byted.org/tos-boe-i-c1s52z2b8k/47aae92445314984b27c3854ce2ec569~tplv-c1s52z2b8k-image.image"]` |
| `materials` | body | array | 否 | SPU素材 | `` |
| `  └ type` | body | mixed | 是 | 素材类型，枚举值：1-主图 | `1` |
| `  └ name` | body | string | 是 | 素材类型名称 | `主图` |
| `  └ content` | body | array | 是 | 素材的实际内容 | `` |
| `    └ content` | body | string | 是 | 素材内容（/spu/batchUploadImg返回的URL） | `https://p3-ecom-spu.byteimg.com/tos-cn-i-89jsre2ap7/dc491713470d4d6c8e49733f20283e18~tplv-89jsre2ap7-image.image` |
| `    └ name` | body | string | 是 | 文件的名称 | `主图1` |
| `  └ description` | body | string | 是 | 描述信息 | `该主图用于xxx` |
| `proofs` | body | array | 否 | 证明信息 | `` |
| `  └ type` | body | mixed | 是 | 证明信息（类型：实物图、版权页） | `2` |
| `  └ name` | body | string | 是 | 证明信息类型，枚举值：2-实物图、6-版权页 | `实物图` |
| `  └ description` | body | string | 是 | 描述信息 | `该实物图用于xxx` |
| `  └ content` | body | array | 是 | 证明材料的实际内容 | `` |
| `    └ name` | body | string | 是 | 文件的名称 | `实物图1` |
| `    └ content` | body | string | 是 | 证明信息内容（/spu/batchUploadImg返回的URL） | `https://p3-ecom-spu.byteimg.com/tos-cn-i-89jsre2ap7/dc491713470d4d6c8e49733f20283e18~tplv-89jsre2ap7-image.image` |
| `barcodes` | body | array | 否 | 条码 | `` |
| `  └ barcode_type` | body | mixed | 否 | 条码类型，1-69码 | `1` |
| `  └ barcode_image` | body | array | 否 | 条码图 | `` |
| `    └ content` | body | string | 否 | 条码图链接 | `https://lf3-cm.ecombdstatic.com/obj/ecom-ecop/168223854898b464cf2268f14ec6ae01ce05d0745ad3914371.jpeg` |
| `    └ name` | body | string | 否 | 条码图名称 | `条码图名称` |
| `  └ barcode` | body | string | 否 | 条码值 | `6900388851185` |
| `channel` | body | mixed | 否 | 类目渠道，0:门捷列夫类目；1:标准类目 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/spu/createSpu?app_key=your_appkey_here&method=spu.createSpu&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `spu_id` | string | SPU的ID | `7120712486076088620` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 图片格式错误（sub_code: isv.business-failed:20121017） | 检查图片链接是否满足要求 |
| `20000` | 系统错误（sub_code: isp.service-error:2012001） | 重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2012004） | 检查请求参数 |
| `50002` | 业务处理失败 / 证明信息参数错误（sub_code: isv.business-failed:20121020） | 检查请求参数中的证明信息 |
| `50002` | 业务处理失败 / 属性信息有误（sub_code: isv.business-failed:20121009） | 检查请求参数中的属性信息 |
| `50002` | 业务处理失败 / 数据加载异常（sub_code: isv.business-failed:2012013） | 重试 |
| `50002` | 业务处理失败 / 触发限流,请稍后再试（sub_code: isv.business-failed:20121015） | 稍后重试 |
| `50002` | 业务处理失败 / 读取数据失败（sub_code: isv.business-failed:20121013） | 重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:20121010） | 业务处理失败 |

## 响应示例

成功：

```json
{
  "data": {
    "spu_id": "7120712486076088620"
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
  "sub_code": "isv.business-failed:20121017",
  "sub_msg": "图片格式错误"
}
```

## 备注
