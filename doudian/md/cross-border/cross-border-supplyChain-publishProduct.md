# supplyChain.publishProduct

> 发布货品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.supplyChain.publishProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/publishProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6325 |
| 更新日期 | `2024-05-16` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bmp_code` | body | string | 是 | 行业身份（跨境pop：xiaodian.crossborder） | `xiaodian.crossborder` |
| `supplier_id` | body | mixed | 否 | 供应商id | `11111` |
| `cargo_category_id` | body | mixed | 否 | 叶子类目id | `111` |
| `item_type` | body | mixed | 是 | 货品类型 1:普通货品 2:配件 6:包材 7:耗材 | `1` |
| `product_name` | body | string | 是 | 货品名称 | `测试` |
| `product_desc` | body | string | 是 | 货品描述 | `测试` |
| `category_props` | body | array | 是 | 类目属性列表 | `` |
| `  └ prop_key` | body | object | 是 | 属性识别数据（传入属性接口用于确认是哪个属性，与获取属性接口的prop_key保持一致） | `` |
| `    └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `    └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `    └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `  └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `  └ prop_val` | body | object | 否 | 属性值信息（不是多选时使用这一字段） | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ prop_val_list` | body | array | 否 | 多选下，属性值信息（多选时使用这一字段） | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `is_need_batch` | body | mixed | 是 | 是否批次管理 1:是 0:否 （跨境pop须填“是”） | `1` |
| `batch_props` | body | array | 是 | 批次管理属性列表（需要批次管理时填写；跨境pop须将“生产批号采集”、“入库业务单号”、“入库日期”、“采集生产日期”、“采集失效日期”填写“是”） | `` |
| `  └ prop_key` | body | object | 是 | 属性识别数据（传入属性接口用于确认是哪个属性，与获取属性接口的prop_key保持一致） | `` |
| `    └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `    └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `    └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `  └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `  └ prop_val` | body | object | 否 | 属性值（不是多选时使用这一字段） | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ prop_val_list` | body | array | 否 | 多选下，属性值信息（多选时使用这一字段） | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `is_need_valid` | body | mixed | 是 | 是否需要效期管理 1:是 0:否 | `1` |
| `period_props` | body | array | 是 | 效期属性列表（需要效期管理时填写） | `` |
| `  └ prop_key` | body | object | 是 | 属性识别数据（传入属性接口用于确认是哪个属性，与获取属性接口的prop_key保持一致） | `` |
| `    └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `    └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `    └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `  └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `  └ prop_val` | body | object | 否 | 属性值信息（不是多选时使用这一字段） | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ prop_val_list` | body | array | 否 | 多选下，属性值信息（多选时使用这一字段） | `` |
| `    └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `    └ prop_value` | body | string | 是 | 属性值 | `是` |
| `skus` | body | array | 是 | 货品下的sku | `` |
| `  └ sku_props` | body | array | 是 | sku属性列表 | `` |
| `    └ prop_key` | body | object | 是 | 属性识别数据（传入属性接口用于确认是哪个属性，与获取属性接口的prop_key保持一致） | `` |
| `      └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `      └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `      └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `    └ prop_val` | body | object | 是 | 属性值信息 | `` |
| `      └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `      └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ sku_category_props` | body | array | 是 | sku级类目属性列表 | `` |
| `    └ prop_key` | body | object | 是 | 属性识别数据（传入属性接口用于确认是哪个属性，与获取属性接口的prop_key保持一致） | `` |
| `      └ prop_key_id` | body | mixed | 是 | 属性id | `111` |
| `      └ prop_key` | body | string | 是 | 属性名称 | `品牌` |
| `      └ prop_code` | body | string | 是 | 属性编码 | `brand` |
| `    └ is_multi` | body | boolean | 是 | 是否多选 | `false` |
| `    └ prop_val` | body | object | 否 | 属性值（不是多选时使用这一字段） | `` |
| `      └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `      └ prop_value` | body | string | 是 | 属性值 | `是` |
| `    └ prop_val_list` | body | array | 否 | 多选下，属性值信息（多选时使用这一字段） | `` |
| `      └ prop_value_id` | body | mixed | 否 | 属性值id | `111` |
| `      └ prop_value` | body | string | 是 | 属性值 | `是` |
| `  └ image` | body | string | 否 | sku维度的图片（应传入使用上传接口获取的URL） | `https://example.com/xxx.jpg` |
| `is_suite` | body | mixed | 否 | 是否组套 1:是 0:否 | `0` |
| `extend_feature01` | body | string | 否 | 扩展字段1 | `111` |
| `extend_feature02` | body | string | 否 | 扩展字段2 | `222` |
| `business_model` | body | string | 是 | 经营模式（跨境pop：/） | `/` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/publishProduct?app_key=your_appkey_here&method=supplyChain.publishProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:400001） | 请检查传入的参数 |
| `40004` | 非法的参数 / 该条码已存在（sub_code: isv.parameter-invalid:3001） | 请检查条码属性是否与已有货品发生重复 |
| `20000` | 系统错误 / 内部服务返回错误（sub_code: isp.service-error:200001） | 请检查传入的参数并稍后重试 |
| `40002` | 缺少必选参数 / 缺少行业参数（sub_code: isv.missing-parameter:400002） | 请检查传入的 BmpCode 参数并重试 |
| `40004` | 非法的参数 / 行业身份不支持（sub_code: isv.parameter-invalid:400003） | 请检查传入的 BmpCode 参数并重试 |
| `40002` | 缺少必选参数 / 缺少业务类型（sub_code: isv.missing-parameter:400004） | 请检查传入的 BusinessModel |
| `40004` | 非法的参数 / 业务类型不支持（sub_code: isv.parameter-invalid:400005） | 请检查传入的 BusinessModel |
| `20000` | 系统错误 / 效期属性计算失败（sub_code: isp.service-error:200013） | 请稍后重试 |
| `20000` | 系统错误 / 调用发品内部逻辑失败（sub_code: isp.service-error:200014） | 请稍后重试 |
| `50002` | 业务处理失败 / 3201:Redis加锁异常（sub_code: isv.business-failed:3201） | 请稍后重试 |
| `50002` | 业务处理失败 / 1000:服务异常（sub_code: isv.business-failed:1000） | 请稍后重试 |
| `50002` | 业务处理失败 / 3202:Redis加锁失败（sub_code: isv.business-failed:3202） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "results": [
        {
          "cargo_code": "11111",
          "external_cargo_code": "11111"
        }
      ]
    }
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
  "sub_code": "isv.parameter-invalid:400001",
  "sub_msg": "非法的参数"
}
```

## 备注
