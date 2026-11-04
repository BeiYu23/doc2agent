# pickup.unbindStoreLibrary

> 门店组批量解绑门店

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.store.pickup.unbindStoreLibrary` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/unbindStoreLibrary` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7337 |
| 更新日期 | `2026-06-24` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_infos` | body | array | 是 | 门店id列表，最大数量100 | `` |
| `  └ store_id` | body | string | 是 | 门店ID | `100` |
| `source` | body | mixed | 是 | 业务类型；2-自提 | `2` |
| `library_id` | body | string | 是 | 门店组id | `200` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/unbindStoreLibrary?app_key=your_appkey_here&method=pickup.unbindStoreLibrary&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `failed_file` | string | 失败的文件链接 | `-` |
| `success_count` | mixed | 成功数量 | `1` |
| `fail_count` | mixed | 失败数量 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -36:门店数量超过100（sub_code: isv.business-failed:-36） | 检查门店数量 |
| `50002` | 业务处理失败 / -7:入参对象为空（sub_code: isv.business-failed:-7） | 检查入参是否完整 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_count": "0",
    "failed_file": "-",
    "success_count": "1"
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
  "sub_code": "isv.business-failed:-36",
  "sub_msg": "-36:门店数量超过100"
}
```

## 备注
