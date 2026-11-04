# 短信回传

> logistics.virtualServicePushSms — 短信回传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 短信回传 |
| 文档地址 | `/docs/doudian/order/order-logistics-virtualServicePushSms` |
| 接口 ID | `doudian.order.logistics.virtualServicePushSms` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/virtualServicePushSms` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/2676 |
| 更新日期 | `2022-10-31` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `request_id` | body | string | 是 | 请求id | `10bc556c-5f64-45af-b9b2-63a9d98beff4` |
| `record_id` | body | string | 是 | 服务商短信记录id | `C202209101052380A21184104136870` |
| `service_code` | body | string | 是 | 服务商身份标识 | `volcengine` |
| `tel_a` | body | string | 是 | A真实号码 | `13013013013` |
| `tel_x` | body | string | 是 | 虚拟主号 | `13141200999` |
| `tel_b` | body | string | 是 | B真实号码 | `13113113113` |
| `sub_id` | body | string | 否 | 绑定关系id | `0008b5c563f5486dbb5e99875f3dd9a2` |
| `send_type` | body | string | 是 | 13：话单中A号码接收短信 14：话单中A号码发送短信 30：无绑定关系的短信 | `13` |
| `area_code` | body | string | 否 | 区域 | `010` |
| `receive_time` | body | string | 是 | 短信接收时间 | `2006-01-02 15:04:05` |
| `sms_content` | body | string | 是 | 短信内容 | `【测试】这是一条测试短信` |
| `sms_result` | body | string | 是 | 发送状态 | `SMS_SUCCESS` |
| `sms_num` | body | string | 是 | 短信条数 | `1` |
| `remark` | body | string | 否 | 备注 | `发送成功的短信无需解析` |
| `ext` | body | string | 否 | 扩展字段 | `{}` |
| `tel_xext` | body | string | 否 | 分机号 | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/virtualServicePushSms?app_key=your_appkey_here&method=logistics.virtualServicePushSms&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:-1） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "isp.service-error:-1",
  "sub_msg": "系统错误"
}
```

## 备注
