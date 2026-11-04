# product.getCatePropertyV2

> 1、调用【/product/addV2】创建商品和【/product/editV2】更新商品时，请求参数【product_format_new】字段需传入。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.getCatePropertyV2` |
| 中文名 | 调用【/product/addV2】创建商品和… |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getCatePropertyV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1373 |
| 更新日期 | `2026-05-22` |

## 接口说明

- 文档书: 商品API（版本 V8.08）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | number | 是 | 叶子类目id 1、传category_leaf_id ，则不需要传first_cid、second_cid、third_cid这三个字段 2、如果没传category_leaf_id，走之前的逻辑，需要传first_cid、second_cid、third_cid这三个字段 | `1342353245` |
| `product_format_new` | body | string | 否 | 1 | `1` |
| `  └ value` | body | number | 否 | 1 | `1` |
| `  └ measure_info` | body | object | 否 | 度量衡信息 | `` |
| `    └ template_id` | body | number | 否 | 度量衡模板id | `1` |
| `    └ extra` | body | string | 否 | 自定义度量衡扩展信息 | `1` |
| `    └ values` | body | array | 否 | 度量衡内容 | `` |
| `      └ extra` | body | string | 否 | 度量衡扩展信息 | `1` |
| `      └ unit_name` | body | string | 否 | 度量衡单位名称 | `1` |
| `      └ value` | body | string | 否 | 值内容 | `1` |
| `      └ prefix` | body | string | 否 | 前缀 | `1` |
| `      └ suffix` | body | string | 否 | 后缀 | `1` |
| `      └ prefix_id` | body | number | 否 | 前缀id | `1` |
| `      └ unit_id` | body | number | 否 | 度量衡单位id | `1` |
| `      └ suffix_id` | body | number | 否 | 后缀id | `1` |
| `      └ module_id` | body | number | 否 | 模块id | `1` |
| `      └ value_required` | body | boolean | 否 | 是否必填 | `1` |
| `      └ value_id` | body | number | 否 | 值id | `1` |
| `  └ name` | body | string | 否 | 1 | `1` |
| `  └ diy_type` | body | number | 否 | 是否为商家自定义属性值，1为是，0为不是 | `1` |
| `need_process_prop_cascade` | body | boolean | 否 | 1 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回参数列表 | `` |
| `tpl_type` | number | 模板类型，SPU为1，结构化为2，默认为0（无特殊需求忽略该字段即可） | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 当前类目不存在，请重新选择类目（sub_code: isv.parameter-invalid:2010003） | 类目已经不存在，业务预期内，不透出属于正常case |
| `40004` | 非法的参数 / 此类目已调整升级，请重新选择类目进行商品发布（sub_code: isv.parameter-invalid:2010044） | 切换类目 |
| `50002` | 业务处理失败 / 获取类目配置失败（sub_code: isv.business-failed:2010202） | 重试 |
| `50002` | 业务处理失败 / 获取可选品牌失败（sub_code: isv.business-failed:2010013） | 重新调用接口获取 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:2010001） | 请重试 |
| `50002` | 业务处理失败 / 2010004:未指定类目ID（sub_code: isv.business-failed:2010004） | 2010004:未指定类目ID |
| `50002` | 业务处理失败 / 110210112:商品类目不符合平台规则，请重新选择商品类目（sub_code: isv.business-failed:110210112） | 请重新选择 |

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
  "sub_code": "isv.parameter-invalid:2010003",
  "sub_msg": "当前类目不存在，请重新选择类目"
}
```

## 备注
