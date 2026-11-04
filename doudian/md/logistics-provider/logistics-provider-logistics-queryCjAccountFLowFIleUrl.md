# 获取物流服务商对应账户的资金日账单

> logistics.queryCjAccountFLowFIleUrl — 获取物流服务商对应账户的资金日账单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取物流服务商对应账户的资金日账单 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-queryCjAccountFLowFIleUrl` |
| 接口 ID | `doudian.logistics-provider.logistics.queryCjAccountFLowFIleUrl` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/queryCjAccountFLowFIleUrl` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8159 |
| 更新日期 | `2026-03-25` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fetch_day` | body | string | 是 | 日期，日期格式为yyyy-MM-dd | `2026-03-19` |
| `account_type` | body | string | 是 | 账户类型, PA：合众账户，WX：微信账户，BZJ：保障金账户 | `PA` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/queryCjAccountFLowFIleUrl?app_key=your_appkey_here&method=logistics.queryCjAccountFLowFIleUrl&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `file_infos` | array | 文件列表，日账单可能会分为多个文件 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 必填参数为空（sub_code: isv.missing-parameter:16001） | 调整请求参数 |
| `40004` | 非法的参数 / 不能导出一年前的数据（sub_code: isv.parameter-invalid:16002） | 调整请求参数 |
| `40004` | 非法的参数 / 账户类型错误（sub_code: isv.parameter-invalid:16003） | 调整请求参数 |
| `50002` | 业务处理失败 / 文件暂未生成（sub_code: isv.business-failed:16004） | 等待文件生成后再调用 |
| `40004` | 非法的参数 / 日期格式错误（sub_code: isv.parameter-invalid:16005） | 调整请求参数 |
| `20000` | 系统错误 / 未知错误（sub_code: isp.service-error:16006） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "file_infos": [
      {
        "begin_time": "1773849600",
        "end_time": "1773935999",
        "url": "xxx"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:16001",
  "sub_msg": "必填参数为空"
}
```

## 备注
