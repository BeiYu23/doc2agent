# 查询商品服务权益

> rights.getProductPrivileges — 查询商品服务权益

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询商品服务权益 |
| 文档地址 | `/docs/doudian/service/service-rights-getProductPrivileges` |
| 接口 ID | `doudian.service.rights.getProductPrivileges` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/rights/getProductPrivileges` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1532/7961 |
| 更新日期 | `2025-12-19` |

## 接口说明

- 文档书: 三方客服API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `client_param` | body | object | 否 | 非必传，用户客户端查询参数 | `` |
| `  └ app_id` | body | mixed | 否 | 用户客户端id，不传默认抖音app | `1128` |
| `  └ app_version` | body | mixed | 否 | 客户端版本 | `370000` |
| `product_params` | body | array | 是 | 必传，商品查询参数 | `` |
| `  └ author_id` | body | mixed | 否 | 非必传，带货达人id | `2228068890454395` |
| `  └ product_id` | body | mixed | 是 | 必传，商品id | `3580838793961427240` |
| `doudian_open_id` | body | string | 否 | 非必传，doudian_open_id，用于解析消费者uid，传入则会校验用户权益资格 | `1@#YOUR_SECRET_KEY` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/rights/getProductPrivileges?app_key=your_appkey_here&method=rights.getProductPrivileges&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_privilege` | array | 商品权益列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 未知错误（sub_code: isp.service-error:1601000000） | 需要联系开发者 |
| `40002` | 缺少必选参数 / 缺少商品参数（sub_code: isv.missing-parameter:1601000013） | 检查商品信息是否传入 |
| `20000` | 系统错误 / 商品信息查询失败（sub_code: isp.service-error:1601100043） | 优先重试，重试仍不成功检查商品是否已下架或商品Id是否有误 |
| `10001` | 请求部分失败 / 部分商品信息查询失败（sub_code: isv.business-part-failed:1601100044） | 检查是否有商品已下架 |
| `20001` | 内部服务超时 / 查询运费险失败（sub_code: isp.service-timeout-error:1601100018） | 可重试 |
| `20001` | 内部服务超时 / 查询运费险失败（sub_code: isp.service-timeout-error:1601100019） | 可重试 |
| `20000` | 系统错误 / 查询商品失败，非授权商家商品（sub_code: isp.service-error:1601100054） | 查询的商品非授权商家的商品 |

## 响应示例

成功：

```json
{
  "data": {
    "product_privilege": [
      {
        "privilege_infos": [
          {
            "code": "insurance_freight",
            "inner_code": "insurance_freight_shop_bulk",
            "label": "大件运费险"
          }
        ],
        "product_id": "3580838793961427240",
        "product_id_str": "\"3580838793961427240\""
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1601000000",
  "sub_msg": "未知错误"
}
```

## 备注
