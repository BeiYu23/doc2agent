# order.serviceDetail

> 商家服务单详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.serviceDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/serviceDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1832 |
| 更新日期 | `2024-07-09` |

## 接口说明

- 文档书: 订单API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_id` | body | number | 是 | 服务请求列表中获取的id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `detail` | object | 详情 | `` |
| `logs` | array | 日志 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10004:无权限（sub_code: isv.business-failed:10004） | 10004:无权限 |

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
  "sub_code": "isv.business-failed:10004",
  "sub_msg": "10004:无权限"
}
```

## 备注
