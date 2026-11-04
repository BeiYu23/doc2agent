# instantShopping.order.uploadPic

> 商家上传图片

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-order.instantShopping.order.uploadPic` |
| 中文名 | 商家上传图片 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1531/8558 |
| 更新日期 | `2026-08-31` |

## 接口说明

- 文档书: 订单管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 否 | 店铺单号 | `"6954957304399009191"` |
| `url_list` | body | array | 否 | 商家上传的图片列表 | `["https://cloud.maiyatian.com/order_YOUR_SECRET_KEY.jpg","https://cloud.maiyatian.com/order_YOUR_SECRET_KEY.jpg"]` |
| `scene` | body | string | 否 | 业务场景标识。鲜花场景赋值为"realShot" | `realShot` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.order.uploadPic&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:100001） | 参数错误 |
| `50002` | 业务处理失败 / 非本店铺订单，不允许操作（sub_code: isv.business-failed:200000202） | 更换店铺订单 |
| `50002` | 业务处理失败 / 查询订单失败，请重试（sub_code: isv.business-failed:200000102） | 查询订单失败，请重试 |
| `50002` | 业务处理失败 / 处理图片信息失败，请重试（sub_code: isv.business-failed:200000405） | 处理图片信息失败，请重试 |
| `50002` | 业务处理失败 / 图片包含敏感信息，请更换后重试（sub_code: isv.business-failed:200000404） | 图片包含敏感信息，请更换后重试 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:100001",
  "sub_msg": "参数错误"
}
```

## 备注
