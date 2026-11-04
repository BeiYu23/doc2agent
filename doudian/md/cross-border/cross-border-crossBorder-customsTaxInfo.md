# 服务商回告海关税费

> crossBorder.customsTaxInfo — 服务商回告海关税费

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商回告海关税费 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-crossBorder-customsTaxInfo` |
| 接口 ID | `doudian.cross-border.crossBorder.customsTaxInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/customsTaxInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/1761 |
| 更新日期 | `2022-04-11` |

## 接口说明

- 文档书: 跨境API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vendor` | body | string | 是 | 字节给供应链服务商定义的编码 | `QS` |
| `customs_code` | body | string | 是 | 回执口岸【口岸代码】 | `3516` |
| `customs_name` | body | string | 是 | 回执口岸【口岸名称】 | `平潭海关` |
| `customs_tax_data` | body | object | 是 | 税费信息 | `` |
| `  └ order_id` | body | string | 是 | 字节电商平台的交易订单号 | `9920138805717562814` |
| `  └ invt_no` | body | string | 否 | 进口清单编号 (宁波 非必传) | `951620221063608616` |
| `  └ tax_no` | body | string | 否 | 电子税单编号 (宁波 非必传) | `951620221063608616_0` |
| `  └ ebc_name` | body | string | 否 | 电商企业名称 (宁波 必传) | `宁波xxxx物流有限公司` |
| `  └ return_time` | body | string | 是 | 回执时间 秒时间戳 | `1652932109` |
| `  └ customs_tax` | body | string | 是 | 应征关税，例如2.16元传2.16 | `0.0` |
| `  └ value_added_tax` | body | string | 是 | 应征增值税，例如2.16元传2.16 | `2.16` |
| `  └ consumption_tax` | body | string | 是 | 应征消费税，例如2.16元传2.16 | `0.0` |
| `  └ status` | body | string | 否 | (宁波 非必传) 海关税单状态  1-已生成，2-已汇总 3-作废 | `1` |
| `  └ tax_detail_list` | body | array | 是 | 商品税费列表 | `` |
| `    └ gnum` | body | string | 是 | 商品项号 | `1` |
| `    └ gcode` | body | string | 是 | 海关商品编码 (宁波传HS编码) | `1806900000` |
| `    └ tax_price` | body | string | 否 | 完税总价格，例如23.74元传23.74 | `23.74` |
| `    └ customs_tax` | body | string | 是 | 关税，例如2.16元传2.16 | `0.0` |
| `    └ value_added_tax` | body | string | 是 | 增值税，例如2.16元传2.16 | `2.16` |
| `    └ consumption_tax` | body | string | 是 | 消费税，例如2.16元传2.16 | `0.0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/customsTaxInfo?app_key=your_appkey_here&method=crossBorder.customsTaxInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 成功就是0 | `0` |
| `msg` | string | 响应msg | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 1000: 非法的参数（sub_code: isv.parameter-invalid:1000） | 检查参数是否正确，若确认参数正确请联系工作人员 |
| `50002` | 业务处理失败 / 1005:接口调用异常，请重试，多次失败请人工反馈（sub_code: isv.business-failed:1005） | 重试，多次失败联系工作人员 |
| `50002` | 业务处理失败 / 1001:未知异常（sub_code: isv.business-failed:1001） | 1001:未知异常 |
| `50002` | 业务处理失败 / 1002:orderId值不能为空！（sub_code: isv.business-failed:1002） | 1002:orderId值不能为空！ |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "成功"
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
  "sub_code": "isv.parameter-invalid:1000",
  "sub_msg": "1000: 非法的参数"
}
```

## 备注
