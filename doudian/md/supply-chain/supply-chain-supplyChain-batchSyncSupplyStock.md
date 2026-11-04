# supplyChain.batchSyncSupplyStock

> 批量同步库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.batchSyncSupplyStock` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/batchSyncSupplyStock` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/7335 |
| 更新日期 | `2025-03-05` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 否 | 货品id | `123` |
| `stock_list` | body | array | 否 | 库存列表 | `` |
| `  └ out_warehouse_id` | body | string | 否 | 外部仓编码 | `"123"` |
| `  └ incremental` | body | boolean | 否 | 库存更新方式， 当前只支持增量 | `true` |
| `  └ idempotent_id` | body | string | 否 | 幂等ID，仅incremental=true时有用 | `123` |
| `  └ stock_num` | body | mixed | 否 | 库存量 | `1` |
| `  └ stock_serial_no_list` | body | array | 否 | 库存实物序列号，如手机即为每个手机的IMEI | `["123"]` |
| `  └ sku_id` | body | mixed | 否 | skuid | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/batchSyncSupplyStock?app_key=your_appkey_here&method=supplyChain.batchSyncSupplyStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
