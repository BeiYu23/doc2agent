# 店铺活动查询

> mini.activity.query — 店铺活动查询接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 店铺活动查询 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-activity-query` |
| 接口 ID | `doudian.miniapp.mini.activity.query` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/query` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6038 |
| 更新日期 | `2024-01-09` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 否 | 活动id | `3640367995802523837` |
| `product_id` | body | mixed | 否 | 商品id | `3640367995802523837` |
| `page_no` | body | mixed | 否 | 从1开始 默认值1 | `1` |
| `page_size` | body | mixed | 否 | 不能超过100 默认值100 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/activity/query?app_key=your_appkey_here&method=mini.activity.query&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_info_list` | array | 活动列表 | `` |
| `total_cnt` | mixed | 总条数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:606010000） | 请检查请求入参 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_info_list": [
      {
        "activity_end_time": "1696151030",
        "activity_id": "7279748320698827052",
        "activity_name": "瓜瓜的任务NewName",
        "activity_start_time": "1696151030",
        "activity_status": "1",
        "product_id": "3639483739320549069",
        "user_buy_limit": "10"
      }
    ],
    "total_cnt": "10"
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
  "sub_code": "isv.parameter-invalid:606010000",
  "sub_msg": "参数错误"
}
```

## 备注
