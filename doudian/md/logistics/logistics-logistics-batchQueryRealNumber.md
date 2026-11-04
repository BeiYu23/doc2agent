# logistics.batchQueryRealNumber

> 批量获取真实手机号

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.batchQueryRealNumber` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/batchQueryRealNumber` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/3534 |
| 更新日期 | `2023-05-16` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_code` | body | string | 是 | 服务编码，联系研发确认 | `xxx` |
| `operation_no_list` | body | array | 是 | 实操单号列表 | `xxx` |
| `service_entity_code` | body | string | 是 | 服务实体编码，联系研发确认 | `xxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/batchQueryRealNumber?app_key=your_appkey_here&method=logistics.batchQueryRealNumber&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `operation_no_2_real_number` | string | 实操单号对应真实手机号map序列化结果 | `xxx` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "operation_no_2_real_number": "xxx"
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
