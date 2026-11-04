# 批量更新门店状态

> pickup.batchUpdateStoreStatus — 批量更新门店状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量更新门店状态 |
| 文档地址 | `/docs/doudian/store/store-pickup-batchUpdateStoreStatus` |
| 接口 ID | `doudian.store.pickup.batchUpdateStoreStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/batchUpdateStoreStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7235 |
| 更新日期 | `2026-06-24` |

## 接口说明

- 文档书: 自提门店API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `batch_update_store_status_info` | body | object | 是 | 门店状态 | `` |
| `  └ store_id_list` | body | array | 是 | 门店id列表 | `-` |
| `  └ state` | body | mixed | 是 | 门店主状态 5:正常营业 6:暂停营业 仅可在两个状态之间切换，避免同状态变更 | `6` |
| `  └ biz_type` | body | mixed | 是 | 门店类型 2:到店自提 | `2` |
| `  └ suspend_type` | body | mixed | 是 | 停业类型 1:主动操作 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/batchUpdateStoreStatus?app_key=your_appkey_here&method=pickup.batchUpdateStoreStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
