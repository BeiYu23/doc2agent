# 店铺装修-绑定门店

> shop.openBindShop — 店铺装修-绑定门店

| 元信息 | 值 |
| --- | --- |
| 中文名 | 店铺装修-绑定门店 |
| 文档地址 | `/docs/doudian/decoration/decoration-shop-openBindShop` |
| 接口 ID | `doudian.decoration.shop.openBindShop` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/openBindShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6303 |
| 更新日期 | `2026-04-02` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tmp_id` | body | string | 是 | 需要和门店绑定的页面 | `7332399246898888986` |
| `shop_list` | body | array | 是 | 需要绑定的门店 | `["155753860"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/openBindShop?app_key=your_appkey_here&method=shop.openBindShop&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_success` | array | 成功门店 | `["155753860"]` |
| `shop_fail` | array | 失败门店 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / RPC错误（sub_code: isp.service-error:10004） | 根据报错内容排查 |
| `50002` | 业务处理失败 / 40002:系统开小差了，请稍后重试哟（sub_code: isv.business-failed:40002） | 根据报错内容排查 |

## 响应示例

成功：

```json
{
  "data": {
    "shop_fail": [
      {
        "msg": "\"无门店权限\"",
        "shop_fail": "[\"155753860\"]"
      }
    ],
    "shop_success": "[\"155753860\"]"
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
  "sub_code": "isp.service-error:10004",
  "sub_msg": "RPC错误"
}
```

## 备注
