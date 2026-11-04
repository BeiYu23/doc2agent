# buyin.instituteOrderColonel

> 查询团长抖音、火山、头条和西瓜订单，需要团长百应授权

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.instituteOrderColonel` |
| 中文名 | 查询团长抖音 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/instituteOrderColonel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1603 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 精选联盟API（版本 V10.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | number | 否 | 每页订单数目，取值区间： [1, 200] | `20` |
| `cursor` | body | string | 否 | 下一页索引（第一页传“0”） | `0` |
| `start_time` | body | string | 否 | 支付时间开始，最早支持90天前 | `2006-01-02 15:04:05` |
| `end_time` | body | string | 否 | 支付时间结束 | `2006-01-02 15:04:05` |
| `order_ids` | body | string | 否 | 订单号，时间范围和订单号必须指定至少一个。多个订单号用英文 , 分隔，最多支持10个订单号 | `4737996432465788974,4737996432465780075` |
| `time_type` | body | string | 否 | 查询时间类型。pay: 支付时间（默认）; update：联盟侧更新时间，非订单状态更新时间 | `pay` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `40004` | 非法的参数 / 无效size（sub_code: isv.parameter-invalid:1031） | 参数校验失败：无效size |
| `40004` | 非法的参数 / 无效order_ids（sub_code: isv.parameter-invalid:1032） | 参数校验失败：无效order_ids |
| `40004` | 非法的参数 / 请指定时间范围或订单号（sub_code: isv.parameter-invalid:1033） | 参数校验失败: 请指定时间范围或订单号 |
| `40004` | 非法的参数 / 无效开始时间（sub_code: isv.parameter-invalid:1034） | 参数校验失败：无效开始时间 |
| `40004` | 非法的参数 / 无效结束时间（sub_code: isv.parameter-invalid:1035） | 参数校验失败：无效结束时间 |
| `40004` | 非法的参数 / 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d）（sub_code: isv.parameter-invalid:1036） | 参数校验失败：无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d） |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 起始查询时间超过了最久查询限制（sub_code: isv.parameter-invalid:4168） | 起始查询时间超过了最久查询限制 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 请检查账号是否可以正常使用，比如是否完成协议签署、是否被清退/关闭等 |
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
