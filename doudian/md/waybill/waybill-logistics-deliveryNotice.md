# 顺丰极效前置订单放行/回退

> logistics.deliveryNotice — 顺丰极效前置订单放行/回退；

| 元信息 | 值 |
| --- | --- |
| 中文名 | 顺丰极效前置订单放行/回退 |
| 文档地址 | `/docs/doudian/waybill/waybill-logistics-deliveryNotice` |
| 接口 ID | `doudian.waybill.logistics.deliveryNotice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/deliveryNotice` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1578 |
| 更新日期 | `2021-12-28` |

## 接口说明

- 文档书: 电子面单API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_no` | body | string | 是 | 运单号 | `SF1345778775768` |
| `notice_type` | body | string | 是 | 放行/回退 | `71` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/deliveryNotice?app_key=your_appkey_here&method=logistics.deliveryNotice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | boolean | 是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result": "true"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
