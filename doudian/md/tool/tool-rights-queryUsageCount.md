# rights.queryUsageCount

> 查询权益可使用次数

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.rights.queryUsageCount` |
| 中文名 | 查询权益可使用次数 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/rights/queryUsageCount` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/6059 |
| 更新日期 | `2024-01-12` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_biz_id` | body | string | 否 | 外部业务ID(模板市场为模板code)，非必传，不可与service_id同传 | `6859718390706503687` |
| `service_id` | body | mixed | 否 | 抖店服务市场服务ID，非必传，不可与outer_biz_id同传 | `11111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/rights/queryUsageCount?app_key=your_appkey_here&method=rights.queryUsageCount&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `canDeductCount` | mixed | 可扣减次数 | `1000` |
| `frozenCount` | mixed | 冻结中的次数(处于退款中/换版本中等状态的次数) | `500` |
| `totalCount` | mixed | 总的可使用次数 | `1500` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:100001） | 修改为正确的传参 |
| `50002` | 业务处理失败 / 查询数据库错误（sub_code: isv.business-failed:200） | 等待系统恢复后重试 |
| `50002` | 业务处理失败 / 越权（sub_code: isv.business-failed:500） | 仅查询或处理属于服务商自己的信息 |

## 响应示例

成功：

```json
{
  "data": {
    "canDeductCount": "1000",
    "frozenCount": "500",
    "totalCount": "1500"
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
  "sub_code": "isv.parameter-invalid:100001",
  "sub_msg": "参数错误"
}
```

## 备注
