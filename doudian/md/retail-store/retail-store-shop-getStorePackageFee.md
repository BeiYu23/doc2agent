# 获取门店打包费

> shop.getStorePackageFee — 获取门店打包费

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取门店打包费 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-shop-getStorePackageFee` |
| 接口 ID | `doudian.retail-store.shop.getStorePackageFee` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/getStorePackageFee` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2634 |
| 更新日期 | `2024-02-26` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店id | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/getStorePackageFee?app_key=your_appkey_here&method=shop.getStorePackageFee&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `package_fee` | object | 打包费 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1） | 参考文档，重新配置 |
| `20000` | 系统错误（sub_code: isp.service-error:100） | 可重试，若仍然失败可oncall反馈 |
| `50002` | 业务处理失败 / 操作数据库失败（sub_code: isv.business-failed:3） | 可重试，若仍然失败可oncall反馈 |
| `50002` | 业务处理失败 / 门店不存在（sub_code: isv.business-failed:8） | 查看storeId是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "package_fee": {
      "amount": "100"
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
  "sub_code": "isv.parameter-invalid:1",
  "sub_msg": "参数错误"
}
```

## 备注
