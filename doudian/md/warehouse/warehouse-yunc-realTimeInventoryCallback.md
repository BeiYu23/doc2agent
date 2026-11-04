# yunc.realTimeInventoryCallback

> 实时库存同步接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.realTimeInventoryCallback` |
| 中文名 | 实时库存同步 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/realTimeInventoryCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2990 |
| 更新日期 | `2023-03-17` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `idempotent_no` | body | string | 是 | (字段长度: 50)幂等键本次请求的唯一键 最大50个字符 | `BC1234567789` |
| `total_lines` | body | number | 是 | 总行数 | `123` |
| `current_page` | body | number | 是 | 当前页数 | `1` |
| `page_size` | body | number | 是 | 本页回传的实际总行数。 不超过100， 否则分多次回传 | `9` |
| `occur_time` | body | number | 是 | 当前回传时间，秒级时间戳 | `123456` |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W001` |
| `owner_code` | body | string | 是 | 货主编码 | `BD0029` |
| `details` | body | array | 是 | 货品明细 | `` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7090525558416982316` |
| `  └ inventory_type` | body | string | 是 | 库存类型 1-正品 2-残品 | `1` |
| `  └ inventory_status` | body | string | 是 | 库存状态 1-正常 | `1` |
| `  └ total_num` | body | string | 是 | 库存总数量 （大于等于0） | `100` |
| `  └ can_use_num` | body | string | 是 | 库存可用数量 （大于等于0） | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/inbound/cancel?app_key=your_appkey_here&method=yunc.wms.inbound.cancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 系统调用code | `0` |
| `msg` | string | 调用接口返回的信息 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:1000） | 请重试 |
| `40004` | 非法的参数 / 实时库存回传请求参数校验失败（sub_code: isv.parameter-invalid:14000） | 请检查回传的参数 |
| `40004` | 非法的参数 / 仓库信息不存在（sub_code: isv.parameter-invalid:14001） | 请检查回传的仓编码 |
| `40004` | 非法的参数 / 货主信息不存在（sub_code: isv.parameter-invalid:14002） | 请检查回传的货主编码 |
| `40004` | 非法的参数 / 货品信息不存在（sub_code: isv.parameter-invalid:14003） | 剔除掉不存在的货品信息 |
| `20001` | 内部服务超时 / 同步库存失败（sub_code: isp.service-timeout-error:14004） | 请重试 |
| `50002` | 业务处理失败 / 1001:未查询到有效货品，请校验传入的所有货品编码！（sub_code: isv.business-failed:1001） | 1001:未查询到有效货品，请校验传入的所有货品编码！ |
| `50002` | 业务处理失败 / 1005:幂等检查失败（sub_code: isv.business-failed:1005） | 1005:幂等检查失败 |
| `50002` | 业务处理失败 / 12000:获取仓库信息失败，请检查编码是否有效（sub_code: isv.business-failed:12000） | 12000:获取仓库信息失败，请检查编码是否有效 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1000",
  "sub_msg": "系统错误"
}
```

## 备注
