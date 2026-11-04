# order.addresSwitchConfig

> 获取App对于商家订单修改地址的审核权限
获取App对于商家订单修改地址的审核权限

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.addresSwitchConfig` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/addresSwitchConfig` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1838 |
| 更新日期 | `2021-05-12` |

## 接口说明

- 文档书: 订单API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/addresSwitchConfig?app_key=your_appkey_here&method=order.addresSwitchConfig&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `authorized_status` | number | 0: 商家当前未开启审核 1:商家当前已开启审核，但本应用不可进行审核 2:商家当前已开启审核，且本应用可审核 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "authorized_status": "0"
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
