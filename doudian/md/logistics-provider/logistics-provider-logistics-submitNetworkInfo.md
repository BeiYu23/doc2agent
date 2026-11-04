# 物流商提报线路信息

> logistics.submitNetworkInfo — 物流商提报线路信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 物流商提报线路信息 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-submitNetworkInfo` |
| 接口 ID | `doudian.logistics-provider.logistics.submitNetworkInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/submitNetworkInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7046 |
| 更新日期 | `2025-06-09` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `report_type` | body | mixed | 是 | 提报类型，1: 线路时效数据；2：线路揽收时间数据； | `1` |
| `line_time_info_list` | body | array | 否 | 线路时效信息，当report_type为1时，传入该数据；可以选择传入明细list或文件，只可二选一，都传入取数优先级：明细list > 文件url | `` |
| `  └ status` | body | mixed | 否 | 1：生效，2：失效 | `1` |
| `  └ origin_city` | body | string | 否 | 起点-市 | `南京市` |
| `  └ origin_district` | body | string | 否 | 起点-区，是否传入请根据提供的线路粒度决定 | `鼓楼区` |
| `  └ target_province` | body | string | 否 | 终点-省 | `浙江省` |
| `  └ target_street` | body | string | 否 | 终点-街道，是否传入请根据提供的线路粒度决定 | `仓前街道` |
| `  └ last_delivery_time` | body | string | 否 | 最晚送达时间，不同业务类型有不同的格式要求 | `1D` |
| `  └ origin_province` | body | string | 否 | 起点-省 | `江苏省` |
| `  └ origin_street` | body | string | 否 | 起点-街道，是否传入请根据提供的线路粒度决定 | `中央门街道` |
| `  └ target_city` | body | string | 否 | 终点-市 | `杭州市` |
| `  └ target_district` | body | string | 否 | 终点-区，是否传入请根据提供的线路粒度决定 | `余杭区` |
| `  └ product_type_name` | body | string | 否 | 与抖音约定的物流产品名称 | `标快` |
| `  └ product_type_code` | body | string | 否 | 与抖音约定的物流产品编码 | `XX` |
| `line_collect_time_info_list` | body | array | 否 | 线路揽收时间信息，当report_type为2时，传入该数据；可以选择传入明细list或文件，只可二选一，都传入取数优先级：明细list > 文件url | `` |
| `  └ origin_province` | body | string | 否 | 起点-省 | `浙江省` |
| `  └ origin_city` | body | string | 否 | 起点-市 | `杭州市` |
| `  └ origin_district` | body | string | 否 | 起点-区，是否传入请根据提供的线路粒度决定 | `余杭区` |
| `  └ origin_street` | body | string | 否 | 起点-街道，是否传入请根据提供的线路粒度决定 | `仓前街道` |
| `  └ last_collect_time` | body | string | 否 | 最晚揽收时间，“nDhh:mm:ss”格式，示例：0D20:00:00 | `0D20:00:00` |
| `  └ status` | body | mixed | 否 | 1：生效，2：失效 | `1` |
| `  └ product_type_name` | body | string | 否 | 与抖音约定的物流产品名称 | `标快` |
| `  └ product_type_code` | body | string | 否 | 与抖音约定的物流产品编码 | `XX` |
| `line_time_info_file_url` | body | string | 否 | 线路时效信息文件地址，当report_type为1时，可以选择传入明细list或文件，只可二选一，都传入取数优先级：明细list > 文件url | `https://xx.xx.xx` |
| `line_collect_time_info_file_url` | body | string | 否 | 线路揽收时间信息文件地址，当report_type为2时，可以选择传入明细list或文件，只可二选一，都传入取数优先级：明细list > 文件url | `https://xx.xx.xx` |
| `logistics_code` | body | string | 是 | 物流商编码 | `shunfeng` |
| `logistics_sign` | body | string | 是 | 物流商签名，用于鉴权，请妥善保管 | `xxxxx` |
| `business_type` | body | mixed | 是 | 线路业务类型，1:承诺达线路，2:即时零售线路 | `线路的业务类型` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/submitNetworkInfo?app_key=your_appkey_here&method=logistics.submitNetworkInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fail_reason_list` | array | 失败原因列表 | `["产品类型编码为空";"产品类型名称为空"]` |
| `report_id` | mixed | 提报单id | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 信息提报失败（sub_code: isv.business-failed:-1001） | 修改参数或重试 |
| `40004` | 非法的参数 / 线路信息参数不合法（sub_code: isv.parameter-invalid:-1002） | 修改参数 |
| `40004` | 非法的参数 / 不支持的提报类型（sub_code: isv.parameter-invalid:-1003） | 修改提报类型 |
| `40004` | 非法的参数 / 线路信息明细数量超出最大限制（sub_code: isv.parameter-invalid:-1004） | 减少提报数据数量 |
| `40004` | 非法的参数 / 线路信息数量为空（sub_code: isv.parameter-invalid:-1005） | 确认提报数据存在 |
| `40004` | 非法的参数 / 物流商编码(LogisticsCode)为空（sub_code: isv.parameter-invalid:-1006） | 确认物流商编码(LogisticsCode)已传 |
| `40004` | 非法的参数 / 物流商签名(LogisticsSign)为空（sub_code: isv.parameter-invalid:-1007） | 确认物流商编码(LogisticsSign)已传 |
| `40004` | 非法的参数 / 不支持的业务类型（sub_code: isv.parameter-invalid:-1008） | 确认业务类型的取值 |
| `40004` | 非法的参数 / 物流商签名校验失败（sub_code: isv.parameter-invalid:-1009） | 确认签名值合法 |
| `40004` | 非法的参数 / 线路信息不存在（sub_code: isv.parameter-invalid:-1010） | 确认线路是否已提报 |
| `40004` | 非法的参数 / 线路揽收信息不存在（sub_code: isv.parameter-invalid:-1011） | 确认线路揽收信息是否已提报 |
| `40004` | 非法的参数 / 时间格式异常（sub_code: isv.parameter-invalid:-1012） | 确认时间字段是否符合要求 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_reason_list": "[\"产品类型编码为空\";\"产品类型名称为空\"]",
    "report_id": "1"
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
  "sub_code": "isv.business-failed:-1001",
  "sub_msg": "信息提报失败"
}
```

## 备注
