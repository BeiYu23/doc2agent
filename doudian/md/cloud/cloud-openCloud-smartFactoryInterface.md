# openCloud.smartFactoryInterface

> 智造工场数据开放接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.smartFactoryInterface` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/smartFactoryInterface` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/2907 |
| 更新日期 | `2025-06-30` |

## 接口说明

- 文档书: 电商云API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `api_name` | body | string | 是 | 智造工场开放API名称 | `demo` |
| `body` | body | string | 是 | 智造工场开放API请求体 | `{   "pageNum": 1,   "pageSize": 1 }` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/smartFactoryInterface?app_key=your_appkey_here&method=openCloud.smartFactoryInterface&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | string | 智造工场开放API响应结果 | `{\"Meta\":[{\"Name\":\"shop_id\",\"Type\":\"int\",\"Comment\":\"\"}],\"Data\":[]}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 请求api不存在（sub_code: isv.business-failed:63000700） | 开发者确认apiName是否填写正确 |
| `50002` | 业务处理失败 / 未知错误，请联系客服（sub_code: isv.business-failed:-1） | 未知错误，请联系客服 |
| `50002` | 业务处理失败 / 报表中的API未上线，请先上线API（sub_code: isv.business-failed:63000720） | 报表中的API未上线，请先上线API |
| `50002` | 业务处理失败 / volc inner 调用开放接口失败（sub_code: isv.business-failed:63000704） | volc inner 调用开放接口失败 |
| `50002` | 业务处理失败 / 10000199:未知错误，请联系客服（sub_code: isv.business-failed:10000199） | 10000199:未知错误，请联系客服 |

## 响应示例

成功：

```json
{
  "data": {
    "result": "{\\\"Meta\\\":[{\\\"Name\\\":\\\"shop_id\\\",\\\"Type\\\":\\\"int\\\",\\\"Comment\\\":\\\"\\\"}],\\\"Data\\\":[]}"
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
  "sub_code": "isv.business-failed:63000700",
  "sub_msg": "请求api不存在"
}
```

## 备注
