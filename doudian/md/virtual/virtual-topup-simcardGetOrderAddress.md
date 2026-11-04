# topup.simcardGetOrderAddress

> 获取号卡商品订单中填写的地址

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.virtual.topup.simcardGetOrderAddress` |
| 中文名 | 获取号卡商品订单中填写的地址 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/simcardGetOrderAddress` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/8217 |
| 更新日期 | `2026-04-22` |

## 接口说明

- 文档书: 虚拟充值API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 订单号 | `123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/simcardGetOrderAddress?app_key=your_appkey_here&method=topup.simcardGetOrderAddress&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `encrypt_post_tel` | string | 收件人电话 | `12312341234` |
| `encrypt_post_receiver` | string | 收件人姓名 | `aaa` |
| `post_addr` | object | 收件人地址 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "encrypt_post_receiver": "aaa",
    "encrypt_post_tel": "12312341234",
    "post_addr": {
      "city": {
        "id": "310000",
        "name": "市辖区"
      },
      "encrypt_detail": "金海街道",
      "province": {
        "id": "31",
        "name": "上海市"
      },
      "street": {
        "id": "310120001",
        "name": "金海街道"
      },
      "town": {
        "id": "310120",
        "name": "奉贤区"
      }
    }
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
