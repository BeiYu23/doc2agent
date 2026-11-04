# warehouse.removeAddr

> 地址与区域仓解绑

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.warehouse.removeAddr` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/removeAddr` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/1899 |
| 更新日期 | `2022-05-09` |

## 接口说明

- 文档书: 库存API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 是 | 外部仓库ID | `ABC` |
| `addr` | body | object | 是 | 删除的地址结构体 | `-` |
| `  └ addr_id1` | body | number | 是 | 一级地址id | `1` |
| `  └ addr_id2` | body | number | 否 | 二级地址id | `2` |
| `  └ addr_id3` | body | number | 否 | 三级地址id | `3` |
| `  └ addr_id4` | body | number | 否 | 四级地址id | `4` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/removeAddr?app_key=your_appkey_here&method=warehouse.removeAddr&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误:地址格式错误（sub_code: isv.parameter-invalid:2） | 请检查地址格式 |
| `50002` | 业务处理失败 / 单次请求过于频繁，请稍后重试（sub_code: isv.business-failed:1005） | 请稍后重试 |
| `50002` | 业务处理失败 / 仓库不存在（sub_code: isv.business-failed:20002） | 请检查确认仓库信息 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "参数错误:地址格式错误"
}
```

## 备注
