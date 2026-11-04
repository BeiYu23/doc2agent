# product.editComponentTemplate

> 编辑尺码模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.editComponentTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/editComponentTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1993 |
| 更新日期 | `2022-06-11` |

## 接口说明

- 文档书: 商品API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | number | 是 | 模板ID | `101` |
| `template_name` | body | string | 否 | 模板名称 | `模板名称2` |
| `component_data` | body | string | 否 | 模板数据json | `{"title":"服装上衣模板","desc":"dy服装上衣模板","tempName":"dy服装上衣模板","configTable":[{"size":"XS","specMap":{"身高（cm）":"180","体重（斤）":"70","胸围（cm）":"80"}},{"size":"M","specMap":{"身高（cm）":"185","体重（斤）":"80","胸围（cm）":"85"}}],"selectedSpecs":["身高（cm）","体重（斤）","胸围（cm）"],"specOptions":["身高（cm）","体重（斤）","胸围（cm）"],"selectedSize":["xl","xxl"]}` |
| `shareable` | body | boolean | 否 | 是否为公有模板(多个商品可共用) | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/editComponentTemplate?app_key=your_appkey_here&method=product.editComponentTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统处理异常（sub_code: isp.service-error:2010001） | 系统处理异常，咨询研发人员 |
| `40002` | 缺少必选参数 / 参数缺失（sub_code: isv.missing-parameter:2010003） | 根据返回信息提示检查参数 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2010004） | 根据返回信息提示检查参数 |
| `20000` | 系统错误（sub_code: isp.service-error:2010011） | 系统处理异常，咨询研发人员 |
| `20000` | 系统错误（sub_code: isp.service-error:2010012） | 系统处理异常，咨询研发人员 |
| `50002` | 业务处理失败 / 110250103:该类目商品需上传完整尺码表信息，目前缺失规格：身高，请补充！<a href='https://school.jinritemai.YOUR_SECRET_KEY' target='_blank'>规则介绍</a>（sub_code: isv.business-failed:110250103） | 110250103:该类目商品需上传完整尺码表信息，目前缺失规格：身高，请补充！<a href='https://school.jinritemai.YOUR_SECRET_KEY' target='_blank'>规则介绍</a> |
| `50002` | 业务处理失败 / 110250142:尺码信息区间值中最大值需要大于最小值（sub_code: isv.business-failed:110250142） | 110250142:尺码信息区间值中最大值需要大于最小值 |
| `50002` | 业务处理失败 / 110250138:模板列数超过上限（sub_code: isv.business-failed:110250138） | 110250138:模板列数超过上限 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:2010001",
  "sub_msg": "系统处理异常"
}
```

## 备注
