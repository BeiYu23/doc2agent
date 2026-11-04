# 即时零售运费模板更新

> instantShopping.trade.freightUpdate — 即时零售运费模板更新接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 即时零售运费模板更新 |
| 文档地址 | `/docs/doudian/retail-logistics/retail-logistics-instantShopping-trade-freightUpdate` |
| 接口 ID | `doudian.retail-logistics.instantShopping.trade.freightUpdate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1530/7424 |
| 更新日期 | `2025-04-24` |

## 接口说明

- 文档书: 物流发货API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template` | body | object | 否 | 运费模板 | `` |
| `  └ template_name` | body | string | 否 | 模板名称 | `模板名称` |
| `  └ calculate_type` | body | mixed | 否 | 解析column中calculate_type字段：计价方式-1.按重量计价 2.按数量计价 | `2` |
| `  └ product_city` | body | mixed | 否 | 发货城市id | `110000` |
| `  └ product_province` | body | mixed | 否 | 发货省份id | `11` |
| `  └ fixed_amount` | body | mixed | 否 | 固定运费金额（单位：分） | `0` |
| `  └ rule_type` | body | mixed | 否 | 计价方式 0:阶梯计价 1:固定运费 2:卖家包邮 6:混合履约模式；固定值传6 | `6` |
| `  └ id` | body | mixed | 否 | 模板id | `11` |
| `  └ transfer_type` | body | mixed | 否 | 固定值1 | `1` |
| `columns` | body | array | 否 | 运费规则 | `` |
| `  └ add_weight_price` | body | string | 否 | 续重价格(单位:元) 按重量计价必填 0.00-30.00之间的小数，小数点后两位 | `0` |
| `  └ add_num` | body | mixed | 否 | 续件(单位:个) 按数量计价必填 1-999的整数 | `1` |
| `  └ over_weight` | body | string | 否 | 满xx重量包邮 单位：kg | `0` |
| `  └ province_infos` | body | array | 否 | 当前规则生效的地址，统一以List<Struct>结构返回，该结构为嵌套结构。对应的json格式为[{"id":"32","children":[{"id":"320500","children":[{"id":"320508","children":[{"id":"320508014"},{"id":"320508004"}]}]}]}] 注意：返回的为最新的四级地址版本（地址存储升级变更的可能，以最新的返回） | `` |
| `    └ id` | body | mixed | 否 | 地址id，第一级是省份、第二级是城市、第三级是区、第四级是街道 | `11` |
| `    └ children` | body | array | 否 | 当前规则生效的地址，统一以List<Struct>结构返回，该结构为嵌套结构。对应的json格式为[{"id":"32","children":[{"id":"320500","children":[{"id":"320508","children":[{"id":"320508014"},{"id":"320508004"}]}]}]}] 注意：返回的为最新的四级地址版本（地址存储升级变更的可能，以最新的返回） | `` |
| `      └ children` | body | array | 否 | 当前规则生效的地址，统一以List<Struct>结构返回，该结构为嵌套结构。对应的json格式为[{"id":"32","children":[{"id":"320500","children":[{"id":"320508","children":[{"id":"320508014"},{"id":"320508004"}]}]}]}] 注意：返回的为最新的四级地址版本（地址存储升级变更的可能，以最新的返回） | `` |
| `        └ children` | body | array | 否 | 当前规则生效的地址，统一以List<Struct>结构返回，该结构为嵌套结构。对应的json格式为[{"id":"32","children":[{"id":"320500","children":[{"id":"320508","children":[{"id":"320508014"},{"id":"320508004"}]}]}]}] 注意：返回的为最新的四级地址版本（地址存储升级变更的可能，以最新的返回） | `` |
| `          └ id` | body | mixed | 否 | 地址id，第一级是省份、第二级是城市、第三级是区、第四级是街道 | `11000000` |
| `        └ id` | body | mixed | 否 | 地址id，第一级是省份、第二级是城市、第三级是区、第四级是街道 | `110000` |
| `      └ id` | body | mixed | 否 | 地址id，第一级是省份、第二级是城市、第三级是区、第四级是街道 | `1100` |
| `  └ end_time` | body | mixed | 否 | 限售自动解除时间戳，单位秒 | `-` |
| `  └ first_num` | body | mixed | 否 | 首件数量(单位:个) 按数量计价必填 1-999的整数 | `1` |
| `  └ first_num_price` | body | string | 否 | 首件价格(单位:元)按数量计价必填 0.00-30.00之间的小数，小数点后两位 | `1` |
| `  └ is_default` | body | mixed | 否 | 是否默认计价方式(1:是；0:不是) | `1` |
| `  └ is_limited` | body | boolean | 否 | 是否限运规则 | `0` |
| `  └ min_sku_amount` | body | mixed | 否 | 最小商品金额限制条件 | `0` |
| `  └ reason` | body | string | 否 | 限售原因。枚举值 distance_shipping_cost_high：因配送距离导致运费过高 weight_shipping_cost_high：因商品重量导致运费过高 force_majeure：因不可抗力（如会议赛事、自然灾害）不配送 cooperation_express_not_deliver：合作快递不配送 cooperation_express_poor_service：合作快递该区域服务差 other：其他 | `-` |
| `  └ calculate_type` | body | mixed | 否 | 计价方式-1.按重量计价 2.按数量计价 | `2` |
| `  └ max_sku_amount` | body | mixed | 否 | 最大商品金额限制条件 | `0` |
| `  └ rule_type` | body | mixed | 否 | 运费规则类型，同template.rule_type字段; 0:阶梯计价；1:固定运费；2:卖家包邮 | `2` |
| `  └ first_weight` | body | string | 否 | 首重(单位:kg) 按重量计价必填 0.1-999.9之间的小数，小数点后一位 | `1` |
| `  └ add_weight` | body | string | 否 | 续重(单位:kg) 按重量计价必填 0.1-999.9之间的小数，小数点后一位 | `0` |
| `  └ fixed_amount` | body | mixed | 否 | 固定运费金额（单位：分） | `0` |
| `  └ is_over_free` | body | boolean | 否 | 是否条件包邮 | `1` |
| `  └ first_weight_price` | body | string | 否 | 首重价格(单位:元) 按重量计价必填 0.00-30.00之间的小数，小数点后两位 | `1` |
| `  └ add_num_price` | body | string | 否 | 续件价格(单位:元) 按数量计价必填 0.00-30.00之间的小数，小数点后两位 | `1` |
| `  └ over_num` | body | mixed | 否 | 满xx件包邮 | `1` |
| `  └ over_amount` | body | mixed | 否 | 满xx金额包邮 单位：分 | `1` |
| `  └ delivery_fulfillment_mode` | body | mixed | 是 | 履约模式：1：即配，2：次日达，3：全国送 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.trade.freightUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_id` | mixed | 运费模板id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参校验未通过（sub_code: isv.parameter-invalid:422） | - |
| `40004` | 非法的参数 / 运费规则和普通运费规则选择的地址有冲突（sub_code: isv.parameter-invalid:425） | - |
| `40004` | 非法的参数 / 模板被锁定（sub_code: isv.parameter-invalid:426） | - |
| `40004` | 非法的参数 / 发货地址为空（sub_code: isv.parameter-invalid:428） | 补充发货省份或者城市 |
| `40004` | 非法的参数 / 非拍卖资质的商家不可创建运费到付的模板（sub_code: isv.parameter-invalid:429） | - |
| `20000` | 系统错误 / 内部异常，请重试（sub_code: isp.service-error:500） | - |

## 响应示例

成功：

```json
{
  "data": {
    "template_id": "123"
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
  "sub_code": "isv.parameter-invalid:422",
  "sub_msg": "入参校验未通过"
}
```

## 备注
