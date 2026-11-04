# product.listChannelProduct

> 检索渠道商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.listChannelProduct` |
| 中文名 | 检索渠道商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/listChannelProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4465 |
| 更新日期 | `2024-05-13` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `main_product_id` | body | number | 是 | 主商品ID。不需要此查询条件可传0 | `3232323232323232` |
| `channel_id` | body | array | 否 | 渠道ID | `1771739938745351` |
| `channel_type` | body | array | 否 | 渠道类型：3商家自卖，4达人带货 | `3` |
| `kol_id` | body | array | 否 | 绑定的达人ID | `1111` |
| `status` | body | number | 否 | 渠道品状态：0下架，2上架，3封禁 | `2` |
| `start_time` | body | string | 否 | 有效期开始时间 | `2023-07-01 00:00:00` |
| `end_time` | body | string | 否 | 有效期结束时间 | `2023-07-21 00:00:00` |
| `page` | body | number | 是 | 第几页，从1开始 | `1` |
| `size` | body | number | 是 | 每页数量，默认20，最多50 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=yunc.erp.inbound.callback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 渠道品列表 | `` |
| `total` | number | 总数 | `12` |
| `page` | number | 当前页面数 | `1` |
| `size` | number | 每页数目大小 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 商家不在开放名单内（sub_code: isv.business-failed:2010003） | 商家不在开放名单内 |
| `50002` | 业务处理失败 / 系统异常,请重试（sub_code: isv.business-failed:2010001） | 系统异常,请重试 |
| `50002` | 业务处理失败 / pageSize不可超过50（sub_code: isv.business-failed:2010004） | pageSize不可超过50 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
  "sub_code": "isv.business-failed:2010003",
  "sub_msg": "商家不在开放名单内"
}
```

## 备注
