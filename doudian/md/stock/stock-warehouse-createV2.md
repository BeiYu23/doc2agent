# warehouse.createV2

> 单个仓创建v2版本

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.warehouse.createV2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/createV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/2390 |
| 更新日期 | `2022-08-18` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse` | body | object | 是 | 仓相关信息 | `` |
| `  └ warehouse_location` | body | object | 是 | 仓的地址编码 | `` |
| `    └ address_id1` | body | number | 是 | 地址1级编码 | `11` |
| `    └ address_id2` | body | number | 是 | 地址2级编码 | `110000` |
| `    └ address_id3` | body | number | 是 | 地址3级编码 | `110105` |
| `    └ address_id4` | body | number | 否 | 地址4级编码 | `110105023` |
| `  └ address_detail` | body | string | 是 | 仓的地址详情 | `朝阳区东风乡将台洼村铁道路口西北` |
| `out_warehouse_id` | body | string | 是 | 外部仓ID | `123` |
| `name` | body | string | 是 | 仓名称 | `测试仓` |
| `intro` | body | string | 是 | 仓介绍 | `介绍一下仓` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/createV2?app_key=your_appkey_here&method=warehouse.createV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_id` | string | 内部仓id | `7020436784400253228` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2） | 修改后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:9999） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_id": "7020436784400253228"
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
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "参数错误"
}
```

## 备注
