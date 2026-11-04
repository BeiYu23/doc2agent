# order.PackageProcessSuccess

> 套餐办理成功

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.virtual.order.PackageProcessSuccess` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/PackageProcessSuccess` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/6903 |
| 更新日期 | `2024-09-24` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 子订单id | `"123456"` |
| `combo_id` | body | number | 是 | skuid | `123` |
| `cert_list` | body | array | 是 | 卡券信息列表 | `` |
| `  └ cert_no` | body | string | 是 | 订单号与上面订单号保持一致 | `"123456"` |
| `  └ status` | body | number | 是 | 卡券状态 | `固定值传2` |
| `  └ grant_time` | body | number | 是 | 发券时间,格式:秒级时间戳 | `当前时间戳，秒级` |
| `op` | body | object | 否 | 风控相关信息 | `` |
| `  └ platform` | body | string | 否 | 操作平台 | `"system"` |
| `  └ op_uid` | body | number | 否 | 操作人uid | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/decryptByteDanceMobile?app_key=your_appkey_here&method=power.decryptByteDanceMobile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_message` | string | 返回信息 | `"成功"` |
| `ret_status` | string | 返回状态,依据状态判定是否需要重试 | `"Success"` |
| `ret_code` | string | 返回码 | `"0"` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "real_tel_no": "0"
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
