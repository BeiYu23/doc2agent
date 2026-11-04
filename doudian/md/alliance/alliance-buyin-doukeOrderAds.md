# 查询独立抖客分销订单

> buyin.doukeOrderAds — 查询独立抖客分销订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询独立抖客分销订单 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-doukeOrderAds` |
| 接口 ID | `doudian.alliance.buyin.doukeOrderAds` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/doukeOrderAds` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/3083 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | mixed | 否 | 每页订单数目，取值区间： [1, 200] | `20` |
| `cursor` | body | string | 否 | 下一页索引（第一页传“0”） | `0` |
| `start_time` | body | string | 否 | 支付时间开始，最早支持90天前 | `2006-01-02 15:04:05` |
| `end_time` | body | string | 否 | 支付时间结束 | `2006-01-02 15:04:05` |
| `order_ids` | body | string | 否 | 订单号。多个订单号用英文 , 分隔，最多支持10个订单号 | `4737996432465788974,4737996432465780075` |
| `pid` | body | string | 否 | 抖客PID | `dy_1234_4567_7890` |
| `distribution_type` | body | string | 否 | 分销类型。Live-直播间分销订单，ProductDetail-商品分销订单，ActivityMaterial-活动页订单 | `Live` |
| `time_type` | body | string | 否 | 查询时间类型。pay: 支付时间（默认）; update：联盟侧更新时间，非订单状态更新时间 | `update` |
| `query_order_type` | body | mixed | 否 | 不填或者填0：查询分销订单，1：查询比价订单 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/doukeOrderAds?app_key=your_appkey_here&method=buyin.doukeOrderAds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败：无效size（sub_code: isv.parameter-invalid:4246） | 参数校验失败：无效size |
| `40004` | 非法的参数 / 参数校验失败：无效order_ids（sub_code: isv.parameter-invalid:4247） | 参数校验失败：无效order_ids |
| `40004` | 非法的参数 / 参数校验失败: 请指定时间范围或订单号（sub_code: isv.parameter-invalid:4248） | 参数校验失败: 请指定时间范围或订单号 |
| `40004` | 非法的参数 / 参数校验失败：无效开始时间（sub_code: isv.parameter-invalid:4249） | 参数校验失败：无效开始时间 |
| `40004` | 非法的参数 / 参数校验失败：无效结束时间（sub_code: isv.parameter-invalid:4250） | 参数校验失败：无效结束时间 |
| `40004` | 非法的参数 / 参数校验失败：无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d）（sub_code: isv.parameter-invalid:4251） | 参数校验失败：无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d） |
| `40004` | 非法的参数 / 无效订单查询时间类型（sub_code: isv.parameter-invalid:4252） | 无效订单查询时间类型 |
| `40004` | 非法的参数 / 起始查询时间超过了最久查询限制（sub_code: isv.parameter-invalid:4253） | 起始查询时间超过了最久查询限制 |
| `40004` | 非法的参数 / 需【独立抖客】角色授权后访问（sub_code: isv.parameter-invalid:8198） | 需【独立抖客】角色授权后访问 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:4097） | 参数校验失败 |
| `50002` | 业务处理失败 / 参数校验失败：无效 PID（sub_code: isv.business-failed:4102） | 参数校验失败：无效 PID |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "sub_code": "isv.parameter-invalid:4246",
  "sub_msg": "参数校验失败：无效size"
}
```

## 备注
