# logistics.BatchCheckServiceOpenStatus

> 批量服务订购查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.BatchCheckServiceOpenStatus` |
| 中文名 | 批量服务订购查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/BatchCheckServiceOpenStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/4838 |
| 更新日期 | `2023-10-10` |

## 接口说明

- 文档书: 电子面单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id_list` | body | array | 是 | 订购方列表 | `[]` |
| `buyer_type` | body | string | 是 | 订购方类型 | `1` |
| `biz_type_list` | body | array | 是 | 业务类型列表 | `[]` |
| `service_code` | body | string | 是 | 服务编码 | `""` |
| `fallback_to_d_b` | body | boolean | 否 | false | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/BatchCheckServiceOpenStatus?app_key=your_appkey_here&method=logistics.BatchCheckServiceOpenStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `open_status_list` | array | [] | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "open_status_list": [
      {
        "biz_type": "\"\"",
        "open_status": "1",
        "shop_id": "\"\""
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
