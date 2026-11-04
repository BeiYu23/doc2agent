# token.refresh

> 使用refresh_token刷新access_token

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.token.refresh` |
| 中文名 | 使用refresh_token刷新access… |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/token/refresh` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/1601 |
| 更新日期 | `2024-11-14` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `refresh_token` | body | string | 是 | 用于刷新access_token的刷新令牌；有效期：14 天； | `82bdc687-eff1-4f63-8444-0b43086c25fd` |
| `grant_type` | body | string | 是 | 授权类型；请传入默认值：refresh_token | `refresh_token1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/token/refresh?app_key=your_appkey_here&method=token.refresh&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `access_token` | string | 用于调用API的access_token 过期时间为expires_in值 可通过refresh_token刷新获取新的access_token，过期时间仍为expires_in值 | `82bdc687-eff1-4f63-8444-0b43086c25fd` |
| `expires_in` | mixed | access_token过期时间；Unix时间戳：秒 | `530808` |
| `refresh_token` | string | 用于刷新access_token的刷新令牌（有效期：14 天） | `ed14a703-1f27-4a0b-9b94-759242744ec8` |
| `scope` | string | 权限范围 | `SCOPE` |
| `shop_id` | mixed | 店铺ID | `222` |
| `shop_name` | string | 店铺名称 | `测试店铺` |
| `authority_id` | string | 授权ID,店铺授权为店铺id，达人授权为达人id； | `1321324` |
| `auth_subject_type` | string | 授权主体类型 | `WuLiuShang` |
| `shop_biz_type` | mixed | 店铺业务类型。0：普通店铺，1：即时零售连锁店，2：即时零售个体店 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 31009:生成token失败,  token不存在（sub_code: isv.business-failed:31009） | 检查token是否存在 |
| `50002` | 业务处理失败 / 31006:生成token失败, 店铺授权已失效，请重新引导商家完成店铺授权（sub_code: isv.business-failed:31006） | 检查授权是否开启 |
| `50002` | 业务处理失败 / 31008:生成token失败, token已过期（sub_code: isv.business-failed:31008） | token已经过期，请重新生成token |
| `50002` | 业务处理失败 / 31012:刷新token失败，有并发请求（sub_code: isv.business-failed:31012） | 有并发请求 |
| `50002` | 业务处理失败 / 31011:生成token失败, 开发者应用已经被删除（sub_code: isv.business-failed:31011） | 应用已经被删除 |
| `50002` | 业务处理失败 / 31003:生成token失败, grant_type参数取值不正确,请参照文档根据应用类型填写不同的值（sub_code: isv.business-failed:31003） | grant_type参数类型不正确 |
| `40002` | 缺少必选参数 / 4:refresh_token、grant_type、及app_key不能为空（sub_code: isv.missing-parameter:4） | refresh_token、grant_type、及app_key不能为空 |
| `50002` | 业务处理失败 / 7:服务器错误（sub_code: isv.business-failed:7） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "access_token": "82bdc687-eff1-4f63-8444-0b43086c25fd",
    "auth_subject_type": "WuLiuShang",
    "authority_id": "1321324",
    "expires_in": "530808",
    "refresh_token": "ed14a703-1f27-4a0b-9b94-759242744ec8",
    "scope": "SCOPE",
    "shop_biz_type": "0",
    "shop_id": "222",
    "shop_name": "测试店铺"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:31009",
  "sub_msg": "31009:生成token失败,  token不存在"
}
```

## 备注
