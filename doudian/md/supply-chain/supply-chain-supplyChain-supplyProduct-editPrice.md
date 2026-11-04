# supplyChain.supplyProduct.editPrice

> 编辑价格

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.editPrice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2555 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | mixed | 是 | skuId | `11111111111111` |
| `supply_price` | body | mixed | 否 | 供货价（单位分） | `10000` |
| `spec_price_list` | body | array | 否 | 特定供货价 | `` |
| `  └ distributor_id_list` | body | array | 是 | 分销商列表 | `[111111111111]` |
| `  └ supply_price` | body | mixed | 是 | 供货价（单位分） | `10000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getServiceList?app_key=your_appkey_here&method=order.getServiceList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11037:已存在待生效的改价申请，不允许重复操作改价（sub_code: isv.business-failed:11037） | 11037:已存在待生效的改价申请，不允许重复操作改价 |
| `50002` | 业务处理失败 / 11002:查询Sku明细为空（sub_code: isv.business-failed:11002） | 11002:查询Sku明细为空 |
| `50002` | 业务处理失败 / 1300:查询供应商行业信息错误（sub_code: isv.business-failed:1300） | 1300:查询供应商行业信息错误 |

## 响应示例

成功：

```json
{
  "data": {
    "list": [
      {
        "create_time": "2020-12-09 13:34:55",
        "detail": "服务单详情",
        "id": "11111",
        "operate_status": "100",
        "operate_status_desc": "已关闭",
        "order_id": "11222332",
        "reply": "我再来狡辩一次",
        "reply_time": "2020-12-09 13:34:55",
        "service_type": "3",
        "shop_id": "1122",
        "update_time": "2020-12-09 13:34:55"
      }
    ],
    "total": "1122"
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
  "sub_code": "isv.business-failed:11037",
  "sub_msg": "11037:已存在待生效的改价申请，不允许重复操作改价"
}
```

## 备注
