# install.order.supplierComplete

> 服务完成

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.order.supplierComplete` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/order/supplierComplete` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5788 |
| 更新日期 | `2026-07-23` |

## 接口说明

- 文档书: 物流商API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 实操单号 | `""` |
| `operation_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `""` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `""` |
| `real_service_num` | body | number | 否 | 实际完成服务数量 | `1` |
| `report_list` | body | array | 否 | 报告列表 | `` |
| `  └ url` | body | string | 否 | 报告链接 | `""` |
| `  └ expiration_time` | body | string | 否 | 报告过期时间，格式："yyyy-MM-dd HH:mm:ss" | `""` |
| `has_extra_fee` | body | boolean | 否 | 有无额外费用 | `false` |
| `install_fee_info` | body | object | 否 | 安装收费信息 | `` |
| `  └ structured_fee_detail_list` | body | array | 否 | 结构化收费明细列表 | `` |
| `    └ fee_item` | body | string | 是 | 收费项目 | `""` |
| `    └ actual_total_amount_cent` | body | number | 是 | 实际单项总收费金额，单位分 | `1` |
| `    └ price_unit` | body | string | 是 | 计价单位 | `""` |
| `    └ fee_item_desc` | body | string | 是 | 收费项说明 | `""` |
| `    └ actual_unit_price_cent` | body | number | 是 | 实际单价，单位分 | `1` |
| `    └ actual_quantity` | body | string | 是 | 实际发生数量 | `1` |
| `  └ other_proof` | body | array | 否 | 其他证明(图片/pdf/html) url形式 | `-` |
| `  └ special_case_desc` | body | string | 否 | 特殊情况说明 | `""` |
| `  └ unstructured_fee_detail_list` | body | array | 否 | 非结构化收费明细列表 | `` |
| `    └ fee_bill_material_url_list` | body | array | 是 | 收费单材料(图片/pdf/html) url形式 | `-` |
| `  └ install_staff_info` | body | string | 否 | 安装人员信息 | `""` |
| `  └ report_method` | body | string | 是 | 回传方式 1-结构化回传 2-非结构化回传 | `1` |
| `  └ customer_confirmation_proof` | body | array | 是 | 用户确认证明(图片/pdf/html) url形式 | `-` |
| `supplement_install_fee_info` | body | boolean | 否 | 是否补录安装收费信息 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/applyChangePrice?app_key=your_appkey_here&method=recycle.applyChangePrice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000006:状态机跃迁校验错误（sub_code: isv.business-failed:10000006） | 10000006:状态机跃迁校验错误 |
| `50002` | 业务处理失败 / 10000000:请求参数错误（sub_code: isv.business-failed:10000000） | 10000000:请求参数错误 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |
| `50002` | 业务处理失败 / 10000031:不在安装收费信息补录时间窗口范围内（sub_code: isv.business-failed:10000031） | 10000031:不在安装收费信息补录时间窗口范围内 |

## 响应示例

成功：

```json
{
  "data": {
    "err_no": "1",
    "message": "ok"
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
  "sub_code": "isv.business-failed:10000006",
  "sub_msg": "10000006:状态机跃迁校验错误"
}
```

## 备注
