# 获取前端组件token

> order.getMCToken — 获取前端组件token

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取前端组件token |
| 文档地址 | `/docs/doudian/tool/tool-order-getMCToken` |
| 接口 ID | `doudian.tool.order.getMCToken` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/getMCToken` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/3586 |
| 更新日期 | `2025-06-23` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getMCToken?app_key=your_appkey_here&method=order.getMCToken&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `token` | string | 前端组件token | `ahiosdfhuiq2h41io5j4398ras` |
| `expire_time` | mixed | token过期时间，时间戳，秒级 | `1680522258` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 数据加密失败，请稍后重试（sub_code: isv.business-failed:300001） | 请稍后重试 |
| `50002` | 业务处理失败 / 服务器错误，请稍后重试（sub_code: isv.business-failed:10000000） | 请稍后重试 |
| `50002` | 业务处理失败 / 查询该shopID对应的用户信息为空（sub_code: isv.business-failed:605040009） | 检查用户id和店铺id |

## 响应示例

成功：

```json
{
  "data": {
    "expire_time": "1680522258",
    "token": "ahiosdfhuiq2h41io5j4398ras"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:300001",
  "sub_msg": "数据加密失败，请稍后重试"
}
```

## 备注
