# openCloud.ddpGetTraceInfo

> 获取数据推送轨迹

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.ddpGetTraceInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/ddpGetTraceInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/5702 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_id` | body | mixed | 是 | 业务ID  1订单 2售后 3商品 | `1` |
| `data_id` | body | string | 是 | 业务单ID | `5032475919537882800` |
| `instance_id` | body | string | 否 | 数据库实例id | `mysql-xxxxxxxxx` |
| `start_time` | body | mixed | 否 | 开始时间 | `1735271910` |
| `end_time` | body | mixed | 否 | 结束时间 | `1735271920` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/ddpGetTraceInfo?app_key=your_appkey_here&method=openCloud.ddpGetTraceInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data_info` | object | 基本信息 | `` |
| `trace_info_list` | array | 轨迹信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 内部错误，请稍后重试（sub_code: isv.business-failed:701） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data_info": {
      "biz_id": "1",
      "biz_name": "订单",
      "biz_status": "5",
      "biz_status_name": "已收货",
      "create_time": "1675818459",
      "data_id": "5032475919537882800",
      "extra": {},
      "history_push_day": "0",
      "last_expiration_time": "1686708852",
      "pay_time": "1675818464",
      "push_status": "1",
      "push_status_name": "已同步",
      "shop_bind_time": "1677069633",
      "shop_id": "77977",
      "shop_name": "刘好好测试",
      "status": "1",
      "update_time": "1685521405"
    },
    "trace_info_list": [
      {
        "biz_status": "5",
        "biz_status_name": "已收货",
        "data_status": "1",
        "data_status_name": "成功",
        "db_instance_id": "mysql-8fd94e30b78x",
        "happen_time": "1685521405",
        "push_type_name": "历史补单",
        "target_version": "1700042732605402",
        "update_time": "1700042722"
      }
    ]
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
  "sub_code": "isv.business-failed:701",
  "sub_msg": "内部错误，请稍后重试"
}
```

## 备注
