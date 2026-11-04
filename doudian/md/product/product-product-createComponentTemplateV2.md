# product.createComponentTemplateV2

> 创建尺码模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.createComponentTemplateV2` |
| 中文名 | 创建尺码模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/createComponentTemplateV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1992 |
| 更新日期 | `2022-06-11` |

## 接口说明

- 文档书: 商品API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_type` | body | string | 是 | 模板类型：尺码模板 | `size_info` |
| `template_sub_type` | body | string | 是 | 模板子类型: clothing(服装)、undies(内衣)、shoes(鞋靴类)、children_clothing(童装) | `clothing` |
| `template_name` | body | string | 是 | 模板名称 | `模板名称1` |
| `component_front_data` | body | string | 是 | 商品组件数据 json，表格行列顺序以selectedSize和selectedSpecs的顺序为准 | `{"title":"测试模板3","desc":"测试","tempName":"测试模板3副本1副本1","configTable":[{"size":"XS","specMap":{"身高（cm）":"1","体重（斤）":"2","胸围（cm）":"3"}},{"size":"M","specMap":{"身高（cm）":"10","体重（斤）":"10","胸围（cm）":"10"}}],"selectedSpecs":["身高（cm）","体重（斤）","胸围（cm）"],"specOptions":["身高（cm）","体重（斤）","胸围（cm）"],"selectedSize":["XS","M"]}` |
| `shareable` | body | boolean | 否 | 是否设置为公有模板(多个商品可共用)。true-是，false-不是；不传默认fasle | `true` |
| `category_id` | body | number | 否 | 类目id，用来确定模板类型 | `214691` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/createComponentTemplateV2?app_key=your_appkey_here&method=product.createComponentTemplateV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_id` | number | 模板ID | `101` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "template_id": "101"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
