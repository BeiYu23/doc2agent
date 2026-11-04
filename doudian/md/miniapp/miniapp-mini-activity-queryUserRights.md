# 查询用户店铺下的权益列表

> mini.activity.queryUserRights — 查询用户店铺下的权益列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询用户店铺下的权益列表 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-activity-queryUserRights` |
| 接口 ID | `doudian.miniapp.mini.activity.queryUserRights` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/queryUserRights` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6039 |
| 更新日期 | `2024-04-25` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 否 | 活动id | `3640367995802523837` |
| `doudian_open_id` | body | string | 是 | 抖店open_id | `1@#YOUR_SECRET_KEY` |
| `page_no` | body | mixed | 否 | 从1开始，默认值1 | `1` |
| `page_size` | body | mixed | 否 | 不能超过100，默认值100 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=mini.activity.queryUserRights&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_info_list` | array | 用户活动权益列表 | `` |
| `total_cnt` | mixed | 总条数 | `5` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:606010000） | 请检查请求入参 |
| `20000` | 系统错误 / 系统内部错误，请稍后重试（sub_code: isp.service-error:606000103） | 系统内部错误，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_info_list": [
      {
        "activity_id": "7279187821620381228",
        "rights_count": "10",
        "used_amount": "5"
      }
    ],
    "total_cnt": "5"
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
