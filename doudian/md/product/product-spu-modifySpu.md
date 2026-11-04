# 修改spu信息

> spu.modifySpu — 修改spu信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 修改spu信息 |
| 文档地址 | `/docs/doudian/product/product-spu-modifySpu` |
| 接口 ID | `doudian.product.spu.modifySpu` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/spu/modifySpu` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8481 |
| 更新日期 | `2026-08-20` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `spu_id` | body | mixed | 是 | 要修改的 SPU ID | `7670734202869924140` |
| `property_infos` | body | array | 否 | 全量属性；传入且非空则覆盖，不传/传空列表则沿用原SPU属性（不会清空） | `` |
| `  └ property_id` | body | mixed | 否 | 属性项id | `1618` |
| `  └ property_name` | body | string | 否 | 属性项名称 | `ISBN编号` |
| `  └ values` | body | array | 否 | 属性值信息 | `` |
| `    └ channel` | body | mixed | 否 | 0：门捷列夫，1：标准类目2.0 | `1` |
| `    └ value_id` | body | mixed | 否 | 属性值ID，如果可输入类型valueId传0 | `0` |
| `    └ value_name` | body | string | 否 | 属性值名称 | `小王子` |
| `materials` | body | array | 否 | 素材（type=Image时回填主图）；传入且非空则覆盖原主图，不传/传空列表则沿用原主图（不会清空） | `` |
| `  └ name` | body | string | 否 | 素材类型名称 | `主图` |
| `  └ type` | body | mixed | 否 | 素材类型，枚举值：1-主图 | `1` |
| `  └ description` | body | string | 否 | 描述信息 | `该主图用于xxx` |
| `  └ content` | body | array | 否 | 素材内容 | `` |
| `    └ content` | body | string | 否 | 内容 | `https://p3-ecom-spu.byteimg.com/tos-cn-i-89jsre2ap7/dc491713470d4d6c8e49733f20283e18~tplv-89jsre2ap7-image.image` |
| `    └ name` | body | string | 否 | 文件名 | `主图1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/spu/modifySpu?app_key=your_appkey_here&method=spu.modifySpu&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `spu_id` | mixed | 若修改了关键属性，则返回的是新spuid,否则就是老spuid | `7120712486076088620` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / spuId非法（sub_code: isv.parameter-invalid:1003042） | 检查入参的spuID是否合法 |
| `40004` | 非法的参数 / 无权限调用ModifySpu4Open（sub_code: isv.parameter-invalid:1003047） | 无权限修改spu信息 |
| `50002` | 业务处理失败 / 查询原SPU失败（sub_code: isv.business-failed:1006249） | 重试 |
| `40004` | 非法的参数 / SPU不存在（sub_code: isv.parameter-invalid:1003044） | 检查操作的spu是否确实存在 |
| `50002` | 业务处理失败 / 构建类目渠道上下文失败（sub_code: isv.business-failed:1003045） | 重试 |
| `60000` | 触发限流，请稍后重试 / 触发限流,请稍后再试（sub_code: isp.traffic-limited:1000027） | 稍后重试 |
| `50002` | 业务处理失败 / 获取商家信息失败（sub_code: isv.business-failed:1000025） | 重试 |
| `40004` | 非法的参数 / 商家不存在（sub_code: isv.parameter-invalid:1003043） | 检查商家是否确实存在 |
| `40004` | 非法的参数 / 请求参数转换失败（sub_code: isv.parameter-invalid:1003046） | 检查请求入参 |
| `50002` | 业务处理失败 / 获取店铺标签失败（sub_code: isv.business-failed:1000030） | 重试 |
| `50002` | 业务处理失败 / 品牌id不一致（sub_code: isv.business-failed:20121014） | 检查品牌id |
| `50002` | 业务处理失败 / 属性项有空属性值（sub_code: isv.business-failed:20121013） | 检查是否存在空属性值 |
| `50002` | 业务处理失败 / SPU状态不合法（sub_code: isv.business-failed:2012004） | 检查操作的spu是否为上线状态 |
| `50002` | 业务处理失败 / 不允许关键属性为空（sub_code: isv.business-failed:20121009） | 检查关键属性值是否为空 |
| `50002` | 业务处理失败 / 新增关键属性或级联失败（sub_code: isv.business-failed:2012001） | 重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1003042",
  "sub_msg": "spuId非法"
}
```

## 备注
