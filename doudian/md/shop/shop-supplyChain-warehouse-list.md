# supplyChain.warehouse.list

> 外部仓列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.supplyChain.warehouse.list` |
| 中文名 | 外部仓列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/warehouse/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2122 |
| 更新日期 | `2022-06-28` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 否 | 外部仓编码 | `w1111111` |
| `warehouse_name` | body | string | 否 | 仓库名称 | `测试仓名称` |
| `out_warehouse_ids` | body | array | 否 | 外部仓编码列表 | `["w1111111"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/warehouse/list?app_key=your_appkey_here&method=supplyChain.warehouse.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_list` | array | 区域仓列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:20000） | 系统错误 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_list": [
      {
        "addr": [
          {
            "addr_id1": "100",
            "addr_id2": "100100",
            "addr_id3": "100110",
            "addr_id4": "100111",
            "create_time": "1623918481",
            "update_time": "1623918481"
          }
        ],
        "create_time": "1623918481",
        "intro": "介绍",
        "name": "名字",
        "out_warehouse_id": "w111111",
        "update_time": "1623918481",
        "warehouse_id": "6853386941874864391"
      }
    ]
  },
  "err_no": 0,
  "message": "success",
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
  "sub_code": "isp.service-error:20000",
  "sub_msg": "系统错误"
}
```

## 备注
