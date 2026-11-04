# shop.topupTmaToken

> 获取腾讯侧小程序登陆态token

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.shop.topupTmaToken` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/topupTmaToken` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7577 |
| 更新日期 | `2025-08-05` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `saler` | body | string | 否 | 主播ID | `93922552059` |
| `game_id` | body | string | 是 | 腾讯侧的游戏ID | `yxzj` |
| `offer_id` | body | string | 是 | 腾讯侧的offerID | `1450224787` |
| `tencent_env` | body | string | 否 | 腾讯LLToken获取接口的环境 | `dev、test、sandbox、release` |
| `use_sdk` | body | string | 否 | 获取sdk拉端参数 | `true、false` |
| `device_platform` | body | string | 否 | 设备平台，android、ios | `android、ios、iphone` |
| `app_id` | body | string | 否 | 标识请求来自抖音、极速版或其他端 | `1128、2329` |
| `channel` | body | string | 否 | 标识客户端渠道，区分内测包与线上包 | `local_test` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/topupTmaToken?app_key=your_appkey_here&method=shop.topupTmaToken&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `wx_link` | string | 跳转微信liveLink的链接 | `weixin://dl/business/?t=rqWgJJakBau` |
| `qq_link` | string | 跳转QQliveLink的链接 | `mqqapi://miniapp/open?_atype=0&_mappid=1111906964&_miniapptype=1&_mvid=&_path=pages%2FgameAccountBind%2Findex&_vt=3&via=qq_txyxll&_sig=3200763575&_nq=c%3DSdk%26a%3DGenMiniappScheme%26actId%3D12608%26code%3DwWHoXmTPD7Jk%252FAE%252FIju1kZqwXD5c%252F%252BKhpHveitFm%252BR0u9K9ABail1R9pQN%252FOGc8G%26faceUrl%3D%26gameIdList%3Dyxzj%26livePlatId%3Ddouyinec%26nickName%3D%26sig%3D58157a478a2c5c6cd3d2b2e94f8d5548%26t%3D1750910179` |
| `err_no` | mixed | 状态码，0表示成功 | `暂无` |
| `err_tips` | string | 错误信息 | `暂无` |
| `token` | string | 登陆态的token | `暂无` |
| `user_name` | string | sdk方式要拉起的livelink小程序的userName | `gh_49af166706ae` |
| `wx_app_id` | string | sdk方式拉起livelink小程序的小程序微信appId | `wx707e2eb408780a5b` |
| `qq_app_id` | string | sdk方式拉起livelink小程序的小程序QQ appId | `1111906964` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "err_no": "暂无",
    "err_tips": "暂无",
    "qq_app_id": "1111906964",
    "qq_link": "mqqapi://miniapp/open?_atype=0&_mappid=1111906964&_miniapptype=1&_mvid=&_path=pages%2FgameAccountBind%2Findex&_vt=3&via=qq_txyxll&_sig=3200763575&_nq=c%3DSdk%26a%3DGenMiniappScheme%26actId%3D12608%26code%3DwWHoXmTPD7Jk%252FAE%252FIju1kZqwXD5c%252F%252BKhpHveitFm%252BR0u9K9ABail1R9pQN%252FOGc8G%26faceUrl%3D%26gameIdList%3Dyxzj%26livePlatId%3Ddouyinec%26nickName%3D%26sig%3D58157a478a2c5c6cd3d2b2e94f8d5548%26t%3D1750910179",
    "token": "暂无",
    "user_name": "gh_49af166706ae",
    "wx_app_id": "wx707e2eb408780a5b",
    "wx_link": "weixin://dl/business/?t=rqWgJJakBau"
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
