# supplyChain.sku.syncSupplyStock

> 设置库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.supplyChain.sku.syncSupplyStock` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2123 |
| 更新日期 | `2022-06-28` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | number | 是 | skuid | `111111111111` |
| `product_id` | body | number | 否 | productid | `11111111` |
| `out_warehouse_id` | body | string | 否 | 外部仓库编码 | `w12345` |
| `incremental` | body | boolean | 否 | 是否增量同步，当前供销平台只支持增量同步 | `true` |
| `idempotent_id` | body | string | 否 | 请求幂等键 | `w12345_0_1656262875` |
| `stock_num` | body | number | 是 | 库存变更量，负值代表减 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.sku.syncSupplyStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:20000） | 系统错误 |

## 响应示例

成功：

```json
{
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
