# promise.pushProductExp

> 推送(商品SKU)过期时间

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.promise.pushProductExp` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/promise/pushProductExp` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/4688 |
| 更新日期 | `2023-09-12` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_exp_list` | body | array | 是 | 待同步的商品列表（store_id-product-sku-exp），单次同步量需小于1000 | `` |
| `  └ product_id` | body | number | 是 | 抖音商品ID | `3632246015060527131` |
| `  └ sku_id` | body | number | 是 | 抖音SKU ID | `6917539360121882326` |
| `  └ exp_time` | body | number | 是 | 商品过期时间 | `1692901833` |
| `  └ store_id` | body | number | 是 | 门店ID | `1111409547` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/promise/pushProductExp?app_key=your_appkey_here&method=promise.pushProductExp&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必要入参，请调整后重试（sub_code: isv.missing-parameter:40002） | 缺少必要入参，请重试 |
| `40004` | 非法的参数 / 非法入参，请调整后重试（sub_code: isv.parameter-invalid:40004） | 非法入参，请调整后重试 |
| `50002` | 业务处理失败 / 商品过期时间更新部分失败（sub_code: isv.business-failed:50002） | 商品过期时间更新部分失败 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:40002",
  "sub_msg": "缺少必要入参，请调整后重试"
}
```

## 备注
