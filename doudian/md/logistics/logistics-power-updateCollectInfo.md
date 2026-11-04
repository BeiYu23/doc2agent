# 取件信息推送（仅用于兼容老物流网关

> power.updateCollectInfo — 取件信息推送（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 取件信息推送（仅用于兼容老物流网关 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-updateCollectInfo` |
| 接口 ID | `doudian.logistics.power.updateCollectInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/updateCollectInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/8526 |
| 更新日期 | `2026-08-20` |

## 接口说明

- 文档书: 物流发货API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_type` | body | string | 否 | 更新类型，支持一次更新多个字段，以‘\|’分割 | `COURIER` |
| `waybill_code` | body | string | 否 | 运单号 | `JT0101001010` |
| `collect_info` | body | object | 否 | - | `` |
| `  └ site_code` | body | string | 否 | 网点编码 | `qwwww` |
| `  └ site_name` | body | string | 否 | 网点名称 | `仓前网点` |
| `  └ courier_tel` | body | string | 否 | 快递员手机号 | `13912439882` |
| `  └ courier_name` | body | string | 否 | 快递员姓名 | `张三` |
| `  └ collect_start_time` | body | string | 否 | 开始揽收时间 | `2021-01-19 09:00:00` |
| `  └ weight_info` | body | object | 否 | 核重核价信息 | `` |
| `    └ charged_type` | body | mixed | 否 | 计费类型 | `1--重量 2--体积` |
| `    └ length` | body | mixed | 否 | 包裹长度 | `100` |
| `    └ child_package_volume_list` | body | array | 否 | 子单体积数据 | `` |
| `      └ length` | body | mixed | 否 | 包裹长度 | `100` |
| `      └ width` | body | mixed | 否 | 包裹宽度 | `100` |
| `      └ height` | body | mixed | 否 | 包裹高度 | `100` |
| `    └ return_mode` | body | string | 否 | 核重回传模式： manual_feedback 快递员人工回传 system_backup_feedback 系统兜底回传 | `manual_feedback` |
| `    └ hight` | body | mixed | 否 | 包裹高度 | `100` |
| `    └ actual_weight` | body | mixed | 否 | 包裹实际重量 | `10` |
| `    └ width` | body | mixed | 否 | 包裹宽度 | `100` |
| `    └ insured_fee` | body | mixed | 否 | 保价费（单位分） | `10` |
| `    └ certificate_photos` | body | array | 否 | 核重核价凭证图片url列表 | `["https://xxx.jpg","https://xxx2.jpg"]` |
| `    └ sum_fee` | body | mixed | 否 | 总金额（单位分） | `10` |
| `    └ charged_weight` | body | mixed | 否 | 包裹计费重量 | `10` |
| `    └ package_fee` | body | mixed | 否 | 包装费（单位分） | `10` |
| `    └ basic_fee` | body | mixed | 否 | 首重金额（单位分） | `10` |
| `    └ is_master_and_child` | body | boolean | 否 | 是否子母单 | `false` |
| `  └ cancel_reason` | body | string | 否 | 取消/拦截原因 | `ILLEGAL_ITEM` |
| `  └ collect_end_time` | body | string | 否 | 截止揽收时间 | `2021-01-19 20:00:00` |
| `  └ package_img_url_list` | body | array | 否 | 开箱验视照片 | `xxx` |
| `  └ charge_fee` | body | object | 否 | 计费信息 | `` |
| `    └ declared_fee` | body | mixed | 否 | 续重金额（单位分） | `6000` |
| `    └ insured_fee` | body | mixed | 否 | 保价费（单位分） | `5000` |
| `    └ package_fee` | body | mixed | 否 | 包装费（单位分） | `150` |
| `    └ add_weight_fee` | body | mixed | 否 | 续重金额（单位分） | `200` |
| `    └ payment_fee` | body | mixed | 否 | - | `0` |
| `    └ major_fee` | body | mixed | 否 | 主运费（单位分），为首重 + 续重 金额「必传」 | `700` |
| `    └ claim_fee` | body | mixed | 否 | - | `0` |
| `    └ sum_fee` | body | mixed | 否 | 总金额 （单位分） | `800` |
| `    └ basic_fee` | body | mixed | 否 | 首重金额（单位分） | `500` |
| `  └ collect_status` | body | string | 否 | 取件状态 | `CHARGED` |
| `order_id` | body | string | 否 | 取号时传的orderId字段 | `1111` |
| `inspection_result` | body | string | 否 | 验货结果 normal -- 正常 abnornal  -- 异常 | `normal` |
| `request_id` | body | string | 否 | 请求唯独id | `true` |
| `abnormal_reason` | body | string | 否 | 支持多个传，‘｜’隔开 | `101` |
| `abnormal_quantity` | body | mixed | 否 | 缺件或者少件时必传 | `1` |
| `app_key` | body | string | 否 | appKey | `appKey` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/updateCollectInfo?app_key=your_appkey_here&method=power.updateCollectInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_weight_exception` | boolean | 订单属性 | `重量是否异常` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11710:当前状态不允许变更（sub_code: isv.business-failed:11710） | 推送正确状态 |
| `50002` | 业务处理失败 / 10000:当前状态不允许更新快递员信息（sub_code: isv.business-failed:10000） | 推送正确状态 |
| `50002` | 业务处理失败 / 11714:当前状态已取消不允许更新（sub_code: isv.business-failed:11714） | 推送正确状态 |
| `50002` | 业务处理失败 / 11715:当前状态已取消不允许更新（sub_code: isv.business-failed:11715） | 推送正确状态 |
| `50002` | 业务处理失败 / 11713:重复拦截（sub_code: isv.business-failed:11713） | 推送正确状态 |
| `50002` | 业务处理失败 / 6405:系统错误（sub_code: isv.business-failed:6405） | 重试 |
| `50002` | 业务处理失败 / -10007:未知错误（sub_code: isv.business-failed:-10007） | 重试 |
| `50002` | 业务处理失败 / 重量异常，重新输入重量信息（sub_code: isv.business-failed:11719） | 重新推送核价 |
| `50002` | 业务处理失败 / 重复核重核价（sub_code: isv.business-failed:11718） | 不需要推送核价 |
| `50002` | 业务处理失败 / 重复揽收（sub_code: isv.business-failed:11712） | 不允许推送揽收 |
| `50002` | 业务处理失败 / 10007:cannot update collectTime（sub_code: isv.business-failed:10007） | 推送正确状态 |

## 响应示例

成功：

```json
{
  "data": {
    "is_weight_exception": "重量是否异常"
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
  "sub_code": "isv.business-failed:11710",
  "sub_msg": "11710:当前状态不允许变更"
}
```

## 备注
