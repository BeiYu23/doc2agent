# storage.notifySaleReturnStatus

> 回告销退单状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.storage.notifySaleReturnStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/storage/notifySaleReturnStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1866 |
| 更新日期 | `2023-01-04` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_no` | body | string | 是 | 物流订单号 | `LB00001` |
| `vendor` | body | string | 是 | 服务商编码 | `Vendor1` |
| `status` | body | string | 是 | 状态 | `1` |
| `occurrence_time` | body | number | 是 | 业务发生时间 | `1620647951` |
| `reason` | body | string | 否 | 备注，格式严格校验 | `{"error_code": "","error_message": ""}` |
| `logistics_fulfil_no` | body | string | 否 | 物流履约单号 | `123456` |
| `warehouse_code` | body | string | 否 | 仓编码 | `W001` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/storage/notifySaleReturnStatus?app_key=your_appkey_here&method=storage.notifySaleReturnStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / InnerError（sub_code: isp.service-error:1001） | 请重试 |
| `50002` | 业务处理失败 / 5002:sale return order not found（sub_code: isv.business-failed:5002） | 请重试 |
| `40002` | 缺少必选参数 / request cannot be nil（sub_code: isv.missing-parameter:1004） | 请检查请求体后重试 |
| `40002` | 缺少必选参数 / logisticsNo is illegal（sub_code: isv.missing-parameter:1004） | 请检查logisticsNo后重试 |
| `40002` | 缺少必选参数 / VendorNo is illegal（sub_code: isv.missing-parameter:1004） | 请检查VendorNo后重试 |
| `40002` | 缺少必选参数 / Status is illegal（sub_code: isv.missing-parameter:1004） | 请检查Status后重试 |
| `40004` | 非法的参数 / remark format is illegal（sub_code: isv.parameter-invalid:1004） | 请检查remark格式后重试 |

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
  "sub_code": "isp.service-error:1001",
  "sub_msg": "InnerError"
}
```

## 备注
