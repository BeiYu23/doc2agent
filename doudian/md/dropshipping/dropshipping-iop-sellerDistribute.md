# iop.sellerDistribute

> 【商家】分配代发订单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.sellerDistribute` |
| 中文名 | 【商家】分配代发订单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/sellerDistribute` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/958 |
| 更新日期 | `2021-09-09` |

## 接口说明

- 文档书: 代发API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `distribute_order_list` | body | array | 是 | 待分配列表，一次批量最多100个 | `` |
| `  └ supplier_shop_id` | body | number | 是 | 要分配的厂商的店铺ID | `77977` |
| `  └ distr_order_id` | body | string | 是 | 代打订单号 | `77878786688878787` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/sellerDistribute?app_key=your_appkey_here&method=iop.sellerDistribute&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `distribute_order_reuslts` | array | 分配结果明细 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 请检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "distribute_order_reuslts": [
      {
        "distr_order_id": "77878786688878787",
        "err_no": "0",
        "message": "succ",
        "supplier_shop_id": "77977"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "参数错误"
}
```

## 备注
