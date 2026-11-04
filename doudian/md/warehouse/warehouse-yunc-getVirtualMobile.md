# yunc.getVirtualMobile

> 隐私小号获取

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.getVirtualMobile` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/getVirtualMobile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/3583 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `platform_order_no` | body | string | 是 | 店铺父订单号，抖店平台生成，平台下唯一 | `6917531973167941080` |
| `out_order_no` | body | string | 是 | ERP单号 | `1111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/getVirtualMobile?app_key=your_appkey_here&method=yunc.getVirtualMobile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_new_create` | boolean | 是否新创建 | `true/false` |
| `mobile_virtual` | string | 虚拟号值 | `10220333123` |
| `expire_time` | string | 虚拟号过期时间，格式为yyyy-MM-dd HH:mm:ss，时区为GMT+8，例如：2016-01-01 12:00:00 | `2023-04-17 20:00:00` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20001` | 内部服务超时 / 1103:请求内部服务超时（sub_code: isp.service-timeout-error:1103） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "expire_time": "2023-04-17 20:00:00",
    "is_new_create": "true/false",
    "mobile_virtual": "10220333123"
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
  "code": 20001,
  "msg": "内部服务超时",
  "sub_code": "isp.service-timeout-error:1103",
  "sub_msg": "1103:请求内部服务超时"
}
```

## 备注
