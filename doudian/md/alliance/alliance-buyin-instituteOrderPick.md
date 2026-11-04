# 选品订单明细查询

> buyin.instituteOrderPick — 选品订单明细查询接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 选品订单明细查询 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-instituteOrderPick` |
| 接口 ID | `doudian.alliance.buyin.instituteOrderPick` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/instituteOrderPick` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2008 |
| 更新日期 | `2023-03-22` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | number | 否 | 每页订单数目，取值区间： [1, 100] | `50` |
| `cursor` | body | string | 否 | 下一页索引（第一页传“0”） | `0` |
| `start_time` | body | string | 否 | 支付时间开始，最早支持2022年01月01日 | `2006-01-02 15:04:05` |
| `end_time` | body | string | 否 | 支付时间结束，该时间不能超过start_time+90 | `2006-01-02 15:04:05` |
| `product_id` | body | string | 否 | 商品ID | `492904930493023` |
| `search_type` | body | number | 否 | 查询粒度（1-查询当前应用，2-查询应用所属工具服务商，不包括抖音应用选品GMV数据） | `1` |
| `order_ids` | body | string | 否 | 订单号。多个订单号用英文 "," 分隔，最多支持100个订单号 | `4737996432465788974,4737996432465780075` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `40004` | 非法的参数 / 无效size（sub_code: isv.parameter-invalid:1031） | 无效size |
| `40004` | 非法的参数 / 请指定时间范围或订单号（sub_code: isv.parameter-invalid:1033） | 请指定时间范围或订单号 |
| `40004` | 非法的参数 / 无效开始时间（sub_code: isv.parameter-invalid:1034） | 无效开始时间 |
| `40004` | 非法的参数 / 无效结束时间（sub_code: isv.parameter-invalid:1035） | 无效结束时间 |
| `40004` | 非法的参数 / 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d）（sub_code: isv.parameter-invalid:1036） | 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d） |
| `40004` | 非法的参数 / 起始查询时间超过了最久查询限制（sub_code: isv.parameter-invalid:4168） | 起始查询时间超过了最久查询限制 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 未查询到应用对应工具服务商信息，请联系开发者解决（sub_code: isv.business-failed:8192） | 未查询到应用对应工具服务商信息，请联系开发者解决 |
| `50002` | 业务处理失败 / 1032:参数校验失败：无效order_ids（sub_code: isv.business-failed:1032） | 1032:参数校验失败：无效order_ids |

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
  "sub_code": "isv.parameter-invalid:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
