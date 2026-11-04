# logistics.overSize.updateCollectInfo

> 取件信息推送

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.pickup.logistics.overSize.updateCollectInfo` |
| 中文名 | 取件信息推送 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1526/6710 |
| 更新日期 | `2026-03-18` |

## 接口说明

- 文档书: 上门取件API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 否 | 请求id | `111` |
| `abnormal_quantity` | body | mixed | 否 | 验货异常时，原因是少件或者多件时必传，需要回传实际商品件数。 | `1` |
| `biz_type` | body | string | 否 | 更新类型，支持一次更新多个字段，以‘\|’分割 | `COURIER` |
| `collect_info` | body | object | 否 | 揽收信息 | `` |
| `  └ collect_end_time` | body | string | 否 | 结束揽收时间 | `2021-01-19 20:00:00` |
| `  └ site_name` | body | string | 否 | 网点信息 | `仓前网点` |
| `  └ site_code` | body | string | 否 | 网点编码 | `aaaa` |
| `  └ collect_start_time` | body | string | 否 | 开始揽收时间 | `2021-01-19 09:00:00` |
| `  └ weight_info` | body | object | 否 | 核重核价信息 | `` |
| `    └ length` | body | mixed | 否 | 包裹长度 | `100` |
| `    └ child_package_volume_list` | body | array | 否 | 子单体积数据 | `` |
| `      └ length` | body | mixed | 否 | 包裹长度 | `10` |
| `      └ height` | body | mixed | 否 | 包裹高度 | `10` |
| `      └ width` | body | mixed | 否 | 包裹宽度 | `10` |
| `    └ actual_weight` | body | mixed | 否 | 续重金额（单位分） | `10` |
| `    └ package_fee` | body | mixed | 否 | 包装费（单位分） | `10` |
| `    └ insured_fee` | body | mixed | 否 | 保价费（单位分） | `10` |
| `    └ sum_fee` | body | mixed | 否 | 总金额 （单位分） | `10` |
| `    └ is_master_and_child` | body | boolean | 否 | 是否子母单 | `false` |
| `    └ return_mode` | body | string | 否 | 核重回传模式 | `manual_feedback` |
| `    └ charged_weight` | body | mixed | 否 | 包裹计费重量 | `10` |
| `    └ charged_type` | body | mixed | 否 | 计费类型 | `1--重量 2--体积` |
| `    └ basic_fee` | body | mixed | 否 | 首重金额（单位分） | `10` |
| `    └ width` | body | mixed | 否 | 包裹宽度 | `100` |
| `    └ certificate_photos` | body | array | 否 | 核重核价凭证图片url列表 | `["https://xxx.jpg","https://xxx2.jpg"]` |
| `    └ hight` | body | mixed | 否 | 包裹高度 | `100` |
| `  └ courier_tel` | body | string | 否 | 快递员电话 | `13912439882` |
| `  └ cancel_reason` | body | string | 否 | 取消原因 | `ILLEGAL_ITEM` |
| `  └ charge_fee` | body | object | 否 | 计费信息 | `` |
| `    └ basic_fee` | body | mixed | 否 | 首重运费 | `500` |
| `    └ sum_fee` | body | mixed | 否 | 总金额 | `800` |
| `    └ package_fee` | body | mixed | 否 | 包装费 | `150` |
| `    └ major_fee` | body | mixed | 否 | 主运费，首重+续重 | `700` |
| `    └ payment_fee` | body | mixed | 否 | 用户支付金额 | `0` |
| `    └ claim_fee` | body | mixed | 否 | 应赔付金额 | `0` |
| `    └ add_weight_fee` | body | mixed | 否 | 续重金额 | `200` |
| `    └ insured_fee` | body | mixed | 否 | 保价费 | `5000` |
| `    └ declared_fee` | body | mixed | 否 | 声明保价费 | `6000` |
| `  └ courier_name` | body | string | 否 | 快递员姓名 | `张三` |
| `  └ collect_status` | body | string | 否 | 取件状态【已揽收、已计费、已取消】 | `CHARGED` |
| `order_id` | body | string | 否 | 物流订单号 | `1111` |
| `inspection_result` | body | string | 否 | 验货结果，normal -- 正常 abnornal -- 异常 | `normal` |
| `waybill_code` | body | string | 否 | 运单号 | `JT0101001010` |
| `abnormal_reason` | body | string | 否 | 验货异常原因，支持多个，多个用‘\|’分隔，本次传的编码 | `101` |
| `express` | body | string | 否 | 承运商 | `shunfengkuaiyun` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.overSize.updateCollectInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_weight_exception` | boolean | 是否重量异常 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000:当前状态不允许更新快递员信息（sub_code: isv.business-failed:10000） | 10000:当前状态不允许更新快递员信息 |
| `50002` | 业务处理失败 / 11714:当前状态已取消不允许更新（sub_code: isv.business-failed:11714） | 11714:当前状态已取消不允许更新 |
| `50002` | 业务处理失败 / 6405:Error 1062: Duplicate entry 'LBF00000000112433968953842' for key 'uk_logistics_fulfill_no'（sub_code: isv.business-failed:6405） | 6405:Error 1062: Duplicate entry 'LBF00000000112433968953842' for key 'uk_logistics_fulfill_no' |

## 响应示例

成功：

```json
{
  "data": {
    "is_weight_exception": "true"
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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "10000:当前状态不允许更新快递员信息"
}
```

## 备注
