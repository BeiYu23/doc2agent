# instantShopping.SyncWarehouseStock

> 同步货品库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.instantShopping.SyncWarehouseStock` |
| 中文名 | 同步货品库存 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/6321 |
| 更新日期 | `2024-07-22` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_id` | body | mixed | 是 | 抖音侧仓ID | `1` |
| `org_shop_id` | body | mixed | 是 | 货主iD | `1111409488` |
| `update_time` | body | mixed | 是 | 1、用于记录此次变更的时间 2、用于防止历史数据替换新数据（如12点的数据先到，11点50的数据后到，则不更新11点50的数据） | `1711248931` |
| `stock_update_list` | body | array | 是 | 需要批量提交的goods_id及对应的数量 数量限制：最多20个货品 | `` |
| `  └ goods_id` | body | string | 是 | 货品id | `111111` |
| `  └ stock_for_sale_num` | body | mixed | 是 | 正品库存（可销售库存数量） | `1111` |
| `  └ stock_locked_num` | body | mixed | 否 | 锁定库存（被待履约单锁定的库存数量） | `1111` |
| `  └ stock_not_for_sale_num` | body | mixed | 否 | 残次品库存（不可销售库存数量） | `111` |
| `  └ remark` | body | string | 否 | 备注 | `abcd` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.commengru/test/encrypt/v1?app_key=your_appkey_here&method=mengru.test.encrypt.v1&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 查询未找到（sub_code: isv.business-failed:40004） | 重试 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:50040） | 重试 |
| `40004` | 非法的参数 / 非法出参（sub_code: isv.parameter-invalid:40001） | 传入合法入参 |
| `50002` | 业务处理失败 / 51040:\|RPCError{PSM:[ecom.stock.backend_rpc] Method:[BatchSetStockForOpen] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[-30001] BizStatusMessage:[181241978商品门店信息不匹配]}:goods_id:3411410950185474\|RPCError{PSM:[ecom.stock.backend_rpc]（sub_code: isv.business-failed:51040） | 51040:\|RPCError{PSM:[ecom.stock.backend_rpc] Method:[BatchSetStockForOpen] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[-30001] BizStatusMessage:[181241978商品门店信息不匹配]}:goods_id:3411410950185474\|RPCError{PSM:[ecom.stock.backend_rpc] |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.business-failed:40004",
  "sub_msg": "查询未找到"
}
```

## 备注
