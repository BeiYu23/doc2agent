# logistics.waybillApply

> 获取面单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.waybillApply` |
| 中文名 | 获取面单信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/waybillApply` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/490 |
| 更新日期 | `2021-06-22` |

## 接口说明

- 文档书: 电子面单API（版本 V2.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_applies` | body | array | 是 | 请求结构体 | `` |
| `  └ logistics_code` | body | string | 是 | 物流公司编码 | `1` |
| `  └ track_no` | body | string | 是 | 运单号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/waybillApply?app_key=your_appkey_here&method=logistics.waybillApply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `waybill_infos` | array | 正常返回结构体 | `` |
| `err_infos` | array | 错误返回结构体 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数有误，请检查请求参数（sub_code: isv.missing-parameter:1001） | 参数有误，请检查请求参数 |
| `20000` | 系统错误 / 查询密钥失败（sub_code: isp.service-error:100102） | 请稍后重试 |
| `20000` | 系统错误 / 获取订单信息失败（sub_code: isp.service-error:100101） | 请稍后重试 |
| `50002` | 业务处理失败 / 1003:运单号有误，请检查运单号（sub_code: isv.business-failed:1003） | 请检查运单号 |
| `50002` | 业务处理失败 / 100106:系统错误，请稍后重试（sub_code: isv.business-failed:100106） | 请检查运单号 |

## 响应示例

成功：

```json
{
  "data": {
    "err_infos": [
      {
        "err_code": "1",
        "err_msg": "1",
        "order_id": "1",
        "track_no": "1"
      }
    ],
    "waybill_infos": [
      {
        "order_id": "1",
        "print_data": "1",
        "sign": "1",
        "track_no": "1"
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
  "sub_code": "isv.missing-parameter:1001",
  "sub_msg": "参数有误，请检查请求参数"
}
```

## 备注
