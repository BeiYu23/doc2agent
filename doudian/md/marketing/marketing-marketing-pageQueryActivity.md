# marketing.pageQueryActivity

> 分页查询营销玩法

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.marketing.marketing.pageQueryActivity` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/pageQueryActivity` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/7777 |
| 更新日期 | `2025-09-16` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 否 | 页码 | `1` |
| `page_size` | body | number | 否 | 每页数量。最多不超过20。 | `20` |
| `activity_query_index_info` | body | object | 否 | 玩法查询索引信息 | `` |
| `  └ activity_query_index_item_list` | body | array | 否 | 索引列表 | `` |
| `    └ activity_index_key` | body | string | 否 | 玩法索引键。 activity_name: 活动名称; activity_code_list: 玩法编码列表; status_list: 活动状态列表; time_buy_discount_type: 单品直降优惠类型; product_id: 商品ID; start_time_before: 活动开始时间下限; start_time_after: 活动开始时间下限; start_time_before: 活动结束时间下限; end_time_after: 活动结束时间上限。状态查询需搭配活动时间索引条件 | `activity_code_list` |
| `    └ activity_index_value` | body | string | 否 | 玩法索引值。list 用英文逗号分隔 | `LimitTimeTimeBuy,LimitQuantityTimeBuy` |
| `activity_query_option_list` | body | array | 否 | 玩法查询选项列表。activity_dto : 玩法模型; need_product_info: 需要商品信息 | `["activity_dto","need_product_info"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolOrderAds?app_key=your_appkey_here&method=buyin.kolOrderAds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_model` | array | 玩法模型 | `` |
| `total` | number | 总数 | `800` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:-100001） | 调整入参 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-100002） | 联系技术人员 |

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
  "sub_code": "isv.parameter-invalid:-100001",
  "sub_msg": "参数校验失败"
}
```

## 备注
