# logistics.getSNInWarehouse

> 获取SN入库数据接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.getSNInWarehouse` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getSNInWarehouse` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/6720 |
| 更新日期 | `2024-07-21` |

## 接口说明

- 文档书: 物流发货API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_num` | body | mixed | 是 | 页码 | `1` |
| `page_size` | body | mixed | 是 | 每页数量 | `10` |
| `data_date_start` | body | string | 是 | 业务开始时间，yyyyMMddHHmmss 格式 | `20220320000000` |
| `data_date_end` | body | string | 是 | 业务结束时间，yyyyMMddHHmmss 格式 | `20220320235959` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getSNInWarehouse?app_key=your_appkey_here&method=logistics.getSNInWarehouse&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `list` | array | 入库记录 | `` |
| `total` | mixed | 返回业务数据总条数 | `231` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 错误appkey（sub_code: isv.parameter-invalid:10001） | 咨询连接平台入驻人员 |
| `40004` | 非法的参数 / 时间戳失效，校验时间戳5分钟内（sub_code: isv.parameter-invalid:10002） | 重新请求 |
| `40004` | 非法的参数 / 签名错误（sub_code: isv.parameter-invalid:10003） | 重新请求 |

## 响应示例

成功：

```json
{
  "data": {
    "list": [
      {
        "cargo_code": "7267816745850175803",
        "in_warehouse_name": "上海仓",
        "in_warehouse_time": "20220320010101",
        "in_warehouse_type": "采购入库",
        "trace_record": "SJPF731VT6V"
      }
    ],
    "total": "231"
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
  "sub_code": "isv.parameter-invalid:10001",
  "sub_msg": "错误appkey"
}
```

## 备注
