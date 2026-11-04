# 创建仓内作业单

> instantShopping.createOperationOrder — 创建仓内作业单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建仓内作业单 |
| 文档地址 | `/docs/doudian/retail-order/retail-order-instantShopping-createOperationOrder` |
| 接口 ID | `doudian.retail-order.instantShopping.createOperationOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1531/6946 |
| 更新日期 | `2024-10-29` |

## 接口说明

- 文档书: 订单管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_order_code` | body | string | 是 | 服务商单据code | `33333333` |
| `operation_order_type` | body | mixed | 是 | 单据类型，1=盘点，2=转移 | `3333333` |
| `remark` | body | string | 否 | 备注 | `入库` |
| `update_time` | body | mixed | 是 | 更新时间（Unix时间戳） | `1728908162` |
| `org_shop_id` | body | string | 是 | 货主id | `1333` |
| `warehouse_id` | body | string | 是 | 仓ID | `123132` |
| `order_details` | body | array | 是 | 作业子单列表 | `` |
| `  └ order_detail_code` | body | string | 是 | 服务商单据明细code / 行号 | `1312323123` |
| `  └ goods_id` | body | string | 是 | 货品ID | `1231313213` |
| `  └ operation_details` | body | array | 是 | 作业明细列表 | `` |
| `    └ change_num` | body | mixed | 是 | 变动数量，正数增加，负数减少 | `11` |
| `    └ production_time` | body | mixed | 否 | 生产日期（Unix时间戳）有s生产日期，有必传，否是应对没有生产日期的货品 | `1728908162` |
| `    └ expire_days` | body | mixed | 否 | 保质期（天）,有必传，否是应对没有保质期的货品 | `7` |
| `    └ expire_time` | body | mixed | 否 | 过期时间（天）,有必传，否是应对没有过期时间的货品 | `1728908162` |
| `    └ receive_time` | body | mixed | 是 | 入库时间（Unix时间戳） | `1727348559` |
| `    └ reason` | body | string | 否 | 操作原因 | `无` |
| `    └ stock_type` | body | mixed | 是 | 库存类型，1=正品，2=残次 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.createOperationOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:40001） | 调整参数 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "operation_order_code": "123123132",
      "operation_order_detail": [
        {
          "order_detail_code": "123132123",
          "order_detail_id": "123123132"
        }
      ],
      "operation_order_id": "1231312313"
    }
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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "非法参数"
}
```

## 备注
