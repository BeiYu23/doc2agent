# spu.QuerySpu

> 检索SPU

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.spu.QuerySpu` |
| 中文名 | 检索SPU |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/spu/QuerySpu` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/6206 |
| 更新日期 | `2026-08-14` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 【必填】从第0页开始 | `0` |
| `size` | body | mixed | 是 | 【必填】最大值为20 | `20` |
| `category_id` | body | mixed | 否 | 【选填】叶子类目ID | `31860` |
| `properties` | body | object | 否 | 【选填】属性 | `` |
| `  └ product_name` | body | string | 否 | 【选填】产品名称 | `美容护肤面霜` |
| `  └ ccc` | body | string | 否 | 【选填】CCC证书编号 | `2023011606593938` |
| `  └ isbn` | body | string | 否 | 【选填】ISBN | `9787544847346` |
| `  └ model` | body | string | 否 | 【选填】型号 | `F911` |
| `  └ book_name` | body | string | 否 | 【选填】书名 | `童话世界` |
| `  └ goods_number` | body | string | 否 | 【选填】货号 | `W91216040101` |
| `  └ brand_id` | body | mixed | 否 | 【选填】品牌 | `2078711068` |
| `  └ series` | body | string | 否 | 【选填】系列 | `JAMES 系列` |
| `  └ registration_approval` | body | string | 否 | 【选填】备案/批准文号 | `粤G妆网备字2023292746` |
| `status` | body | array | 否 | 【选填】SPU状态：1-上线，2-下线，3-审核中，4-审核不通过 | `[1,2]` |
| `channel` | body | mixed | 否 | 0：门捷列夫，1：标准类目2.0 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/spu/QuerySpu?app_key=your_appkey_here&method=spu.QuerySpu&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 查询到的总数据量 | `80` |
| `spuList` | array | SPU信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 传入参数错误（sub_code: isv.parameter-invalid:40004） | 请检查传入参数 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:50002） | 请稍后重试 |
| `50002` | 业务处理失败 / 2012004:传入参数异常，该商家无类目[29196]资质（sub_code: isv.business-failed:2012004） | 2012004:传入参数异常，该商家无类目[29196]资质 |
| `50002` | 业务处理失败 / 2012013:获取品牌信息失败（sub_code: isv.business-failed:2012013） | 2012013:获取品牌信息失败 |
| `50002` | 业务处理失败 / 2012001:查询商家类目资质异常（sub_code: isv.business-failed:2012001） | 2012001:查询商家类目资质异常 |

## 响应示例

成功：

```json
{
  "data": {
    "spuList": [
      {
        "barcodes": [
          {
            "barcode": "6973971701655"
          }
        ],
        "brandId": "437716142",
        "categoryId": "23072",
        "materials": [
          {
            "content": [
              {
                "content": "https://p3-ecom-spu.byteimg.com/tos-cn-i-89jsre2ap7/2feb661390654869ab35a2d05fea5472~tplv-89jsre2ap7-image.image"
              }
            ],
            "type": "1"
          }
        ],
        "spuId": "7340298802504761650",
        "spuName": "9787561139684/红点奖:全球最佳视觉传达设计年鉴",
        "spuPropertyInfos": [
          {
            "propertyId": "1479",
            "propertyName": "产品名称",
            "propertyType": "1",
            "propertyValues": [
              {
                "valueId": "0",
                "valueName": "神经酰胺修护霜"
              }
            ]
          }
        ],
        "status": "1"
      }
    ],
    "total": "80"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40004",
  "sub_msg": "传入参数错误"
}
```

## 备注
