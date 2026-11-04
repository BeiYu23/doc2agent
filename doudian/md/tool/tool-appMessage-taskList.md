# appMessage.taskList

> 获取服务市场应用消息任务列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.appMessage.taskList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/appMessage/taskList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/3646 |
| 更新日期 | `2023-05-08` |

## 接口说明

- 文档书: 工具API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | number | 否 | 模板id | `1` |
| `page_no` | body | number | 是 | 页码，从1开始 | `1` |
| `page_size` | body | number | 是 | 页大小 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/appMessage/taskList?app_key=your_appkey_here&method=appMessage.taskList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_list` | array | 消息任务列表 | `` |
| `total` | number | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "task_list": [
      {
        "app_id": "6864478719709301000",
        "app_name": "open_admin自动化",
        "create_time": "1683544661",
        "failure_cnt": "0",
        "id": "168",
        "msg_param": "{\\\"warning_title\\\":\\\"物流异常\\\",\\\"warning_content\\\":\\\"您的78笔订单，物流出现异常情况，请及时查看。\\\",\\\"jump_url\\\":\\\"https://www.baidu.com/\\\"}",
        "rid": "7791664a-beee-5a41-0ae6-06dc93d5e619",
        "send_status": "3",
        "send_to": "12345",
        "shop_name": "刘好好",
        "success_cnt": "1",
        "template_id": "6864478719709301000",
        "template_name": "异常预警",
        "update_time": "1683544662"
      }
    ],
    "total": "10"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
