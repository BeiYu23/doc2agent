# sms.queryPublicDomainAudience

> 查询公域标签圈选的人群包

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.queryPublicDomainAudience` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/queryPublicDomainAudience` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7503 |
| 更新日期 | `2025-10-15` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `audience_name` | body | string | 否 | 人群包名称 | `人群包名称` |
| `audience_id` | body | string | 否 | 人群包ID | `12323` |
| `page` | body | mixed | 否 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 否 | 每页数量，需要小于100 | `20` |
| `token` | body | string | 是 | 组件token获取，对接API文档：https://op.jinritemai.com/docs/api-docs/162/3586 | `wefsdfsa` |
| `audience_type` | body | mixed | 否 | 0-公域人群 2-组合人群 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/queryPublicDomainAudience?app_key=your_appkey_here&method=sms.queryPublicDomainAudience&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `10` |
| `results` | array | 结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "results": [
      {
        "audience_id": "12323",
        "audience_name": "人群包名称",
        "audience_type": "0",
        "create_time": "1749453592",
        "node_list": [
          {
            "condition": "AND",
            "node_type": "1",
            "produce_id": "12"
          }
        ],
        "update_time": "1749453592"
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
