# product.isCategoryMigrateObj

> 主要用于类目树升级场景，判断店铺和类目的信息是否已经升级需使用新的类目信息做相关操作，如商品发布，商品更新等

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.product.isCategoryMigrateObj` |
| 中文名 | 主要用于类目树升级场景 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/isCategoryMigrateObj` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/8058 |
| 更新日期 | `2026-01-21` |

## 接口说明

- 文档书: 工具API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 否 | 类目id，非必填参数，传入会查询判断类目是新的还是老的。 | `20117` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_result` | boolean | 判断店铺是否已经升级为类目树（新类目店铺），true-已升级，false-未升级 | `true` |
| `category_result` | boolean | 判断类目是否已经升级为类目树（新类目信息），true-新类目，false-旧类目 | `false` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常,请重试（sub_code: isp.service-error:2010001） | 重试 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:2010001",
  "sub_msg": "系统异常,请重试"
}
```

## 备注
