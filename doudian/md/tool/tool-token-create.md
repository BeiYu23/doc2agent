# token.create

> 生成token API。创建token成功即可，可以定期调/token/refresh接口来刷新token避免过期，请不要频繁的调用！
推荐使用SDK进行token获取：https://op.jinritemai.com/docs/guide-docs/1

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.token.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/token/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/1600 |
| 更新日期 | `2025-01-06` |

## 接口说明

- 文档书: 工具API（版本 V2.13）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `code` | body | string | 否 | 授权码；参数必传，工具型应用: 传code值；自用型应用:传"" | `82bdc687-eff1-4f63-8444-0b43086c25fd` |
| `grant_type` | body | string | 是 | 授权类型 ；【工具型应用:authorization_code  自用型应用:authorization_self】，如果自用型应用有授权code，传authorization_code | `authorization_code` |
| `test_shop` | body | string | 否 | 判断测试店铺标识 ，非必传，若新增测试店铺传1，若不是则不必传 | `2` |
| `shop_id` | body | string | 否 | 店铺ID，抖店自研应用使用。当auth_subject_type不为空时，该字段请勿传值，请将值传入到auth_id字段中 | `17239` |
| `auth_id` | body | string | 否 | 授权id，配合auth_subject_type字段使用。当auth_subject_type不为空时，请使用auth_id字段传值，shop_id请勿使用。 | `112334` |
| `auth_subject_type` | body | string | 否 | 授权主体类型，配合auth_id字段使用，YunCang -云仓；WuLiuShang -物流商；WLGongYingShang -物流供应商；MiniApp -小程序；MCN-联盟MCN机构；DouKe-联盟抖客 ；Colonel-联盟团长； | `WuLiuShang` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `access_token` | string | token值。 Tips： 1. 在 access_token 过期前1h之前，ISV使用 refresh_token 刷新时，会返回原来的 access_token 和 refresh_token，但是二者有效期不会变； 2. 在 access_token 过期前1h之内，ISV使用 refresh_token 刷新时，会返回新的 access_token 和 refresh_token，但是原来的 access_token 和 refresh_token 继续有效一个小时； 3. 在 access_token 过期后，ISV使用 refresh_token 刷新时，将获得新的 acces_token 和 refresh_token，同时原来的 acces_token 和 refresh_token 失效； | `5a3bd7d0-1b48-46d6-811e-7e05ace08a2f` |
| `expires_in` | number | 过期时间(秒级时间戳) | `412219354` |
| `refresh_token` | string | 刷新token值。用于刷新access_token的刷新令牌（有效期：14 天） | `50b6ae40-ed8f-4b60-a4af-2ed743a4b903` |
| `scope` | string | 范围 | `SCOPE` |
| `shop_id` | number | 店铺ID | `11111172` |
| `shop_name` | string | 店铺名称 | `李飞测试放心花人店一体` |
| `authority_id` | string | 授权ID | `3445403781179769176` |
| `auth_subject_type` | string | 授权主体类型 | `WuLiuShang` |
| `encrypt_operator` | string | 操作店铺账号（加密），不支持解密 | `x123xxxxxxxxxx` |
| `operator_name` | string | 操作店铺账号昵称（脱敏） | `*磊` |
| `shop_biz_type` | number | 店铺业务类型。0：普通店铺，1：即时零售连锁店，2：即时零售个体店 | `0` |
| `toutiao_id` | string | token生成对应的账号 | `121212` |
| `token_type` | number | 0表示token是由主账号生成，1表示token由子账号生成 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 31006:生成token失败, 店铺授权已失效，请重新引导商家完成店铺授权（sub_code: isv.business-failed:31006） | 店铺授权已失效 |
| `50002` | 业务处理失败 / 31020:authCode对应的授权不存在（sub_code: isv.business-failed:31020） | 授权不存在 |
| `50002` | 业务处理失败 / 31005:根据appId和shopId未找到授权记录（sub_code: isv.business-failed:31005） | 授权不存在 |
| `50002` | 业务处理失败 / 31021:authCode已失效，请重新点击去使用按钮（sub_code: isv.business-failed:31021） | authCode不存在或者过期失效，请重新在商家后台获取code |
| `50002` | 业务处理失败 / 31007:生成token失败，code已经失效（code的有效期为10分钟）（sub_code: isv.business-failed:31007） | authCode已经过期 |
| `50002` | 业务处理失败 / 31012:刷新token失败，有并发请求（sub_code: isv.business-failed:31012） | create/token接口有并发请求，请减少并发次数 |
| `50002` | 业务处理失败 / 31003:生成token失败（sub_code: isv.business-failed:31003） | grant_type参数取值不正确,请参照文档根据应用类型填写不同的值 |
| `50002` | 业务处理失败 / 4:非自用型应用code不能为空（sub_code: isv.business-failed:4） | 非自用型应用code不能为空 |
| `50002` | 业务处理失败 / 31011:生成token失败, 当前应用不存在（sub_code: isv.business-failed:31011） | 当前应用不存在，请检查请求参数app_key的值 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:31006",
  "sub_msg": "31006:生成token失败, 店铺授权已失效，请重新引导商家完成店铺授权"
}
```

## 备注
