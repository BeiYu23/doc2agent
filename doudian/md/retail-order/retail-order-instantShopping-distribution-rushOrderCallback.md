# instantShopping.distribution.rushOrderCallback

> 配送商催单结果回调

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-order.instantShopping.distribution.rushOrderCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1531/7031 |
| 更新日期 | `2024-10-30` |

## 接口说明

- 文档书: 订单管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `rushId` | body | mixed | 是 | 催单ID | `123456` |
| `interfaceRushResult` | body | string | 否 | 接口催单结果 | `{         "IsSuccess": true,         "Msg": "" }` |
| `callRushResult` | body | string | 否 | 外呼催单结果 | `{         "IsSuccess": true,         "Msg": "",         "IsThrough": true }` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.distribution.rushOrderCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
