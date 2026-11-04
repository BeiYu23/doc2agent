# resale.quote.result

> 服务商质检完成报价/修改报价信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.recycle.resale.quote.result` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/resale/quote/result` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/4628 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 回收寄卖API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 内部单号 | `"1232323213"` |
| `service_entity_code` | body | string | 是 | 服务商编码，平台提供 | `"xxxx"` |
| `inspection_status` | body | mixed | 是 | 质检结果，0：质检成功；1：无法质检等； | `0` |
| `inspection_desc` | body | string | 是 | 质检结果描述 | `"质检完成"` |
| `inspection_report` | body | object | 是 | 质检报告 | `` |
| `  └ report_id` | body | mixed | 是 | 报告ID | `12345545` |
| `  └ report_type` | body | mixed | 是 | 报告类型，1：差异报告，机型一致才出这个报告；2：瑕疵报告，机型不一致才会有； | `1` |
| `  └ report_url` | body | string | 是 | 报告地址 | `"xxxxxx.html"` |
| `  └ report_time` | body | string | 是 | 报告时间 | `"yyyy-MM-dd hh:MM:ss"` |
| `  └ diff_count` | body | mixed | 是 | 差异项数量 | `2` |
| `  └ match_count` | body | mixed | 是 | 吻合项数量 | `2` |
| `  └ raw_data` | body | string | 是 | 质检报告原始数据 | `""` |
| `  └ inspect_product_category_info` | body | object | 否 | 质检结果类目信息 | `` |
| `    └ first_category_id` | body | string | 否 | 一级类目id | `""` |
| `    └ first_category_name` | body | string | 否 | 一级类目名称 | `""` |
| `    └ second_category_id` | body | string | 否 | 二级类目id | `""` |
| `    └ second_category_name` | body | string | 否 | 二级类目名称 | `""` |
| `    └ third_category_id` | body | string | 否 | 三级类目id | `""` |
| `    └ third_category_name` | body | string | 否 | 三级类目名称 | `""` |
| `    └ forth_category_id` | body | string | 否 | 四级类目id | `""` |
| `    └ forth_category_name` | body | string | 否 | 四级类目名称 | `""` |
| `  └ sn_check_res` | body | mixed | 否 | sn校验结果，1：不存在；2：成功；3：失败； | `1` |
| `fixed_price` | body | mixed | 是 | 报价，单位：分 | `20000` |
| `operate_time` | body | string | 是 | 操作时间 | `"yyyy-MM-dd hh:MM:ss"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/resale/quote/result?app_key=your_appkey_here&method=resale.quote.result&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | "" |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10000004",
  "sub_msg": "10000004:系统内部错误"
}
```

## 备注
