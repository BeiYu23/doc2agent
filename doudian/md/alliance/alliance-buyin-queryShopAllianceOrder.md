# 获取商家的联盟订单

> buyin.queryShopAllianceOrder — 获取商家的联盟订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取商家的联盟订单 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-queryShopAllianceOrder` |
| 接口 ID | `doudian.alliance.buyin.queryShopAllianceOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/queryShopAllianceOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2407 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | number | 否 | 每页订单数目，取值区间： [1, 20] | `20` |
| `cursor` | body | string | 是 | 下一页索引(第一页传"0") | `0` |
| `start_time` | body | string | 否 | 支付时间开始，最早支持2021年01月01日 | `2022-08-23 00:00:00` |
| `end_time` | body | string | 否 | 支付时间结束，该时间不能超过start_time+90天 | `2022-08-23 23:59:59` |
| `order_ids` | body | string | 否 | 订单号列表，"," 分隔, 最多20个订单号 | `12345678,8765432` |
| `time_type` | body | string | 否 | 查询时间类型。pay: 支付时间（默认）; update：联盟侧更新时间，非订单状态更新时间 | `update` |

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
| `40004` | 非法的参数 / 无效order_ids（sub_code: isv.parameter-invalid:1032） | 无效order_ids |
| `40004` | 非法的参数 / 起始查询时间超过了最久查询限制（sub_code: isv.parameter-invalid:4168） | 起始查询时间超过了最久查询限制 |
| `40004` | 非法的参数 / 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d）（sub_code: isv.parameter-invalid:1039） | 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d） |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 请指定时间范围或订单号（sub_code: isv.parameter-invalid:1033） | 请指定时间范围或订单号 |
| `50002` | 业务处理失败 / 4497:仅支持查询支付时间近1年的订单数据（sub_code: isv.business-failed:4497） | 4497:仅支持查询支付时间近1年的订单数据 |

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
