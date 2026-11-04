# logistics.operatorCheckInEvent

> 师傅上门签到事件

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.operatorCheckInEvent` |
| 中文名 | 师傅上门签到事件 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/operatorCheckInEvent` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/3535 |
| 更新日期 | `2023-04-19` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_code` | body | string | 是 | 服务编码 | `xxx` |
| `operation_no` | body | string | 是 | 实操单号 | `xxx` |
| `operator_name` | body | string | 是 | 师傅姓名 | `xxx` |
| `operator_phone` | body | string | 是 | 师傅电话 | `xxx` |
| `operation_time` | body | string | 是 | 上门时间，格式："yyyy-MM-dd HH:mm:ss" | `xxx` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `xxx` |
| `img_url` | body | string | 是 | 图片链接 | `xxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/operatorCheckInEvent?app_key=your_appkey_here&method=logistics.operatorCheckInEvent&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
