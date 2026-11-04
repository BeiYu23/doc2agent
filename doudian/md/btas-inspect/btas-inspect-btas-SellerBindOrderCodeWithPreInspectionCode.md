# btas.SellerBindOrderCodeWithPreInspectionCode

> 商家_商家针对前置质检订单进行绑码或者换绑

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.SellerBindOrderCodeWithPreInspectionCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/SellerBindOrderCodeWithPreInspectionCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2878 |
| 更新日期 | `2023-01-30` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `0738304024` |
| `inspection_code` | body | string | 是 | 质检证书编号，仅字母数字 | `ZJ324342351123` |
| `inspection_sc_id` | body | number | 是 | 质检机构ID | `32` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comtest/encrypt/2?app_key=your_appkey_here&method=test.encrypt.2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

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
    "data": "2",
    "or": "7"
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
