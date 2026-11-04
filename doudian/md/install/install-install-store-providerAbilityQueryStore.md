# install.store.providerAbilityQueryStore

> 到店安装通过服务能力反查门店id列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.providerAbilityQueryStore` |
| 中文名 | 到店安装通过服务能力反查门店id列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/providerAbilityQueryStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7843 |
| 更新日期 | `2025-11-05` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ability_id` | body | string | 是 | 能力id (注意，这里只能是单个能力哈，不支持多个能力) | `33862_549444_9343` |
| `lp_code` | body | string | 是 | 服务商code | `xxxx` |
| `pn` | body | mixed | 否 | 页码 | `1` |
| `rn` | body | mixed | 否 | 当前大小 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.providerAbilityQueryStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_id_list` | array | 门店id列表(具备指定能力的门店id列表) | `<1,2,3>` |
| `pn` | mixed | 当前页码 | `1` |
| `rn` | mixed | 每一页的数量 | `10` |
| `total` | mixed | 返回的总数量 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "pn": "1",
    "rn": "10",
    "store_id_list": "<1,2,3>",
    "total": "100"
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
