# supplyCenter.order.query

> 查询采购单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.order.query` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/order/query` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5617 |
| 更新日期 | `2023-11-10` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pur_order_id` | body | string | 是 | 采购单号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/qualityTask?app_key=your_appkey_here&method=product.qualityTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pur_order_info` | object | 采购单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 300202:无此采购单信息（sub_code: isv.business-failed:300202） | 确认店铺下采购单号是否存在 |

## 响应示例

成功：

```json
{
  "data": {
    "is_standard": "true",
    "meet_standard_num": "1",
    "problem_num_to_improve": "10",
    "problem_num_total": "10",
    "problem_type_distribution": [
      {
        "num": "2",
        "type_key": "1",
        "type_name": "商品信息不规范"
      }
    ],
    "product_num_finished": "10",
    "product_num_to_improve_total": "10",
    "product_num_total": "10",
    "standard_rate": "10",
    "task_finish_time": "2021-09-07 01:21:46",
    "task_id": "15293",
    "task_status": "2"
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
  "sub_code": "isv.business-failed:300202",
  "sub_msg": "300202:无此采购单信息"
}
```

## 备注
