# supplyChain.editProduct

> 编辑货品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.supplyChain.editProduct` |
| 中文名 | 编辑货品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/editProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6327 |
| 更新日期 | `2024-03-26` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cargo_category_id` | body | mixed | 否 | 货品类目id | `1111111` |
| `product_name` | body | string | 否 | 货品名称 | `测试货品` |
| `product_desc` | body | string | 否 | 货品描述 | `测试货品描述` |
| `category_props` | body | array | 否 | 类目属性列表 | `` |
| `  └ prop_key` | body | object | 是 | 属性识别数据 | `` |
| `    └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `    └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `    └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `  └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `  └ prop_val` | body | object | 否 | 属性值信息 | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ prop_val_list` | body | array | 否 | 多选下，属性值信息 | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `is_need_batch` | body | mixed | 是 | 是否批次管理 1:是 0:否 | `1` |
| `batch_props` | body | array | 是 | 批次属性列表 | `` |
| `  └ prop_key` | body | object | 是 | 属性识别数据 | `` |
| `    └ prop_key_id` | body | mixed | 是 | 属性key | `111` |
| `    └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `    └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `  └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `  └ prop_val` | body | object | 否 | 属性值信息 | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ prop_val_list` | body | array | 否 | 多选下，属性值信息 | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `is_need_valid` | body | mixed | 是 | 是否效期管理 1:是 2:否 | `0` |
| `period_props` | body | array | 否 | 效期属性列表 | `` |
| `  └ prop_key` | body | object | 是 | 属性识别数据 | `` |
| `    └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `    └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `    └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `  └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `  └ prop_val` | body | object | 否 | 属性值信息 | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ prop_val_list` | body | array | 否 | 多选下，属性值信息 | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `skus` | body | array | 否 | sku信息 | `` |
| `  └ sku_props` | body | array | 是 | sku属性 | `` |
| `    └ prop_key` | body | object | 是 | 属性识别数据 | `` |
| `      └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `      └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `      └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `    └ prop_val` | body | object | 是 | 属性值信息 | `` |
| `      └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `      └ prop_value` | body | string | 是 | 属性值名称 | `是` |
| `  └ sku_category_props` | body | array | 是 | sku类目级属性列表 | `` |
| `    └ prop_key` | body | object | 是 | 属性识别信息 | `` |
| `      └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `      └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `      └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `    └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `    └ prop_val` | body | object | 否 | 属性值信息 | `` |
| `      └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `      └ prop_value` | body | string | 是 | 属性值 | `是` |
| `    └ prop_val_list` | body | array | 否 | 多选下，属性值信息 | `` |
| `      └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `      └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ image` | body | string | 否 | sku维度的图片（应传入使用上传接口获取的URL） | `https://example.com/xxx.jpg` |
| `  └ cargo_code` | body | string | 是 | sku维度货品编码 | `11111` |
| `is_suite` | body | mixed | 否 | 是否组套 1:是 0:否 | `0` |
| `extend_feature01` | body | string | 否 | 扩展参数1 | `1111` |
| `extend_feature02` | body | string | 否 | 扩展参数2 | `2222` |
| `edit_attachment` | body | object | 否 | 修改原因及证明材料（若类目或效期属性被修改，必填） | `` |
| `  └ change_reason` | body | string | 是 | 修改原因 | `修改原因` |
| `  └ file_pic_url_list` | body | array | 是 | 效期变更证明材料（需例如实物效期图片、厂家证明等能证明效期变动的图片材料即可） | `["https://example.com/xxx.jpg"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/editProduct?app_key=your_appkey_here&method=supplyChain.editProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:400001） | 请检查传入的参数 |
| `40004` | 非法的参数 / 该条码已存在（sub_code: isv.parameter-invalid:3001） | 请检查条码属性是否与已有货品发生重复 |
| `40004` | 非法的参数 / 货品不存在（sub_code: isv.parameter-invalid:3000） | 请检查输入的货品编码是否正确 |
| `20000` | 系统错误 / 内部服务返回错误（sub_code: isp.service-error:200001） | 请检查传入的参数并稍后重试 |
| `20000` | 系统错误 / 效期属性计算失败（sub_code: isp.service-error:200013） | 请稍后重试 |
| `20000` | 系统错误 / 调用编辑内部逻辑失败（sub_code: isp.service-error:200015） | 请稍后重试 |
| `50002` | 业务处理失败 / 无权限（sub_code: isv.business-failed:300001） | 编辑的货品编码中含有不存在或不属于当前用户的货品 |

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
  "sub_code": "isv.parameter-invalid:400001",
  "sub_msg": "非法的参数"
}
```

## 备注
