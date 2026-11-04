# appMessage.templateList

> 获取消息模版列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.appMessage.templateList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/appMessage/templateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/3645 |
| 更新日期 | `2023-05-08` |

## 接口说明

- 文档书: 工具API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_index` | body | number | 是 | 页码，从1开始 | `1` |
| `page_size` | body | number | 是 | 页大小 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/appMessage/templateList?app_key=your_appkey_here&method=appMessage.templateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_list` | array | 消息模板列表 | `` |
| `total` | number | 总数 | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "template_list": [
      {
        "content": "预警内容：{{.warning_content}}",
        "description": "异常预警",
        "example": "{\\\"title\\\":\\\"打单工具-物流异常预警\\\",\\\"content\\\":\\\"预警内容：您的3笔订单，物流出现异常情况，请及时查看。\\\",\\\"jumpUrl\\\":\\\"\\\"}",
        "msg_type": "1",
        "msg_type_str": "待处理任务",
        "params": [
          {
            "example_value": "物流异常",
            "is_necessary": "1",
            "param_desc": "预警标题",
            "param_name": "warning_title"
          }
        ],
        "status": "1",
        "template_id": "1",
        "template_name": "异常预警",
        "title": "{{.app_name}}-{{.warning_title}}预警"
      }
    ],
    "total": "2"
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
