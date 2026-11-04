# order.getServiceList

> 获取售后平台客服工单列表，对应抖店功能：https://school.jinritemai.com/doudian/web/lark-doc/fdJHrykEbfsrM

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.getServiceList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getServiceList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1835 |
| 更新日期 | `2022-11-14` |

## 接口说明

- 文档书: 订单API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | number | 是 | 创建开始时间时间戳 | `121312313` |
| `end_time` | body | number | 是 | 创建结束时间时间戳，必须大于开始时间 | `123131221123` |
| `status` | body | string | 否 | 1、不传代表获取全部服务请求     2、操作状态：0 #待处理 10 #审核中 100 #已关闭 | `0` |
| `order_id` | body | number | 否 | 订单id | `212332343564454545` |
| `service_id` | body | number | 否 | 服务单id | `12212121121212` |
| `order_by` | body | string | 否 | 1、默认按服务单创建时间搜索     2、值为“create_time”：按服务单创建时间；值为“update_time”：按服务单更新时间 | `create_time` |
| `page` | body | string | 否 | 页数（默认值为1，第一页从1开始） | `1` |
| `size` | body | string | 否 | 每页订单数（默认为10，最大100），超过100则会按照最大值100处理 | `100` |
| `order` | body | string | 否 | 排序方式：ASC按时间升序，  DESC按时间降序     默认DESC | `ASC` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 总数 | `1122` |
| `list` | array | 列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 时间格式不正确（sub_code: isv.business-failed:10002） | - |

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
  "sub_code": "isv.business-failed:10002",
  "sub_msg": "时间格式不正确"
}
```

## 备注
