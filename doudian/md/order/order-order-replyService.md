# order.replyService

> 回复服务请求

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.replyService` |
| 中文名 | 回复服务请求 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/replyService` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1917 |
| 更新日期 | `2022-11-14` |

## 接口说明

- 文档书: 订单API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `id` | body | number | 是 | 服务请求列表中获取的id | `123` |
| `reply` | body | string | 是 | 回复内容 | `哈哈哈` |
| `evidence` | body | string | 否 | 回复凭证，通过/order/serviceDetail获取是否当前服务单</br>是否必须上传凭证。多张图片用竖线分开。不超过4张 | `img_url1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/replyService?app_key=your_appkey_here&method=order.replyService&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务申请已经回复，无需重复回复（sub_code: isp.service-error:10009） | - |
| `20000` | 系统错误 / 参数错误（sub_code: isp.service-error:10002） | - |
| `50002` | 业务处理失败 / 图片链接有误（sub_code: isv.business-failed:10017） | - |

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
  "sub_code": "isp.service-error:10009",
  "sub_msg": "服务申请已经回复，无需重复回复"
}
```

## 备注
