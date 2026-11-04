# crossBorder.notifyWarehouseFeeOrder

> 服务商回传仓租计费明细

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossBorder.notifyWarehouseFeeOrder` |
| 中文名 | 服务商回传仓租计费明细 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/notifyWarehouseFeeOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/2824 |
| 更新日期 | `2022-12-22` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ws_store_no` | body | string | 是 | 仓租单号 | `WS123456` |
| `warehouse_code` | body | string | 是 | 仓库编码 | `123456` |
| `fee_date` | body | number | 是 | 计费日期。 十位秒级时间戳，需要截断时分秒，否则会被校验住报错。 如 1640966400  表示2022-01-01 00:00:00 | `1640966400` |
| `need_charge` | body | boolean | 是 | 是否需要计费 | `true` |
| `vendor` | body | string | 是 | 服务商编码 | `GZJS` |
| `detail_list` | body | array | 否 | 当仓租单需要计费时必传 | `` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `7074780` |
| `  └ order_no` | body | string | 是 | 订单号 | `7234512` |
| `  └ order_type` | body | string | 是 | 订单类型  采购入库：PURCHASE_IN;  销退入库：SALE_RETURN_IN;  库存调整（盘盈）：INVENTORY_ADJUST | `PURCHASE_IN` |
| `  └ stock_num` | body | number | 是 | 结算库存数（T-1日期末库存） | `10` |
| `  └ warehouse_area_type` | body | string | 是 | 库区类型：  1-普通区 2-恒温区 3-冷藏区 4-冷冻区 5-急冻区 6-深冷区 | `2` |
| `  └ storage_age` | body | number | 是 | 库龄（单位是天），10天 | `10` |
| `  └ bar_code` | body | string | 否 | 货品条码 | `123456` |
| `  └ length` | body | number | 是 | 长（单位 mm） | `10` |
| `  └ width` | body | number | 是 | 宽（单位 mm） | `10` |
| `  └ height` | body | number | 是 | 高（单位 mm） | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comtest/encrypt/2?app_key=your_appkey_here&method=test.encrypt.2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:1005） | 联系平台研发 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:20001） | 修正参数重新传参 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:20002） | 联系平台研发 |
| `50002` | 业务处理失败 / 无效的状态越迁（sub_code: isv.business-failed:20003） | 联系平台研发 |
| `50002` | 业务处理失败 / 存在重复的记录（sub_code: isv.business-failed:20004） | 联系平台研发 |
| `80000` | 风控拦截 / 未授权访问（sub_code: isv.risk-control-failed:20005） | 获取授权 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "2",
    "or": "7"
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
  "sub_code": "isp.service-error:1005",
  "sub_msg": "系统内部错误"
}
```

## 备注
