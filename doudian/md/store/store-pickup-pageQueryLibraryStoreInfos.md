# pickup.pageQueryLibraryStoreInfos

> 门店组绑定门店列表查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.store.pickup.pageQueryLibraryStoreInfos` |
| 中文名 | 门店组绑定门店列表查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/pageQueryLibraryStoreInfos` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7104 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `library_id` | body | string | 是 | 门店组id | `""` |
| `size` | body | mixed | 是 | 分页大小 | `1` |
| `city_code` | body | string | 否 | 二级市编码 | `""` |
| `district_code` | body | string | 否 | 区编码 | `""` |
| `source` | body | mixed | 是 | 业务类型：2-到店自提 | `2` |
| `store_id` | body | string | 否 | 门店id | `""` |
| `store_code` | body | string | 否 | 门店编码 | `""` |
| `store_name` | body | string | 否 | 门店名称 | `""` |
| `province_code` | body | string | 否 | 省编码 | `""` |
| `page` | body | mixed | 是 | 页码，从1开始 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/pageQueryLibraryStoreInfos?app_key=your_appkey_here&method=pickup.pageQueryLibraryStoreInfos&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_infos` | array | "" | `` |
| `total` | mixed | 门店数量 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1000000001:业务身份错误,无法解析（sub_code: isv.business-failed:1000000001） | 请确认业务身份类型参数 |

## 响应示例

成功：

```json
{
  "data": {
    "store_infos": [
      {
        "name": "\"\"",
        "store_id": "\"\""
      }
    ],
    "total": "0"
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
  "sub_code": "isv.business-failed:1000000001",
  "sub_msg": "1000000001:业务身份错误,无法解析"
}
```

## 备注
