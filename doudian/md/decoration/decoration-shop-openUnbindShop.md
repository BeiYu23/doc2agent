# shop.openUnbindShop

> 店铺装修-解绑门店

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.shop.openUnbindShop` |
| 中文名 | 店铺装修-解绑门店 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/openUnbindShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6302 |
| 更新日期 | `2026-04-02` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tmp_id` | body | string | 是 | 需要解绑的页面id | `7332399246898888986` |
| `shop_id_list` | body | array | 否 | 需要解绑的店铺id。如果选择全部清空，会删除页面下所有门店，不需要传这个。 | `["155753860"]` |
| `is_batch_del` | body | boolean | 是 | 是否全部清空 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/openUnbindShop?app_key=your_appkey_here&method=shop.openUnbindShop&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / RPC调用失败（sub_code: isp.service-error:10004） | 根据报错内容排查 |
| `50002` | 业务处理失败 / 40002:系统开小差了，请稍后重试哟（sub_code: isv.business-failed:40002） | 根据报错日志排查 |

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
  "sub_code": "isp.service-error:10004",
  "sub_msg": "RPC调用失败"
}
```

## 备注
