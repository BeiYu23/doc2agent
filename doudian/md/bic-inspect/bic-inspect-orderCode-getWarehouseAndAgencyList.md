# 获取全量QIC质检仓和机构的信息

> orderCode.getWarehouseAndAgencyList — 获取全量QIC质检仓和机构的信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取全量QIC质检仓和机构的信息 |
| 文档地址 | `/docs/doudian/bic-inspect/bic-inspect-orderCode-getWarehouseAndAgencyList` |
| 接口 ID | `doudian.bic-inspect.orderCode.getWarehouseAndAgencyList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/getWarehouseAndAgencyList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/51/6733 |
| 更新日期 | `2024-07-30` |

## 接口说明

- 文档书: BIC质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/orderCode/getWarehouseAndAgencyList?app_key=your_appkey_here&method=orderCode.getWarehouseAndAgencyList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_list` | array | 仓库列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 商家不存在（sub_code: isv.business-failed:50002） | 使用其他商家信息调用 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_list": [
      {
        "address": "新江湾抖音广场T4",
        "agency_list": [
          {
            "agency_id": "101",
            "agency_name": "测试机构",
            "agency_short_name": "测试机构"
          }
        ],
        "area": "杨浦区",
        "city": "上海市",
        "province": "上海市",
        "street": "新江湾城街道",
        "user_name": "测试",
        "user_phone": "13122222222",
        "warehouse_code": "99",
        "warehouse_name": "测试仓库"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:50002",
  "sub_msg": "商家不存在"
}
```

## 备注
