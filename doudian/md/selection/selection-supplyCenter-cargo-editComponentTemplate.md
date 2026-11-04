# supplyCenter.cargo.editComponentTemplate

> 编辑尺码模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.cargo.editComponentTemplate` |
| 中文名 | 编辑尺码模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5319 |
| 更新日期 | `2023-10-25` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | number | 是 | 模板ID | `101` |
| `template_name` | body | string | 否 | 模板名称 | `模板名称1` |
| `component_data` | body | string | 否 | 模板数据json | `{"title":"服装上衣模板","desc":"dy服装上衣模板","tempName":"dy服装上衣模板","configTable":[{"size":"XS","specMap":{"身高（cm）":"180","体重（斤）":"70","胸围（cm）":"80"}},{"size":"M","specMap":{"身高（cm）":"185","体重（斤）":"80","胸围（cm）":"85"}}],"selectedSpecs":["身高（cm）","体重（斤）","胸围（cm）"],"specOptions":["身高（cm）","体重（斤）","胸围（cm）"],"selectedSize":["xl","xxl"]}` |
| `shareable` | body | boolean | 否 | 是否为公有模板(多个商品可共用) | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.cargo.editComponentTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照商品编辑尺寸模板接口（sub_code: isv.parameter-invalid:66666） | https://op.jinritemai.com/docs/api-docs/14/1993 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:66666",
  "sub_msg": "参照商品编辑尺寸模板接口"
}
```

## 备注
